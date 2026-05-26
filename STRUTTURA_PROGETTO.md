# 📋 Istruzioni per Riformattare un Progetto D&D basato su una Nuova Campagna

**Contesto:** Questo documento descrive come adattare la struttura del progetto `dragon-heist-dm` a un nuovo progetto D&D basato su una campagna diversa, con la particolarità che:
- Il progetto è nuovo (nessuna sessione ancora giocata)
- I personaggi del party non sono ancora stati definiti
- Non ci saranno missioni secondarie di fazione (struttura semplificata)

---

## 📁 **PARTE 1: Struttura Cartelle**

Crea questa struttura di base:

```
progetto-campagna/
├── .claude/                          # Configurazione Claude Code
│   └── skills/                       # Skills personalizzate (opzionale)
│
├── .github/                          # Template per GitHub (opzionale)
│
├── ai/                               # *** CORE: Tutto ciò che servono agli agenti DM
│   ├── knowledge/                    # Sorgente di verità per il mondo/party
│   │   ├── contesto.md               # *** ESSENZIALE: Metadati campagna, villain, livelli, capitoli
│   │   ├── party.md                  # *** ESSENZIALE: Party (sarà vuoto inizialmente, riempire man mano)
│   │   ├── fazioni.md                # Fazioni rilevanti (SENZA missioni secondarie se non previste)
│   │   ├── png-incontrati.md         # Database PNG: referenti fazioni, alleati, nemici
│   │   ├── rapporti.md               # Tracking relazioni tra PG/PNG/fazioni
│   │   ├── stato-missioni.md         # Tracciamento missioni (se presenti)
│   │   └── recaps/                   # Archivio dei recap sessioni
│   │       ├── recap-sessione-01.md
│   │       └── recap-sessione-02.md (etc)
│   │
│   ├── agents/                       # Descrizioni agenti orchestratori
│   │   ├── AGENTS.md                 # Indice + istruzioni comuni
│   │   ├── instructions.md           # Istruzioni globali per tutti gli agenti
│   │   ├── 00-campaign-setup.agent.md
│   │   ├── 01-session-extractor.agent.md
│   │   ├── 02-session-translator.agent.md
│   │   ├── 03-session-pc-integrator.agent.md
│   │   ├── 04-session-missions-integrator.agent.md (opzionale se no missioni)
│   │   ├── 05-pg-png-updater.agent.md
│   │   ├── 06-session-reviewer.agent.md
│   │   ├── 07-location-updater.agent.md
│   │   └── 08-context-updater.agent.md
│   │
│   └── procedimenti/                 # Guide operative
│       ├── integrazione-mappa-luoghi.md
│       └── ...
│
├── campagna/                         # *** ESSENZIALE: Files giocabili al tavolo
│   ├── sessioni/                     # Note DM compilate per ogni sessione
│   │   ├── dm-notes-sessione-01.md
│   │   ├── dm-notes-sessione-02.md
│   │   └── ...
│   │
│   └── luoghi-visitati/              # Compendio luoghi esplorati (generato da build)
│       ├── 01-locazione-primo.md
│       └── ...
│
├── missioni-secondarie/              # *** OMETTI SE NON PREVISTE
│   ├── fazione-1/
│   │   ├── M1-Titolo.md
│   │   ├── M2-Titolo.md
│   │   └── ...
│   └── fazione-2/
│       └── ...
│
├── fonti/                            # *** SORGENTI GREZZE (di riferimento)
│   └── (Copia qui i materiali originali della campagna: PDF, .txt, .odt, etc)
│
├── src/                              # Codice build e utilities
│   ├── converter.js                  # (Opzionale: converter per formati speciali)
│   └── ...
│
├── packs/                            # *** AUTO-GENERATO: Compendium Foundry VTT (LevelDB)
│   ├── campagna-completa/
│   ├── sessioni/
│   ├── missioni-secondarie/          # (Ometti se no missioni)
│   └── pg-background/
│
├── module.json                       # *** ESSENZIALE: Metadata modulo Foundry
├── package.json                      # Config build + scripts
├── build-foundry.mjs                 # *** Script per generare packs da markdown
│
├── INDEX.md                          # *** Wiki: entry point
├── QUICK_REF.md                      # *** Reference rapido per il tavolo
└── README.md                         # Info generali progetto
```

---

## 📄 **PARTE 2: File di Configurazione Essenziali**

### **A) `ai/knowledge/contesto.md`** (è IL file sorgente di verità)

