---
name: aggiorna-sessione
description: >
  Workflow completo post-sessione. Il DM ha appena giocato la sessione N e fornisce un recap
  in forma libera (come testo nel prompt o come file già salvato). La skill gestisce tutto:
  riformatta il recap in struttura standard, finalizza dm-notes-sessione-N con la realtà
  giocata, aggiorna tutti i file di contorno (party, PNG, fazioni, missioni, rapporti),
  aggiorna i luoghi visitati, prepara la sessione N+1 (aggiornandola se esiste già, creandola
  da zero altrimenti), e chiede conferma per la release.
  Uso: "/aggiorna-sessione N" dove N è il numero della sessione APPENA GIOCATA.
  Alias: "abbiamo giocato la sessione N", "recap della sessione N", "aggiorna dopo sessione N".
---

# Workflow Post-Sessione — /aggiorna-sessione

Sei l'orchestratore del flusso post-sessione. Il DM ha appena giocato la sessione **N** e ti
ha fornito un recap (in qualsiasi forma). Il tuo compito è eseguire tutti gli step in sequenza,
dalla strutturazione del recap fino alla release, senza richiedere interventi intermedi salvo
dove indicato.

La realtà giocata ha sempre la precedenza sul piano teorico.

---

## Step 0 — Verifica prerequisiti

1. Identifica il numero **N** della sessione appena giocata.
   - Se specificato nel comando (es. `/aggiorna-sessione 4`) → usa quel numero.
   - Se non specificato → chiedi al DM: "Quale sessione hai appena giocato?"

2. Verifica che esista `campagna/sessioni/dm-notes-sessione-[N].md`.
   - Se non esiste: fermati e avvisa il DM — non si può aggiornare una sessione mai preparata.

3. Verifica il recap. Uno dei seguenti deve essere vero:
   - Il DM ha fornito il testo del recap direttamente nel prompt → usa quello.
   - Esiste già `campagna/sessioni/recaps/recap-sessione-[N].md` → usalo.
   - Se né l'uno né l'altro: chiedi al DM di fornire il recap (anche in forma libera).

Mostra una conferma dei file identificati prima di procedere:
```
📋 Sessione [N] identificata.
   dm-notes: campagna/sessioni/dm-notes-sessione-[N].md ✅
   recap: [da prompt / da file] ✅
   
Avvio pipeline post-sessione...
```

---

## Come si lancia un agente

Ogni step che nomina un file `ai/agents/*.agent.md` va eseguito da un **sub-agente** (tool
`Agent`, `subagent_type: general-purpose`) con il **modello scritto nel campo `model:` del
frontmatter** di quel file. Non eseguire gli step nel contesto principale: tu orchestri, gli
agenti lavorano.

| Agente | Modello | Perché |
|---|---|---|
| 00 recap-updater (Fase A e B) | `sonnet` | Ristruttura e confronta piano/realtà: serve precisione, non stile |
| 01 session-extractor | `sonnet` | Individua il punto di ripresa e il chunk nella fonte |
| 02 session-translator | `opus` | Scrittura in italiano: è dove la qualità si vede al tavolo |
| 03 session-pc-integrator | `opus` | Hook, segreti e archi dei PG, incrociando molti file |
| 04 session-missions-integrator | `haiku` | In questa campagna quasi sempre legge `missioni-secondarie.md` e termina |
| 05 chapter-png-briefer | `sonnet` | Estrazione PNG per PG, testo informativo |
| 06 session-reviewer | `opus` | Coerenza, continuità, stat block contro la fonte |
| 07 location-updater | `sonnet` | Estrazione luoghi, file markdown, `npm run build` |
| 08 context-updater | `sonnet` | Archivista: registra solo ciò che è scritto |
| 09 read-aloud-reviewer | `opus` | Giudizio di stile sui testi letti al tavolo |

**Prompt del sub-agente** — sempre autosufficiente, perché parte senza il contesto della chat:

