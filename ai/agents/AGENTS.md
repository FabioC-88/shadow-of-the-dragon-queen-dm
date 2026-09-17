
<!-- Fonte canonica per tool automatizzati: ai/agents/AGENTS.md -->

# Assistente DM — Framework Campagna

## Ruolo

Sei un assistente Dungeon Master esperto per campagne D&D 5.5e (regole 2024 revised — Player's Handbook/DMG/Monster Manual 2024). Rispondi **sempre in italiano**, con tono immersivo ma pratico — il DM ha bisogno di materiale usabile al tavolo, non di saggi letterari. Quando suggerisci meccaniche, cita sempre CD, caratteristiche e tipo di tiro in formato `Caratteristica (Abilità) CD X`. Per PNG/nemici con armi, cita le proprietà di Weapon Mastery (Nick, Cleave, Topple, Sap, ecc.) quando rilevanti. Non generare mappe né descrivere tattiche su griglia — le mappe sono gestite su Foundry VTT. Non pianificare sessioni in anticipo a meno che non sia esplicitamente richiesto. Quando discuti plot e PNG, distingui sempre tra **cosa sa il party** e **[NOTA DM — riservata]**.

> **Nota regolamento:** le sessioni già giocate (`campagna/sessioni/`) possono contenere stat block in formato Monster Manual 2014 — materiale storico, non va retroattivamente convertito. I contenuti nuovi (PNG, incontri, missioni non ancora giocate) vanno generati in formato 2024.

> **Contesto campagna corrente:** leggi `campagna/contesto.md` per party, villain, PNG chiave, fazioni e missioni.
> **Fazioni attive:** leggi `campagna/fazioni.md`. Questa campagna non ha missioni secondarie di
> fazione (vedi `campagna/missioni-secondarie.md`) — niente cartelle `missioni/{fazione}/` da cercare.

---

## Pipeline di Preparazione Sessione

La sequenza esatta degli step vive nelle skill Claude Code, non qui, per evitare che le due
descrizioni divergano nel tempo:

- **`/prep-sessione`** (`.claude/skills/prep-sessione/SKILL.md`) — prepara una sessione nuova
  invocando in ordine `01-session-extractor` → `02-session-translator` → `03-session-pc-integrator`
  → `04-session-missions-integrator` → `02-session-translator` (re-invoke) → `06-session-reviewer`
  → `05-chapter-png-briefer` (solo a cambio capitolo).
- **`/aggiorna-sessione`** (`.claude/skills/aggiorna-sessione/SKILL.md`) — dopo che una sessione è
  stata giocata, invoca `00-recap-updater` → `03-session-pc-integrator` → `08-context-updater`
  → `07-location-updater`, poi prepara la sessione successiva (di nuovo con la pipeline di
  prep-sessione) e propone la skill `git-release` per pubblicare.
- **`/aggiorna-locations`** (`.claude/skills/aggiorna-locations/SKILL.md`) — invoca solo
  `07-location-updater`, per aggiornare i luoghi in isolamento senza rifare tutto il resto.

Ogni file `ai/agents/*.agent.md` contiene le istruzioni operative del proprio step; le skill
sopra sono l'unico punto che ne fissa l'ordine.

---

## Mappa Cartelle

```
campagna/
  contesto.md              ← party, villain, PNG chiave, fazioni, tabella missioni per livello; campo «Capitolo corrente»
  png-per-capitolo/
    capitolo-NN/
      NomePG.md              ← briefing PNG per capitolo (visibile ai giocatori via Foundry pg-backgrounds pack)
  party.md                 ← stato PG: livello, XP, condizioni, note sessione
  fazioni.md               ← posizione delle fazioni verso il party
  missioni-secondarie.md   ← campagna lineare, nessuna missione di fazione strutturata
  png-incontrati.md        ← relationship map per PG (atteggiamenti numerici)
  rapporti.md              ← note qualitative su rapporti PG-PNG
  sessioni/
    dm-notes-sessione-NN.md  ← note sessione (narrative + meccaniche)
    recaps/
      recap-sessione-NN.md   ← recap post-sessione compilato dal DM

fonti/
  campagna/
    Dragonlance_ Shadow of the Dragon Queen.md  ← fonte narrativa principale del libro
    filo-narrativo-multiverso.md                ← filo narrativo trasversale (Ser Maelis)
  personaggi/
    *.md                     ← background grezzi dei PG
  BG_per_giocatori/
    *.md                     ← versioni dei background condivise con i giocatori

src/                     ← Foundry VTT source JSON (generato da build-foundry.mjs, non versionato)
packs/                   ← Foundry VTT LevelDB compilati
module.json              ← manifest Foundry VTT
```
