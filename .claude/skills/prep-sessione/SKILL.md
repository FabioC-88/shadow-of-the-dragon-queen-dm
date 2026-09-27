---
name: prep-sessione
description: >
  Orchestratore della pipeline completa di preparazione sessione per la campagna D&D Shadow of the Dragon Queen.
  Usa questa skill ogni volta che il DM vuole preparare una nuova sessione di gioco, anche se
  scrive semplicemente "/prep-sessione" o "prepara la sessione" o "prossima sessione". Esegue
  in sequenza gli agenti 1→2→3→4→2→6→9 e opzionalmente 5 (chapter-png-briefer a cambio capitolo).
  Produce il file dm-notes-sessione-NN.md pronto per il tavolo.
---

# Pipeline Preparazione Sessione — /prep-sessione

Sei l'orchestratore della pipeline DM per Shadow of the Dragon Queen. Il tuo compito è guidare la preparazione
di una sessione completa eseguendo in sequenza tutti gli agenti definiti in `ai/agents/`.

**Prima di iniziare:** se il numero della sessione target non è stato specificato, chiedi al DM.
Il numero si trova contando i file in `campagna/sessioni/dm-notes-sessione-*.md` + 1.

---

## Come si lancia un agente

Ogni step va eseguito da un **sub-agente** (tool `Agent`, `subagent_type: general-purpose`) con il
**modello scritto nel campo `model:` del frontmatter** del file `ai/agents/*.agent.md`
(indicato anche accanto a ogni step qui sotto). Tu orchestri, gli agenti lavorano. Le ragioni
delle scelte di modello sono nella tabella di `.claude/skills/aggiorna-sessione/SKILL.md`.

Il prompt di ogni sub-agente è autosufficiente: numero della sessione NN, file dell'agente da
eseguire, file di input e di output, e la richiesta di restituire al massimo 15 righe (file
modificati, TODO DM, anomalie), senza fare commit.

**Il file che passa di mano è `campagna/sessioni/dm-notes-sessione-NN.md`:** l'Agente 1 lo crea
con il chunk grezzo, ogni agente successivo lo legge e lo riscrive. Aspetta la notifica di
completamento prima di lanciare lo step dopo.

---

## Pipeline (esegui nell'ordine)

Tra uno step e il successivo, mostra un breve messaggio di avanzamento:
`✅ Agente N completato → avvio Agente N+1...`

### Step 1 — Estrazione chunk narrativo · `sonnet`
Sub-agente su `ai/agents/01-session-extractor.agent.md`.

Input: ultimo `dm-notes-sessione-XX.md` (per il marker di avanzamento) + `fonti/campagna/`
Output: documento grezzo con chunk EN, testi boxed marcati `[BOXED TEXT — ID: BT-XX]`, indice encounter.

### Step 2 — Traduzione e stile italiano · `opus`
Sub-agente su `ai/agents/02-session-translator.agent.md`.

Input: output Step 1
Output: draft IT con testi boxed tradotti. Aggiunte atmosferiche (facoltative, brevi) in blockquote separati `*[aggiunta atmosferica]*`.
Tutte le informazioni dell'originale devono essere presenti — nessun dettaglio può essere omesso.

### Step 3 — Integrazione personaggi giocanti · `opus`
Sub-agente su `ai/agents/03-session-pc-integrator.agent.md`.

Input: draft IT da Step 2
File da leggere: `campagna/party.md`, `campagna/png-incontrati.md`, `campagna/rapporti.md`,
`campagna/fazioni.md`, `campagna/contesto.md`, `fonti/personaggi/*.md`
Output: draft con hook PG, scene spotlight opzionali, note DM riservate, atteggiamenti PNG aggiornati.

### Step 4 — Integrazione missioni fazioni · `haiku`
Sub-agente su `ai/agents/04-session-missions-integrator.agent.md`.

Input: draft da Step 3
File da leggere: `campagna/missioni-secondarie.md`, `campagna/fazioni.md` (per `folder_path` e `fonti_path`),
file missioni nelle cartelle indicate da `fazioni.md`.
Output: draft con max 2-3 hook missione inseriti nei momenti di respiro narrativo. Tabella thread narrativi.

### Step 5 — Uniformazione stile (seconda invocazione Agente 2) · `opus`
Sub-agente, di nuovo su `ai/agents/02-session-translator.agent.md`.

Questa volta il tuo ruolo è solo uniformare lo stile italiano sulle parti aggiunte dagli Agenti 3 e 4.
Non stravolgere le integrazioni — solo correggi calchi linguistici e incongruenze di registro.

### Step 6 — Revisione finale · `opus`
Sub-agente su `ai/agents/06-session-reviewer.agent.md`.

Input: draft quasi-finale da Step 5 + ultimo `dm-notes-sessione-XX.md` giocato
Applica direttamente le correzioni (non solo segnalarle). Genera Revision Log.
Output: `dm-notes-sessione-NN.md` finalizzato con sezione `🔍 REVISION LOG — Agente 6`.

### Step 6.5 — Aggiornamento PNG nei file PG (condizionale) · `sonnet`
Leggi `campagna/contesto.md` e controlla il campo `Capitolo corrente`.
Controlla il capitolo della sessione appena preparata.

**Solo se il capitolo della sessione > Capitolo corrente:** sub-agente su
`ai/agents/05-chapter-png-briefer.agent.md`.
Output: file `campagna/png-per-capitolo/capitolo-NN/NomePG.md` creati per ogni PG con almeno 1 PNG noto.
Aggiorna `campagna/contesto.md` con il nuovo capitolo corrente.

Non tocca il dm-notes: lancialo **in parallelo** con lo Step 7.

Se il capitolo non è cambiato: stampa `⏭ Step 6.5 saltato (nessuna transizione di capitolo)`.

### Step 7 — Revisione dei testi da leggere · `opus`
Sub-agente su `ai/agents/09-read-aloud-reviewer.agent.md`, su `dm-notes-sessione-NN.md`.

È l'ultimo step che scrive sul dm-notes. Ripulisce SETUP INIZIALE, riquadri `[BT-xx]`, aggiunte
atmosferiche e testi delle Villain Action dai pattern da AI, e segnala segreti, nomi o
descrizioni doppie finiti nel testo letto al tavolo. Riporta queste segnalazioni nel riepilogo
finale al DM.

---

## Riepilogo finale

Al termine di tutta la pipeline, stampa:

```
✅ Pipeline completata — Sessione NN

File prodotti:
- campagna/sessioni/dm-notes-sessione-NN.md
[- campagna/png-per-capitolo/capitolo-NN/NomePG.md  ← file PNG per capitolo, solo se Step 6.5 attivo]

Testi da leggere: [N] riquadri corretti su [M] (Agente 9)
[⚠️ segreti / nomi / doppioni segnalati dall'Agente 9, se ce ne sono]

Prossimi step manuali:
1. Leggi e approva dm-notes-sessione-NN.md
2. /aggiorna-locations NN  (dopo aver giocato la sessione)
3. /git-release  (per pubblicare l'aggiornamento su Foundry)
```