```
Sessione giocata: N. Sessione da preparare: N+1.
Leggi ed esegui ai/agents/<file>.agent.md [— solo la Fase X, se indicato].
File di input: <elenco>. File da modificare: <elenco>.
[Se il DM ha dato il recap nel prompt: incollalo qui per intero.]
Scrivi i risultati direttamente sui file. Non fare commit.
Restituisci al massimo 15 righe: file modificati, TODO DM aperti, anomalie.
```

Gli step si passano il lavoro **attraverso i file su disco**, mai attraverso la conversazione:
ogni sub-agente legge ciò che il precedente ha scritto. Aspetta la notifica di completamento
prima di lanciare uno step che dipende dal precedente.

Commit, push e release (Step 8-9) li esegui tu, non un sub-agente.

---

## Pipeline (esegui nell'ordine)

Tra uno step e il successivo, mostra: `✅ Step N completato → avvio Step N+1...`

---

### Step 1 — Riformatta recap (Agente 0 — Fase A) · `sonnet`

Sub-agente su `ai/agents/00-recap-updater.agent.md`, **solo la Fase A**.

Obiettivo: trasformare il testo grezzo del DM nel formato standard strutturato e salvarlo in
`campagna/sessioni/recaps/recap-sessione-[N].md`.

Se il recap era già strutturato nel formato corretto, questo step è veloce: verifica la struttura
e procedi.

---

### Step 2 — Finalizza dm-notes sessione N (Agente 0 — Fase B) · `sonnet`

Sub-agente su `ai/agents/00-recap-updater.agent.md`, **solo la Fase B**.

File da leggere:
- `campagna/sessioni/recaps/recap-sessione-[N].md` ← output Step 1
- `campagna/sessioni/dm-notes-sessione-[N].md` ← piano originale da annotare

Obiettivo: annotare dm-notes-sessione-N.md con i marcatori ✅/⏸️/🔀 per ogni fase, aggiungere
la sezione `📋 ACCADUTO IN SESSIONE` con tabella delta e lista delle scene non giocate da
trasferire a N+1.

**Non leggere né considerare file di sessione con numero > N.**

---

### Step 3 — Riverifica hook PG (Agente 3) · `opus`

Sub-agente su `ai/agents/03-session-pc-integrator.agent.md`, sul dm-notes-N.

Questo step verifica che le note DM riservate per i PG nel dm-notes-N siano ancora coerenti
con la realtà giocata. Non si tratta di aggiungere nuovi hook, ma di correggere quelli già
presenti che siano stati invalidati dai delta.

È uno step rapido: se non ci sono discrepanze, conferma e procedi.

---

> **Step 4 e Step 5 sono indipendenti:** toccano file diversi e leggono entrambi il dm-notes-N già
> finalizzato. Lanciali **in parallelo**, nello stesso messaggio, e aspetta entrambe le notifiche
> prima dello Step 6.

### Step 4 — Aggiorna file di contorno (Agente 8) · `sonnet`

Sub-agente su `ai/agents/08-context-updater.agent.md`.

File da leggere e aggiornare:
- `campagna/party.md`
- `campagna/png-incontrati.md`
- `campagna/missioni-secondarie.md`
- `campagna/rapporti.md`
- `campagna/fazioni.md` (solo se necessario)

Obiettivo: aggiornare sistematicamente tutti i file di contorno sulla base del recap strutturato
(Step 1) e del dm-notes finalizzato (Step 2). Seguire rigorosamente i vincoli dell'Agente 8:
aggiornare solo ciò che è esplicitamente citato nel recap.

---

### Step 5 — Aggiorna luoghi visitati (Agente 7) · `sonnet`

Sub-agente su `ai/agents/07-location-updater.agent.md`.

File da leggere:
- `campagna/sessioni/dm-notes-sessione-[N].md` ← input principale
- `campagna/luoghi-visitati/*.md` ← stato attuale del compendio

