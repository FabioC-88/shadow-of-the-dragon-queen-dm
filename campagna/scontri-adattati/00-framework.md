# Framework — Adattamento Scontri (Fase 1)

Regole del tavolo valide per **tutti** i capitoli in `campagna/scontri-adattati/`, decise con Fabio e da non ridiscutere a ogni capitolo (se cambiano, si aggiorna solo qui).

## Perché adattiamo

- **2024 vs 2014:** i PG con le regole 2024 (talento d'origine dal 1° livello, Weapon Mastery, spellcasting più generoso) sono più forti del baseline con cui *Shadow of the Dragon Queen* è stato scritto.
- **5 giocatori, non 4:** più turni a round per il party = l'azione di un boss solitario "si perde" contro 5 iniziative. Il problema è l'economia delle azioni, non (solo) il CR dei nemici.

## Fonte del framework

[fonti/Flee, Mortals! (MCDM)](../../fonti/Flee,%20Mortals!.md) — usato per la matematica degli incontri (più severa della DMG 2024 core) e per il design dei boss. Riferimenti citati come "azioni da Villain" ecc. sono terminologia di design, non testo riprodotto dal libro: le voci/i numeri specifici per questa campagna sono scritti da zero.

## Regole opzionali collegate

[campagna/regole-opzionali.md](../regole-opzionali.md) — critici massimizzati, esaurimento su cura da 0 PF, riposo lungo limitato ai Dadi Vita, Lingering Injuries al posto della morte per danno massiccio. Attive per tutta la campagna da qui in avanti; la sezione "Letalità target" qui sotto presume queste regole accese.

## Regole fisse

1. **Budget CR per scontro:** tabella *Flee, Mortals!* "Encounter CR per Character" (per livello medio del party), moltiplicata ×5 (numero di PG). Il "CR cap" per livello non va superato per singole creature.
2. **Niente regola Minion — gruppi numerosi restano stat block classici, di qualunque dimensione.** *(Rimossa su richiesta di Fabio — usata solo nella Sessione 04 del Cap. 4, ora riconvertita, vedi ricontrollo capitolo-04.md.)* Per gestire i gruppi in fretta al tavolo: creature con lo stesso blocco statistico condividono l'iniziativa (una sola iniziativa di gruppo) — nessuna semplificazione di danno o PF, solo dei turni.
3. **Non tutti i nemici nominati sono Action-Oriented — due livelli, non uno:**
   - **Minaccia nominata ma minore** (es. Gragonis — boss di una singola scena, non il climax del capitolo): solo una **Bonus Action** e una **Reaction** fisse, per non farla morire al primo round contro 5 iniziative. Niente Villain Actions, niente testo boxed dedicato — basta il testo d'ingresso già presente nei dm-notes.
   - **Boss veramente serio o di fine capitolo** (es. Fewmaster Gholcag, e più avanti Virruza, Akhviri, Belephaion, Kansaldi Fire-Eyes, Lord Soth — non Lohezet, che resta un incontro sociale): trattamento pieno Action-Oriented — Bonus Action, Reaction, e 3 **Villain Actions** (Opener / Control / Ultimate, una per round dopo il turno di un nemico, ciascuna usabile una sola volta a combattimento). Il CR aumenta solo se il budget lo richiede — la priorità resta l'economia delle azioni, non HP/danno gonfiati.
   - **Come si decide il livello:** chiediti "è il motivo per cui questa sessione/capitolo esiste, o è un ostacolo lungo la strada verso quel motivo?". Solo il primo caso merita le Villain Actions.

   **Ogni Villain Action ha un breve testo da leggere ai giocatori** (stile "Testo" dei dm-notes, con `[Aggiunta atmosferica]` dove serve) per marcare il momento — non è solo meccanica, è la scena che dice "questo nemico non è come gli altri". Scrivilo **umano/mostruoso, non da IA**: gesti fisici concreti, dettagli sensoriali, niente costruzioni a contrasto tipo "non è X, è Y" — meglio una frase secca o un'immagine fisica (Gholcag che si lecca il grasso dalle dita) che una frase "poetica" generica. Il peso del testo scala con l'importanza narrativa del villain:
   - **Boss di capitolo** (es. Fewmaster Gholcag): testo + Aggiunta atmosferica, che lega l'azione al tema della sessione.
   - **Nemesi ricorrente/finale** (Lord Soth, Kansaldi Fire-Eyes): testo più lungo ed evocativo, coerente con il peso che hanno nella campagna — qui vale la pena investire più cura.

   **Non riciclare lo stesso schema tra villain diversi.** Le tre Villain Actions di ogni boss devono nascere dalla sua natura specifica (Gholcag comanda una macchina d'assedio ed è famelica; Lord Soth è soprannaturale e non ha bisogno di "chiamare rinforzi"), non essere "apertura=rinforzi, controllo=area+prono, ultimate=colpo+HP temporanei" copiato e incollato con nomi diversi — quel rischio è già emerso una volta, va controllato ogni volta prima di consegnare un capitolo.
4. **Lingua dei documenti:** mostri, stat block, nomi di azioni/abilità (Actions, Bonus Action, Reaction, Villain Actions, Multiattack, nomi delle creature) sempre in **inglese** — è la terminologia meccanica ufficiale, tradurla introduce solo ambiguità. **Tutto ciò che va letto ad alta voce ai giocatori resta in italiano** (testo delle Villain Actions, boxed text). Prosa/commentario da DM (perché abbiamo adattato, note tattiche, tabelle riepilogo) resta italiano.
5. **Letalità target:** Deadly/Hard scalato su 5 PG, ma calibrato tenendo conto delle regole opzionali attive ([regole-opzionali.md](../regole-opzionali.md)) — critici massimizzati e riposo lungo che non guarisce più automaticamente alzano la letalità reale ben oltre quanto dice il budget CR nudo. Di conseguenza: **preferire la fascia bassa** di Hard/Deadly piuttosto che il tetto massimo, specialmente per scontri con più ondate o senza possibilità di riposo tra un incontro e l'altro. Verificare dopo ogni sessione reale e correggere PF/CD dei boss se serve (marcato `[TODO DM: verificare]` dove il numero è puramente a giudizio).
6. **Villain Parties (capitolo 3 del libro):** 7 squadre da 5 villain, ciascuna calibrata per **5 PG** a un livello preciso (3°, 5°, 7°, 9°, 11°, 13°, 15°). **Amethyst Knife** (11°) coincide col livello finale del Cap. 7 — candidata a fare da scheletro meccanico per Kansaldi + luogotenenti, da valutare quando arriveremo lì.

## Cosa NON cambia

- Narrativa, PNG, dialoghi, hook dei `dm-notes-sessione-NN.md` restano la fonte di riferimento — questi documenti toccano solo blocchi statistici e regole d'incontro.
- Nessuna mappa/tattica su griglia (gestita da Foundry).

## Stato per capitolo

| Capitolo | File | Stato |
|---|---|---|
| 1 | — | Escluso (solo background, nessun combattimento) |
| 2 | [capitolo-02.md](capitolo-02.md) | Fatto (nessun boss — solo il preludio "Scales of War") |
| 3 — When Home Burns | [capitolo-03.md](capitolo-03.md) | Fatto (ricontrollato: nessun Minion reale da convertire, letalità e Villain Actions Gholcag verificate) |
| 4 — Shadow of War | [capitolo-04.md](capitolo-04.md) | Fatto (ricontrollato: 12 Goblin + Dragon Army Soldier convertiti da Minion, letalità e Villain Actions Caradoc/Sarlamir verificate — due echi strutturali con Gholcag segnalati, non riscritti. Lord Soth resta non affrontabile in combattimento diretto qui) |
| 5 — The Northern Wastes | [capitolo-05.md](capitolo-05.md) | Fatto (boss: Virruza, Akhviri come contingenza — nessuno stat block ufficiale in fonte, tutto ricostruito, `[TODO DM: verificare]` diffuso) |
| 6 — City of Lost Names | [capitolo-06.md](capitolo-06.md) | Fatto (boss: Belephaion — Lohezet trattamento minore, no Villain Actions) |
| 7 — Siege of Kalaman | [capitolo-07.md](capitolo-07.md) | Fatto (intero capitolo, Sessioni 25-28 — boss: Kansaldi Fire-Eyes/Ignia + Lord Soth contingenza, basati sulle ricostruzioni già in dm-notes-sessione-27/28.md; resto del capitolo trattamento minore/standard) |

---

## ⚠️ Schede ufficiali applicate il 2026-09-13 — i CR sono cambiati

Fabio ha fornito gli stat block ufficiali (MM'25 e DSotDQ). Erano tutti ricostruzioni dichiarate, e in diversi casi il CR reale è **diverso** da quello su cui erano stati calcolati i budget degli scontri. Questa tabella è la ragione per cui alcuni incontri dei capitoli 4-7 vanno ricontrollati.

| Creatura | CR usato prima | CR ufficiale | Effetto sul budget |
|---|---|---|---|
| **Dragon Army Soldier** (p200) | CR 1/4 (50 XP) — e CR 1/8 in S13 | **CR 1 (200 XP)** | ⬆️ **×4-8.** AC 17, 22 PF, due attacchi con +1d4 fuoco. Gli incontri con 8 soldati sono un'altra cosa |
| **Sivak Draconian** (p199) | CR 2 (450 XP) | **CR 4 (1.100 XP)** | ⬆️ **×2,4.** Ed è **Grande** con **Volo 18 m**, 57 PF, 3 attacchi/round |
| **Ufficiale del Dragon Army** (p200) | CR 1 in S13, CR 3 altrove | **CR 3 (700 XP)** | ⬆️ solo in S13. AC 19, portata 3 m, Ordini d'Assalto |
| **Kapak Draconian** (p198) | CR 2 in Cap. 4 e 7 | **CR 3 (700 XP)** | ⬆️ e il Multiattacco può **paralizzare** |
| **Bozak Draconian** (p198) | CR 3 (700 XP) | **CR 2 (450 XP)** | ⬇️ e le Death Throes fanno 2d8 **forza** CD 10, non 4d6 fuoco CD 13 |
| **Dragonnel del Dragon Army** (p201) | CR 4 (1.100 XP) | **CR 3 (700 XP)** | ⬇️ |
| **Baaz Draconian** (p197) | CR 1 in S05/S06/Cap. 4 | **CR 1/2 (100 XP)** | ⬇️ **metà**, e picchia molto meno (2× Spada corta 1d6+1) |
| **Aurak Draconian** (p196) | CR 6 | **CR 6 (2.300 XP)** | = ma capacità **completamente diverse** |
| **Guard** (MM'25 p162) | Crossbow + Shortsword | CR 1/8, **solo Lancia** | = come peso, diverso come tattica |
| **Warhorse** (MM'25 p373) | Hooves 2d6+4 + carica con TS | **2d4+4**, carica dentro l'attacco | ⬇️ leggermente |
| **Boilerdrak** (p189) | Costrutto 50 PF, cono 9 m, 4d6 | **Oggetto 100 PF, cono 18 m, 5d10, CD 15** | ⬆️ **molto** |

**Regola pratica:** dove il CR è salito, **riduci il numero di nemici** invece di indebolire il blocco; dove è sceso, **aumentalo**. I blocchi ora sono quelli veri e non vanno più toccati — si scala con le quantità, come già fatto per il quinto giocatore.

**Capitoli da ricontrollare prima di giocarli:** 4 (posto di vedetta e forte: baaz ⬇️, kapak ⬆️, sivak ⬆️), 5, 6 e 7 (sivak e soldati ⬆️ in modo sostanziale). I Capitoli 2 e 3 — Sessioni 00, 01 e 02 — sono a posto: usano baaz, guard, warhorse, kapak e boilerdrak già verificati.