```markdown
# Contesto Campagna — [NOME CAMPAGNA]

> Questo file contiene tutte le informazioni specifiche della campagna corrente.
> Aggiorna dopo ogni sessione rilevante. Consultato da tutti gli agenti come fonte di verità.

---

## Campagna

- **Avventura:** [Nome Avventura Ufficiale]
- **Villain/Tema:** [Villain principale o tema stagionale]
- **Livello di partenza:** [N]
- **Party:** [N° giocatori] (nomi/ruoli TBD)
- **Stato:** Preparazione — Sessione 1 da pianificare
- **Durata Media Sessioni:** [N] ore
- **Capitolo corrente:** [N]
- **Numero Capitoli Totali:** [N]

---

## Il Party

| Giocatore | Nome PG | Razza / Classe | Fazione | Gancio Personale |
|-----------|---------|---------------|---------|------------------|
| [Nome] | TBD | TBD | TBD | TBD |
| [Nome] | TBD | TBD | TBD | TBD |

---

## Fazioni del Party

### [Fazione 1]
- **Membro:** TBD
- **Referente:** [Nome PNG]
- **Stile operativo:** [Breve descrizione]
- **Obiettivo:** [Goal principale]

---

## Mondo / Lore Essenziale

- **Location principale:** [Città/Regione]
- **Timeline:** [Periodo/Stagione]
- **Governo:** [Tipo]
- **Antagonisti principali:**
  - [Nome] — [Ruolo/Motivazione]
  - [Nome] — [Ruolo/Motivazione]

---

## Note Speciali

[Qualsiasi informazione non standard che gli agenti devono sapere]
```

### **B) `ai/knowledge/party.md`** (Stato party — sarà compilato via via)

```markdown
# Party — [NOME CAMPAGNA]

> Aggiorna dopo ogni sessione o quando un PG subisce cambiamenti rilevanti.

## Stato generale

- **Livello attuale:** [N]
- **Ultima sessione:** [N]
- **Sede base:** TBD

---

## Personaggi

### [Nome PG]
**Giocatore:** [Nome]
**Razza / Classe:** —
**Background:** —
**Fazione:** —

| | |
|--|--|
| **Livello** | — |
| **PF attuali** | — |
| **Condizioni** | — |

#### Gancio personale principale
TBD

#### PNG collegati
- TBD

---

[Ripeti per ogni PG]
```

### **C) `ai/knowledge/fazioni.md`** (Senza missioni secondarie se non previste)

```markdown
# Fazioni — [NOME CAMPAGNA]

> Aggiorna dopo ogni sessione rilevante.
> **Posizioni:** Ostile · Diffidente · Neutrale · Amichevole · Alleata

---

## Fazioni Rilevanti

### [Fazione 1]

| Campo | Valore |
|-------|--------|
| **Posizione verso il party** | Neutrale |
| **PNG di contatto** | TBD |
| **Membro nel party** | TBD |
| **Sede operativa** | TBD |

**Stile operativo:** [Descrizione breve]

**Tensioni interne:** [Nessuna / Descrizione]

---

[Ripeti per ogni fazione]
```

### **D) `ai/knowledge/png-incontrati.md`** (Database PNG)

```markdown
# PNG Incontrati — [NOME CAMPAGNA]

> Archivio di tutti i PNG: referenti fazioni, alleati, nemici, neutrali.
> Aggiorna quando un PG incontra un nuovo PNG importante.

---

## Referenti Fazioni

### [Nome PNG]
- **Ruolo:** [Es. "Referente Force Grey"]
- **Affidabilità:** [Trustworthy / Manipolatore / Equilibrato / etc]
- **Primo incontro:** [Sessione N]
- **Note:** [Comportamento, preferenze, segreti noti]

---

## PNG Chiave (Non-Fazioni)

### [Nome PNG]
- **Ruolo:** [Es. "Taverna keeper / Informatore / etc"]
- **Relazione col party:** [Amichevole / Neutrale / Ostile]
- **Primo incontro:** [Sessione N]
- **Note:** [Comportamento, segreti noti]

---

[Aggiungi via via man mano che il party incontra PNG]
```

### **E) `ai/knowledge/rapporti.md`** (Relazioni)

```markdown
# Rapporti — [NOME CAMPAGNA]

> Tracking delle relazioni esplicite tra PG, PNG, fazioni, e mondo.

---

## PG ↔ PNG

| PG | PNG | Relazione | Note |
|----|-----|-----------|-------|
| [PG] | [PNG] | Alleato / Nemico / Neutrale | Breve spiegazione |

---

## PG ↔ Fazioni

| PG | Fazione | Status | Missioni Ricevute |
|----|---------|--------|-------------------|
| [PG] | [Fazione] | Membro / Alleato / Spia | M1: …, M2: … |

---

## PNG ↔ PNG

| PNG | PNG | Relazione | Note |
|-----|-----|-----------|-------|
| [A] | [B] | Rivale / Alleato / Sconosciuto | Breve spiegazione |

---

[Aggiorna man mano]
```

