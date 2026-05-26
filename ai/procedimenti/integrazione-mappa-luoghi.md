# Procedimento: Integrazione Mappa Luoghi in Foundry VTT

Questa guida spiega come creare mappe interattive in Foundry VTT per le location della campagna **Dragonlance: Shadow of the Dragon Queen**, con pin che linkano direttamente ai **Luoghi Visitati** del compendio.

---

## Obiettivo

Creare Scene (mappe) delle location principali della campagna con pin posizionati sui punti chiave. Ogni pin è un Journal Note che collega a una pagina specifica del compendio "Luoghi Visitati".

**Location principali supportate:**
- Vogler (Cap 3)
- Kalaman città (Cap 4)
- Northern Wastes (Cap 5)
- City of Lost Names / Onyari (Cap 6)

---

## Prerequisiti

- Foundry VTT con modulo `shadow-of-the-dragon-queen-dm` attivato nel mondo
- Immagini delle mappe (vedi Appendice E del libro; mappa Kalaman-Northern Wastes e mappa Ansalon)
- Compendio "Luoghi Visitati" compilato (generato da `npm run build`)

---

## Step 1: Preparare le Mappe

### Opzione A — Mappe Ufficiali DSotDQ (Consigliato)

Il libro include due mappe in Appendice E:
- **Map 12.01:** Kalaman & Northern Wastes (con versione player)
- **Map 12.02:** Il continente di Ansalon (con versione player)

Usa le versioni "Player Version" per le Scene visibili ai giocatori.

### Opzione B — Mappe Alternative

Se non hai le mappe ufficiali:
- **D&D Beyond:** Asset mappa Dragonlance (se disponibile)
- **Cartography Exchange / Reddit r/dndmaps:** Mappe fan di Kalaman
- **Homebrew:** Crea mappe custom usando Inkarnate o similar

---

## Step 2: Creare le Scene in Foundry

1. Apri il tuo mondo Foundry con il modulo attivato
2. Vai in **Scenes** → **Create Scene**
3. Configura:
   - **Name:** `Kalaman — Mappa Città` (o nome location)
   - **Background:** carica l'immagine mappa
   - **Grid Type:** Gridless (le mappe di questo libro non usano griglia standard)
   - **Visibility:** decidi se visibile ai giocatori subito o solo quando raggiungono la location

---

## Step 3: Aggiungere Note/Pin

1. Nella Scene, attiva il layer **Journal Notes** (icona libro)
2. Clicca **Create Note** e posiziona il pin sulla mappa
3. Per ogni pin, configura:
   - **Journal Entry:** collega alla entry corrispondente nel compendio "Luoghi Visitati"
   - **Icon:** usa un'icona appropriata (castello per fortezze, tenda per accampamenti, ecc.)
   - **Label:** nome del luogo in italiano

### Location Chiave — Kalaman

| Location | Tipo | Entry Compendio |
|----------|------|-----------------|
| Castle Kalaman | Fortezza | luoghi-visitati/castle-kalaman.md |
| Harbor Beacons | Fari | luoghi-visitati/harbor-beacons.md |
| Wyhan's Apothecary | Negozio | luoghi-visitati/wyhan-apothecary.md |
| The Steady Beacon | Taverna | luoghi-visitati/steady-beacon.md |
| Trade Gate | Porta | luoghi-visitati/trade-gate.md |

### Location Chiave — Vogler

| Location | Tipo | Entry Compendio |
|----------|------|-----------------|
| Brass Crab | Locanda | luoghi-visitati/brass-crab.md |
| Village Circle | Piazza | luoghi-visitati/village-circle.md |
| Thornwall Keep | Fortezza | luoghi-visitati/thornwall-keep.md |
| Vogler's Crossing | Traghetto | luoghi-visitati/voglers-crossing.md |

---

## Step 4: Collegare al Compendio

Ogni file in `campagna/luoghi-visitati/` viene compilato nel pack `campagna` del modulo tramite `npm run build`.

Per aggiungere un luogo al compendio:
1. Crea il file `campagna/luoghi-visitati/nome-luogo.md` con il formato standard
2. Esegui `npm run build` per ricompilare i packs
3. In Foundry: **Compendium** → cerca il pack "Note Campagna" → importa nel mondo

---

## Step 5: Organizzare le Scene per Capitolo

Crea Scene separate per ogni area principale visitata. Struttura consigliata:

```
Scene: Ansalon — Worldmap (mappa poster, sempre disponibile)
Scene: Vogler (Cap 3)
Scene: Kalaman — Vista Città (Cap 4)
Scene: Kalaman — Castle Kalaman (Cap 4)
Scene: Northern Wastes — Overview (Cap 5)
Scene: City of Lost Names — Rovine (Cap 6)
Scene: Flying Citadel — Layout (Cap 7)
```

---

## Note Aggiuntive

- Le mappe ufficiali del libro (App. E) includono versioni player-safe (senza annotazioni DM)
- La mappa poster di Ansalon è ottima come worldmap di campagna
- Per il Northern Wastes, il libro usa un sistema di location labels (A, B, C...) — tieni questa struttura nelle note dei pin
- La Flying Citadel non ha una mappa nel libro; il DM può creare una mappa custom al momento del Cap 7
- Le immagini nel file .md sorgente sono in formato webp (path `img/adventure/DSotDQ/...`) — non sono disponibili nel repository senza il materiale digitale originale

---

> Aggiorna questo file quando aggiungi nuove Scene o cambi la struttura del compendio.
