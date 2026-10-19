---
name: prep-sessione
description: >
  Orchestratore della pipeline di preparazione sessione per la campagna D&D Shadow of the Dragon Queen.
  Usa questa skill ogni volta che il DM vuole preparare una nuova sessione di gioco, anche se
  scrive semplicemente "/prep-sessione" o "prepara la sessione" o "prossima sessione". Esegue
  in sequenza gli agenti 1 → 2 → 3 → revisione finale (6 + 9).
  Produce il file dm-notes-sessione-NN.md pronto per il tavolo.
---

# Pipeline Preparazione Sessione — /prep-sessione

Sei l'orchestratore della pipeline DM per Shadow of the Dragon Queen. Il tuo compito è guidare
la preparazione di una sessione eseguendo in sequenza gli agenti di `ai/agents/`.

**Il prodotto è uno solo:** `campagna/sessioni/dm-notes-sessione-NN.md`, l'unico file che il DM
legge (decisione del DM, 2026-10-19). Nessuno step crea altri file.

**Prima di iniziare:** se il numero della sessione target non è stato specificato, chiedi al DM.
Il numero è il più alto tra i file `campagna/sessioni/dm-notes-sessione-NN.md` + 1: le sessioni
speciali `dm-notes-sessione-NNbis.md` non contano (vedi «Sessioni Speciali» in `ai/agents/AGENTS.md`).
Per preparare una sessione speciale il DM indica la NN dopo cui si gioca, e l'Agente 1 estrae il
chunk che il DM sceglie invece di partire dal marker di avanzamento.

---

## Come si lancia un agente

Ogni step va eseguito da un **sub-agente** (tool `Agent`, `subagent_type: general-purpose`) con il
modello indicato accanto allo step. Tu orchestri, gli agenti lavorano.

Il prompt di ogni sub-agente è autosufficiente: numero della sessione NN, file dell'agente da
eseguire, file di input e di output, e la richiesta di restituire al massimo 15 righe (file
modificati, TODO DM, anomalie), senza fare commit.

**Il file che passa di mano è `campagna/sessioni/dm-notes-sessione-NN.md`:** l'Agente 1 lo crea
con il chunk grezzo, ogni agente successivo lo legge e lo riscrive. Aspetta la notifica di
completamento prima di lanciare lo step dopo.

---

## Pipeline (esegui nell'ordine)

Tra uno step e il successivo, mostra: `✅ Step N completato → avvio Step N+1...`

### Step 1 — Estrazione chunk narrativo · `sonnet`
Sub-agente su `ai/agents/01-session-extractor.agent.md`.

Input: ultimo `dm-notes-sessione-XX.md` (per il marker di avanzamento) + `fonti/campagna/`
Output: documento grezzo con chunk EN, testi boxed marcati `[BOXED TEXT — ID: BT-XX]`, indice encounter.

### Step 2 — Traduzione e stile italiano · `opus`
Sub-agente su `ai/agents/02-session-translator.agent.md`.

Input: output Step 1
Output: draft IT con testi boxed tradotti, un riquadro solo per scena: un eventuale dettaglio in più sta dentro il riquadro, mai in un blockquote `*[aggiunta atmosferica]*` separato.
Tutte le informazioni dell'originale devono essere presenti — nessun dettaglio può essere omesso.

### Step 3 — Integrazione personaggi giocanti · `opus`
Sub-agente su `ai/agents/03-session-pc-integrator.agent.md`.

Input: draft IT da Step 2
File da leggere: `campagna/party.md`, `campagna/png-incontrati.md`, `campagna/contesto.md`,
`fonti/personaggi/*.md`
Output: draft con hook PG, scene spotlight opzionali, note DM riservate, atteggiamenti PNG aggiornati.
Le parti aggiunte vanno scritte già nello stile dell'Agente 2: non c'è un secondo giro di traduzione.

### Step 4 — Revisione finale · `opus`
Un solo sub-agente che esegue, in quest'ordine, `ai/agents/06-session-reviewer.agent.md` e
`ai/agents/09-read-aloud-reviewer.agent.md` su `dm-notes-sessione-NN.md`.

Input: draft da Step 3 + ultimo `dm-notes-sessione-XX.md` giocato. Applica direttamente le
correzioni e genera la sezione `🔍 REVISION LOG`. Poi ripulisce SETUP INIZIALE, riquadri
`[BT-xx]` e testi delle Villain Action dai pattern da AI, e segnala segreti, nomi o descrizioni
doppie finiti nel testo letto al tavolo: riporta queste segnalazioni nel riepilogo finale al DM.

---

## Riepilogo finale

```
✅ Pipeline completata — Sessione NN

File prodotto: campagna/sessioni/dm-notes-sessione-NN.md
Testi da leggere: [N] riquadri corretti su [M]
[⚠️ segreti / nomi / doppioni segnalati, se ce ne sono]

Prossimi step manuali:
1. Leggi e approva dm-notes-sessione-NN.md
2. /git-release  (per pubblicare l'aggiornamento su Foundry)
```