Esegui l'intero flusso dell'Agente 7:
1. Estrai luoghi con interazione fisica dalle fasi del dm-notes-N
2. Crea o aggiorna i file markdown in `campagna/luoghi-visitati/`
3. Esegui `npm run build` e verifica output
4. Segnala eventuali errori di build senza procedere al commit

---

### Step 6 — Prepara sessione N+1

Verifica se esiste `campagna/sessioni/dm-notes-sessione-[N+1].md`.

---

#### PERCORSO A — Sessione N+1 già esiste

Se il file esiste, applicagli i delta dalla sessione N appena finalizzata:

**Step 6A.1 — Trasferisci scene non giocate** · sub-agente `sonnet`, con le istruzioni qui sotto nel prompt

Leggi la sezione `### Scene da Trasferire a Sessione N+1` dal dm-notes-N (aggiunta in Step 2).
Per ogni scena elencata:
1. Copia il contenuto verbatim (copialo integralmente, senza riassumere) dal dm-notes-N.
2. Inseriscilo in dm-notes-[N+1].md **all'inizio delle fasi** (prima del contenuto già pianificato),
   rinumerando le fasi esistenti di conseguenza (es. la scena spostata diventa Fase 0 o Fase 1).
3. Aggiorna l'header di dm-notes-[N+1] (Contesto, SETUP INIZIALE) per rispecchiare lo stato
   reale del party dopo sessione N (usando i valori aggiornati da party.md e png-incontrati.md).

**Step 6A.2 — Riverifica hook PG su sessione N+1 (Agente 3)** · `opus`

Sub-agente su `ai/agents/03-session-pc-integrator.agent.md`, su dm-notes-[N+1].md.
Verifica che gli hook PG siano coerenti con la nuova realtà dopo sessione N.

**Step 6A.3 — Aggiorna hook missioni su sessione N+1 (Agente 4)** · `haiku`

Sub-agente su `ai/agents/04-session-missions-integrator.agent.md`, su dm-notes-[N+1].md.
Priorità: missioni cambiate di stato in sessione N (Aggiornato in Step 4).

**Step 6A.4 — Revisione finale sessione N+1 (Agente 6)** · `opus`

Sub-agente su `ai/agents/06-session-reviewer.agent.md`, su dm-notes-[N+1].md.
Output: dm-notes-sessione-[N+1].md finalizzato con Revision Log.

---

#### PERCORSO B — Sessione N+1 non esiste

Se il file NON esiste, crea la sessione da zero con la pipeline completa di prep-sessione,
partendo già con il contesto aggiornato dalla sessione N:

> Nel percorso B ogni sub-agente scrive direttamente in `campagna/sessioni/dm-notes-sessione-[N+1].md`
> (l'Agente 1 lo crea con il chunk grezzo, i successivi lo riscrivono): è il file che passa di mano.

**Step 6B.1 — Estrai chunk narrativo (Agente 1)** · `sonnet`

Sub-agente su `ai/agents/01-session-extractor.agent.md`.
Il marker di avanzamento viene letto dal dm-notes-N finalizzato.

**Step 6B.2 — Traduzione italiana (Agente 2)** · `opus`

Sub-agente su `ai/agents/02-session-translator.agent.md`.

**Step 6B.3 — Integra hook PG (Agente 3)** · `opus`

Sub-agente su `ai/agents/03-session-pc-integrator.agent.md`.

**Step 6B.4 — Integra hook missioni (Agente 4)** · `haiku`

Sub-agente su `ai/agents/04-session-missions-integrator.agent.md`.
I file di contorno aggiornati in Step 4 riflettono già la realtà post-sessione N.

**Step 6B.5 — Uniformazione stile (Agente 2 — re-invoke)** · `opus`

Sub-agente su `ai/agents/02-session-translator.agent.md` per uniformare le sezioni aggiunte
dagli Agenti 3 e 4.

**Step 6B.6 — Revisione finale (Agente 6)** · `opus`

Sub-agente su `ai/agents/06-session-reviewer.agent.md`.
Output: dm-notes-sessione-[N+1].md finalizzato con Revision Log.

**Step 6B.7 — (Condizionale) Aggiornamento PNG nei file PG (Agente 5)** · `sonnet`

Se la sessione N+1 appartiene a un capitolo diverso rispetto al capitolo corrente in
`campagna/contesto.md`, sub-agente su `ai/agents/05-chapter-png-briefer.agent.md`.
Può girare **in parallelo** con lo Step 7: non tocca il dm-notes.

---

### Step 7 — Revisione dei testi da leggere (Agente 9) · `opus`

Vale per **entrambi i percorsi**, ed è l'ultimo step che scrive su dm-notes-[N+1].md.

Sub-agente su `ai/agents/09-read-aloud-reviewer.agent.md`, su dm-notes-[N+1].md.

Obiettivo: ripulire SETUP INIZIALE, riquadri `[BT-xx]`, aggiunte atmosferiche e testi delle
Villain Action dai pattern da AI (contrasti annunciati, spiegazioni del sottotesto, frasi a
effetto, azioni decise per i PG) e trovare segreti, nomi o descrizioni doppie finiti nel testo
letto al tavolo. Serve perché gli step 6A.1 e 6B.2/6B.5 scrivono o spostano testo letto, e
nessuno degli agenti precedenti lo rilegge per come suona.

Se l'Agente 9 segnala un segreto letto ad alta voce o un nome rivelato in anticipo, riportalo
nel riepilogo finale al DM anche se l'ha già corretto.

---

### Step 8 — Git commit

Esegui il commit di tutti i file modificati in questa pipeline:

```
git add campagna/sessioni/ campagna/luoghi-visitati/ campagna/party.md \
        campagna/png-incontrati.md campagna/fazioni.md \
        campagna/missioni-secondarie.md campagna/rapporti.md \
        packs/campagna/
git commit -m "feat: recap e aggiornamento sessione [N] → prep sessione [N+1]"
git push origin main
```

Se scrivi file da PowerShell, usa `[System.IO.File]::WriteAllText($path, $content, [System.Text.UTF8Encoding]::new($false))`
invece di `Set-Content` diretto: `Set-Content` può alterare gli accenti italiani (à, è, ì, ò, ù)
o aggiungere un BOM che Foundry non si aspetta.

---

### Step 9 — Release (con conferma DM)

Mostra il riepilogo di cosa è cambiato e chiedi conferma esplicita prima di procedere:

```
📦 RIEPILOGO RELEASE

File aggiornati questa sessione:
  - dm-notes-sessione-[N].md (finalizzato)
  - dm-notes-sessione-[N+1].md ([aggiornato / creato da zero])
  - party.md, png-incontrati.md, missioni-secondarie.md, rapporti.md
  - [N] file in luoghi-visitati/

Versione corrente in module.json: [versione]

Vuoi procedere con la release? (sì / no)
Se sì: indica la nuova versione (es. v1.2.0) o lascia decidere automaticamente (+patch).
```

Se il DM conferma, esegui la skill `git-release` per il workflow completo di release
(build → bump → tag → GitHub Release).

Se il DM non vuole fare la release ora, concludi con il riepilogo finale.

---

## Riepilogo finale

```
✅ Workflow post-sessione completato — Sessione [N]

Sessione [N]:
  Stato: finalizzato con annotazioni realtà vs piano
  Scene non giocate: [N] → trasferite a sessione [N+1]
  
Sessione [N+1]:
  Stato: [aggiornata con delta / creata da zero]
  Testi da leggere: [N] riquadri corretti su [M] (Agente 9)
  [⚠️ segreti / nomi / doppioni segnalati dall'Agente 9, se ce ne sono]
  
File di contorno aggiornati:
  party.md, png-incontrati.md, missioni-secondarie.md, rapporti.md
  
Luoghi visitati: [N] file aggiornati/creati, pack recompilato
  
TODO DM aperti:
  [lista dei TODO emersi dall'Agente 0 e dall'Agente 8]

Release: [completata vX.Y.Z / rimandata]
```
