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