---

## 📋 **PARTE 3: File di Configurazione Foundry**

### **A) `module.json`** (Metadata modulo Foundry)

```json
{
  "id": "campagna-code",
  "title": "[NOME CAMPAGNA] — DM Notes",
  "description": "Note DM e sorgenti per la campagna [NOME].",
  "version": "0.1.0",
  "compatibility": {
    "minimum": "12",
    "verified": "14"
  },
  "authors": [
    {
      "name": "[TUO NOME]",
      "flags": {}
    }
  ],
  "packs": [
    {
      "name": "campagna-completa",
      "label": "[NOME] — Sorgente Completa",
      "path": "./packs/campagna-completa",
      "type": "JournalEntry",
      "ownership": {
        "PLAYER": "NONE",
        "ASSISTANT": "OWNER"
      }
    },
    {
      "name": "sessioni",
      "label": "Sessioni",
      "path": "./packs/sessioni",
      "type": "JournalEntry",
      "ownership": {
        "PLAYER": "NONE",
        "ASSISTANT": "OWNER"
      }
    },
    {
      "name": "pg-background",
      "label": "Background PG",
      "path": "./packs/pg-background",
      "type": "JournalEntry",
      "ownership": {
        "PLAYER": "NONE",
        "ASSISTANT": "OWNER"
      }
    },
    {
      "name": "luoghi-visitati",
      "label": "Luoghi Visitati",
      "path": "./packs/luoghi-visitati",
      "type": "JournalEntry",
      "ownership": {
        "PLAYER": "NONE",
        "ASSISTANT": "OWNER"
      }
    }
  ],
  "url": "https://github.com/[USERNAME]/[REPO]",
  "manifest": "https://raw.githubusercontent.com/[USERNAME]/[REPO]/master/module.json",
  "download": "https://github.com/[USERNAME]/[REPO]/releases/download/[VERSION]/[REPO]-v[VERSION].zip"
}
```

**Note:** Se NON hai missioni secondarie, ometti il pack `missioni-secondarie`.

### **B) `package.json`**

```json
{
  "name": "campagna-dm-builder",
  "version": "0.1.0",
  "description": "Build script per generare Compendium Packs Foundry VTT da file Markdown",
  "type": "module",
  "private": true,
  "scripts": {
    "build": "node build-foundry.mjs",
    "ai-validate": "node scripts/validate-prompts.mjs",
    "ai-load": "node scripts/load-prompts.mjs"
  },
  "dependencies": {
    "marked": "^14.0.0"
  },
  "devDependencies": {
    "@foundryvtt/foundryvtt-cli": "^3.0.3"
  }
}
```

### **C) `build-foundry.mjs`** (Script di build)

Copia il file da `dragon-heist-dm/build-foundry.mjs` e adatta i path/nomi pack. Il file è autorappellante: legge tutti i `.md` nelle cartelle configurate e genera i packs LevelDB.

---

## 📝 **PARTE 4: File Wiki**

### **A) `INDEX.md`** (Entry point wiki)

Template:

```markdown
# 🗺️ [NOME CAMPAGNA] — Wiki Centralizzata

**Campagna:** [Nome] | **Villain:** [Nome] | **Livello Partenza:** [N]  
**Stato:** [Preparazione / In corso]

---

## 📌 Accesso Rapido

| **Categorie** | **Link** |
|---|---|
| **Party & Personaggi** | [👥 Party](ai/knowledge/party.md) • [🎭 PNG Incontrati](ai/knowledge/png-incontrati.md) |
| **Fazioni** | [⚔️ Fazioni](ai/knowledge/fazioni.md) • [📊 Rapporti](ai/knowledge/rapporti.md) |
| **Lore & Mondo** | [🌆 Lore Principale](fonti/) • [⚙️ Quick Reference](QUICK_REF.md) |
| **Sessioni** | [📓 Note Sessioni](campagna/sessioni/) |

---

## 👥 Party (TBD)

[Inserisci tabella party man mano che definisci i PG]

---

## 🌆 Mondo Principale

- **Location:** [Città/Regione]
- **Governo:** [Tipo]
- **Villain(s):** [Antagonisti]

---

## 📊 Quick Reference

[Link a QUICK_REF.md]

---

## 📓 Sessioni

[Lista sessioni man mano]

---

## 🔀 Come Usare Questa Wiki

1. **Navigazione:** Clicca sui link per esplorare
2. **Ricerca:** Ctrl+F per cercare pagina; Ctrl+Shift+F per full-text
3. **Aggiorna:** Dopo ogni sessione, aggiorna `party.md`, `rapporti.md`, `contesto.md`

---

**Ultima modifica:** [Data]  
**Versione Wiki:** 0.1 (setup iniziale)
```

