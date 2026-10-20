---
name: aggiorna-sessione
description: >
  Workflow post-sessione. Il DM ha appena giocato la sessione N e fornisce un recap in forma
  libera nel prompt. La skill annota dm-notes-sessione-N con quello che è successo, aggiorna la
  memoria degli agenti (party, PNG, contesto), porta le novità nella sessione dopo (o la crea se
  non esiste), la rilegge una volta e chiede conferma per la release.
  Uso: "/aggiorna-sessione N" dove N è il numero della sessione APPENA GIOCATA.
  Alias: "abbiamo giocato la sessione N", "recap della sessione N", "aggiorna dopo sessione N".
---

# Workflow Post-Sessione — /aggiorna-sessione

Sei l'orchestratore del flusso post-sessione. Il DM ha appena giocato la sessione **N** e ti
ha dato un recap, in qualsiasi forma. La realtà giocata ha sempre la precedenza sul piano.

**Il DM legge solo le dm-notes delle sessioni** (decisione del DM, 2026-10-19). Ogni step
scrive o nelle dm-notes o nei tre file di memoria che gli agenti leggono (`campagna/party.md`,
`campagna/png-incontrati.md`, `campagna/contesto.md`), e in nient'altro. Niente file di recap
separati, niente luoghi visitati, niente aggiornamenti di `rapporti.md`,
`missioni-secondarie.md` o `fazioni.md`: restano nel repo come archivio.

---

## Step 0 — Prerequisiti

1. **N:** dal comando (`/aggiorna-sessione 4`), altrimenti chiedi al DM quale sessione ha giocato.
2. **dm-notes:** deve esistere `campagna/sessioni/dm-notes-sessione-[N].md`; se manca, fermati
   e avvisa il DM.
3. **Recap:** deve essere nel prompt. Se manca, chiedilo al DM (va bene in forma libera). Se è
   troppo vago su un punto che cambia la sessione dopo (es. dove si è fermata la serata, il
   livello del party), chiedi solo quello; il resto diventa `[TODO DM]`.
4. **Sessione dopo** (vedi «Sessioni Speciali» in `ai/agents/AGENTS.md`): di norma è la N+1.
   Se N è una NNbis, la successiva è la NN+1. Se N è normale ed esiste la sua NNbis, chiedi al DM
   se la prossima serata è la speciale. Chiamiamo **S** la sessione scelta.

```
📋 Sessione [N] identificata — prossima serata: [S]
Avvio pipeline post-sessione...
```

---

## Come si lancia un agente

Ogni step è un **sub-agente** (tool `Agent`, `subagent_type: general-purpose`) con il modello
indicato. Tu orchestri, gli agenti lavorano, e si passano il lavoro attraverso i file su disco.

Il prompt di ogni sub-agente è autosufficiente, perché parte senza il contesto della chat:

```
Sessione giocata: N. Prossima serata: S.
Leggi CLAUDE.md, poi leggi ed esegui ai/agents/<file>.agent.md.
File di input: <elenco>. File da modificare: <elenco>.
[Recap del DM incollato per intero, con le precisazioni date in chat.]
Scrivi i risultati direttamente sui file. Non fare commit.
Restituisci al massimo 15 righe: file modificati, TODO DM aperti, anomalie.
```

Tra uno step e il successivo mostra: `✅ Step N completato → avvio Step N+1...`

---

## Pipeline

### Step 1 — Annota la sessione giocata · `sonnet`

Sub-agente su `ai/agents/00-recap-updater.agent.md`.
Input: recap del DM. Modifica solo `campagna/sessioni/dm-notes-sessione-[N].md`: marcatori
✅/⏸️/🔀 sulle fasi e sezione finale `📋 ACCADUTO IN SESSIONE`, con le scene da trasferire a S.

### Step 2 e Step 3 — in parallelo

Leggono entrambi la sezione `📋 ACCADUTO IN SESSIONE` scritta allo Step 1 e toccano file
diversi: lanciali nello stesso messaggio e aspetta entrambe le notifiche prima dello Step 4.

**Step 2 — Aggiorna la memoria · `sonnet`**

Sub-agente su `ai/agents/08-context-updater.agent.md`. Modifica solo `campagna/party.md`,
`campagna/png-incontrati.md` e `campagna/contesto.md`.

**Step 3 — Porta le novità nella sessione S · `opus`**

- **Se `dm-notes-sessione-[S].md` esiste:** un sub-agente, con queste istruzioni nel prompt.
  1. Copia **integralmente** (senza riassumere) le scene elencate in «Scene da trasferire» del
     dm-notes-N e mettile all'inizio delle fasi di S, rinumerando.
  2. Aggiorna intestazione, Nota pre-sessione e SETUP INIZIALE di S con lo stato reale dopo N:
     livello, XP, dove si trova il party, chi è vivo, cosa sa.
  3. Correggi in S solo ciò che i delta di N invalidano (atteggiamenti dei PNG, hook dei PG,
     prerequisiti delle scene, thread). Per gli hook segui le regole di
     `ai/agents/03-session-pc-integrator.agent.md`, senza aggiungerne di nuovi.
  4. Se la serata si è fermata a metà scena (es. a metà combattimento), apri S con una sezione
     `🎬 RIPRESA` che dica cosa riaprire su Foundry e rimetta il tavolo nella scena.
- **Se non esiste:** esegui `/prep-sessione` per S (`.claude/skills/prep-sessione/SKILL.md`),
  passando all'Agente 1 il dm-notes-N annotato come punto di partenza.

### Step 4 — Revisione finale della sessione S · `opus`

Un solo sub-agente che esegue, in quest'ordine, `ai/agents/06-session-reviewer.agent.md` e
`ai/agents/09-read-aloud-reviewer.agent.md` su `dm-notes-sessione-[S].md`: coerenza, continuità e
incontri (numero corretto di nemici, niente stat block né note di bilanciamento), poi i testi da
leggere al tavolo. È l'ultimo step che scrive su S.

Se segnala un segreto letto ad alta voce o un nome rivelato in anticipo, riportalo al DM nel
riepilogo finale anche se l'ha già corretto.

### Step 5 — Commit (lo fai tu)

Committa solo i file di contenuto, mai `module.json` né `packs/`: build, versione e pack li
gestisce la CI al momento della release. Se un `npm run build` locale li ha toccati, riportali
com'erano con `git checkout -- module.json packs`.

```
git add campagna/ ai/ .claude/
git commit -m "docs: sessione [N] giocata → prep sessione [S]"
git push origin main
```

### Step 6 — Release (con conferma del DM)

```
📦 RIEPILOGO RELEASE

Aggiornati: dm-notes-sessione-[N].md (giocata), dm-notes-sessione-[S].md, memoria (party, PNG, contesto)
Versione corrente in module.json: [versione]

Vuoi pubblicare su Foundry? (sì / no — e la versione, oppure +patch automatico)
```

Se il DM conferma, esegui la skill `git-release`. Altrimenti chiudi con il riepilogo.

---

## Riepilogo finale

```
✅ Post-sessione completato — Sessione [N]

Sessione [N]: annotata (✅/⏸️/🔀), [N] scene trasferite a [S]
Sessione [S]: [aggiornata / creata da zero], rivista
[⚠️ segreti / nomi / doppioni segnalati dalla revisione, se ce ne sono]

TODO DM aperti:
  [lista, solo fatti di trama: niente su build, equipaggiamento o scelte dei PG]

Release: [completata vX.Y.Z / rimandata]
```