### **B) `QUICK_REF.md`** (Reference al tavolo)

```markdown
# ⚙️ Quick Reference — [NOME CAMPAGNA]

Tabelle veloci per il tavolo:

## 📋 PNG Chiave & Ruoli

| Nome | Ruolo | Fazione | First Appearance |
|------|-------|---------|------------------|
| [Nome] | [Ruolo] | [Fazione] | [Sessione] |

## 🎯 Tiri Frequenti

[CD comuni, skill test ricorrenti]

## 📅 Timeline Principale

[Eventi importanti, scadenze in-game]

## 💰 Ricompense

[XP per livello, gold, items speciali]

---

[Aggiorna man mano necessario]
```

---

## ⚙️ **PARTE 5: Setup Iniziale**

1. **Copia i file di base** (da `dragon-heist-dm`):
   - `build-foundry.mjs` (script di build)
   - `ai/agents/` (template agenti, adatta solo nomi/reference)
   - `src/` (utils di build, se necessari)

2. **Crea i file di knowledge** (`ai/knowledge/`):
   - `contesto.md` — Riempi con dati nuova campagna
   - `party.md` — Lascia vuoto per ora (il DM riempie man mano)
   - `fazioni.md` — Elenca fazioni rilevanti (senza M1/M2/M3/M4 se no missioni)
   - `png-incontrati.md` — Inizia vuoto
   - `rapporti.md` — Inizia vuoto
   - `stato-missioni.md` — (Ometti se no missioni)

3. **Crea struttura cartelle**:
   - `campagna/sessioni/`
   - `campagna/luoghi-visitati/`
   - `fonti/` (copia sorgenti originali)

4. **Configura build**:
   - Adatta `module.json` (id, title, authors, packs da includere)
   - Copia `build-foundry.mjs` e adatta path packs
   - Copia `package.json`

5. **Crea wiki entry point**:
   - `INDEX.md`
   - `QUICK_REF.md`

6. **Installa dipendenze**:
   ```bash
   npm install
   npm run build
   ```

---

## 🤖 **PARTE 6: Adattamento Agenti**

Gli agenti definiti in `ai/agents/*.agent.md` sono il core della pipeline. Per una campagna SENZA missioni secondarie:

- **Mantieni:** Agenti 0-3, 5-6, 7-8 (tutti funzionano senza missioni secondarie)
- **Salta o Adatta:** Agente 04 (session-missions-integrator) — se non hai missioni, o riduci al minimo

Ogni agente legge da `ai/knowledge/` e genera output specifico. Non vanno modificati se non hai esigenze speciali.

---

## 📌 **PARTE 7: Workflow Tipico per il DM**

Dopo ogni sessione giocata:

1. **Recap informale** → passa a Claude Code via chat
2. **Skill `/aggiorna-sessione N`** → pipeline orchestrata automaticamente:
   - Estrae info rilevanti dal recap
   - Traduce in struttura standard
   - Aggiorna `party.md`, `rapporti.md`, `contesto.md`
   - Compila `dm-notes-sessione-N.md` pronto per tavolo
   - Aggiorna locations visitate
   - (Salta missioni se N/A)

3. **Review & QA** → DM verifica i file generati
4. **Commit & Push** → Git workflow

---

## ✅ **Checklist Setup Nuovo Progetto**

- [ ] Struttura cartelle creata
- [ ] File `ai/knowledge/*.md` compilati (almeno `contesto.md` completo)
- [ ] `module.json` adattato
- [ ] `package.json` copiato
- [ ] `build-foundry.mjs` copiato e adattato
- [ ] `INDEX.md` e `QUICK_REF.md` creati
- [ ] `npm install && npm run build` eseguito senza errori
- [ ] Git repository inizializzato e primo commit fatto
- [ ] Agenti testati con `/prep-sessione 1`

---

**Fine. Questo documento è self-contained e può essere passato a un'altra istanza di Claude Code per riprodurre la struttura con una nuova campagna.**
