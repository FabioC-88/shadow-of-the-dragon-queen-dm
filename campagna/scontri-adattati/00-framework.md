# Framework — Adattamento Scontri (Fase 1)

Regole del tavolo valide per **tutti** i capitoli in `campagna/scontri-adattati/`, decise con Fabio e da non ridiscutere a ogni capitolo (se cambiano, si aggiorna solo qui).

## Perché adattiamo

- **2024 vs 2014:** i PG con le regole 2024 (talento d'origine dal 1° livello, Weapon Mastery, spellcasting più generoso) sono più forti del baseline con cui *Shadow of the Dragon Queen* è stato scritto.
- **5 giocatori, non 4:** più turni a round per il party = l'azione di un boss solitario "si perde" contro 5 iniziative. Il problema è l'economia delle azioni, non (solo) il CR dei nemici.

## Fonte del framework

[fonti/Flee, Mortals! (MCDM)](../../fonti/Flee,%20Mortals!.md) — usato per il CR cap e per il design dei boss. Il budget degli scontri si **verifica in XP con la DMG 2024** (punto 5): con i gruppi numerosi di CR basso la somma dei CR di *Flee, Mortals!* è risultata più morbida, non più severa (S05, vedi punto 5). Riferimenti citati come "azioni da Villain" ecc. sono terminologia di design, non testo riprodotto dal libro: le voci/i numeri specifici per questa campagna sono scritti da zero.

## Regole opzionali collegate

[campagna/regole-opzionali.md](../regole-opzionali.md) — critici massimizzati, esaurimento su cura da 0 PF, riposo lungo limitato ai Dadi Vita, Lingering Injuries al posto della morte per danno massiccio. Attive per tutta la campagna da qui in avanti; la sezione "Letalità target" qui sotto presume queste regole accese.

## Regole fisse

1. **Budget CR per scontro:** tabella *Flee, Mortals!* "Encounter CR per Character" (per livello medio del party), moltiplicata ×5 (numero di PG). Il "CR cap" per livello non va superato per singole creature. Il totale si verifica poi in XP con la DMG 2024 (punto 5), che ha l'ultima parola.
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
5. **Letalità target — budget in XP della DMG 2024** *(decisione del DM, 2026-10-19, dopo la S05: sostituisce la «fascia bassa» di prima)*. Ogni scontro si verifica sommando gli XP dei mostri (nessun moltiplicatore per il numero) contro la tabella qui sotto, già moltiplicata per 5 PG:

   | Livello | Bassa | Moderata | Alta |
   |:--:|--:|--:|--:|
   | 3 | 750 | 1.125 | 2.000 |
   | 4 | 1.250 | 1.875 | 2.500 |
   | 5 | 2.500 | 3.750 | 5.500 |
   | 6 | 3.000 | 5.000 | 7.000 |
   | 7 | 3.750 | 6.500 | 8.500 |
   | 8 | 5.000 | 8.500 | 10.500 |
   | 9 | 6.500 | 10.000 | 13.000 |
   | 10 | 8.000 | 11.500 | 15.500 |
   | 11 | 9.500 | 14.500 | 20.500 |

   - **Scontri che contano** (picco della sessione, boss, missioni con premio): **Alta**, fino a circa 1,25 × Alta se il party ci arriva riposato.
   - **Scontri di passaggio:** **Moderata**.
   - **Bassa** solo per riempitivi e incontri casuali.

   **Perché è cambiata.** Alla prova del tavolo (S05, 2026-10-18) il posto di vedetta (1.000 XP al 4° livello, sotto la Bassa) è finito in pochi round con il party quasi illeso, e alla fattoria *ragnatela* e *crescita di spine* hanno tolto di mezzo metà degli hobgoblin al primo round. La somma dei CR conta dieci hobgoblin come CR 5, ma con 11 PF a testa li ferma un solo incantesimo ad area. Le regole opzionali (critici massimizzati, riposo lungo che rende solo i Dadi Vita) restano attive, ma **non sono più un motivo per scendere sotto il target**: pesano sulla giornata, non sul singolo scontro. Dopo ogni sessione reale si verifica di nuovo e si corregge (marcato `[TODO DM: verificare]` dove il numero è a giudizio).
6. **I nemici giocano per vincere** *(decisione del DM, 2026-10-19: «i nemici hanno sempre poche opzioni, tanti PF ma pochi danni e pochi CC»)*. Le schede DSotDQ sono scritte con le regole 2014: un attacco, nessuna Bonus Action né Reaction, quasi nessun effetto sul colpo. Per compensare, in ogni scontro che conta:
   - **Ogni capo ha Bonus Action e Reaction.** Ufficiali, bozak, capitani, sergenti: anche se non sono minacce nominate, prendono il trattamento «minore» del punto 3 (una Bonus Action e una Reaction fisse, nate dalla loro natura).
   - **Rinforzi a ondate.** Almeno un terzo del budget entra al 2°-3° round, da un'altra direzione: il controllo d'apertura dei PG colpisce solo la prima ondata.
   - **Bersagli intelligenti.** Chi ha armi a distanza tira a chi mantiene la concentrazione; dopo il primo incantesimo ad area i gruppi si allargano; chi scopre un terreno pericoloso si ferma e tira invece di attraversarlo.
   - **PF allineati al riferimento 2024 del CR** (tabella «Allineamento ai numeri 2024», in fondo) e **effetti sul colpo automatici** dove il 2024 li farebbe tali (Prono, Afferrato, spinta). Il CR e gli XP restano quelli ufficiali.
   - **Il morale è una valvola, non la regola.** La resa o la fuga «a metà gruppo» si usa solo se il tavolo è davvero in difficoltà.
7. **Villain Parties (capitolo 3 del libro):** 7 squadre da 5 villain, ciascuna calibrata per **5 PG** a un livello preciso (3°, 5°, 7°, 9°, 11°, 13°, 15°). **Amethyst Knife** (11°) coincide col livello finale del Cap. 7 — candidata a fare da scheletro meccanico per Kansaldi + luogotenenti, da valutare quando arriveremo lì.

## Cosa NON cambia

- Narrativa, PNG, dialoghi, hook dei `dm-notes-sessione-NN.md` restano la fonte di riferimento — questi documenti toccano solo blocchi statistici e regole d'incontro.
- Nessuna mappa/tattica su griglia (gestita da Foundry).

## Stato per capitolo

| Capitolo | File | Stato |
|---|---|---|
| 1 | — | Escluso (solo background, nessun combattimento) |
| 2 | [capitolo-02.md](capitolo-02.md) | Fatto (nessun boss — solo il preludio "Scaglie di Guerra (*Scales of War*)") |
| 3 — Quando Brucia la Casa (*When Home Burns*) | [capitolo-03.md](capitolo-03.md) | Fatto (ricontrollato: nessun Minion reale da convertire, letalità e Villain Actions Gholcag verificate) |
| 4 — L'Ombra della Guerra (*Shadow of War*) | [capitolo-04.md](capitolo-04.md) | Fatto (ricontrollato: 12 Goblin + Soldato dell'Armata dei Draghi (*Dragon Army Soldier*) convertiti da Minion, letalità e Villain Actions Caradoc/Sarlamir verificate — due echi strutturali con Gholcag segnalati, non riscritti. Lord Soth resta non affrontabile in combattimento diretto qui) |
| 5 — Terre Desolate del Nord | [capitolo-05.md](capitolo-05.md) | Fatto (boss: Virruza, Akhviri come contingenza — nessuno stat block ufficiale in fonte, tutto ricostruito, `[TODO DM: verificare]` diffuso) |
| 6 — Città dei Nomi Perduti | [capitolo-06.md](capitolo-06.md) | Fatto (boss: Belephaion — Lohezet trattamento minore, no Villain Actions) |
| 7 — Assedio di Kalaman (*Siege of Kalaman*) | [capitolo-07.md](capitolo-07.md) | Fatto (intero capitolo, Sessioni 25-28 — boss: Kansaldi Fire-Eyes/Ignia + Lord Soth contingenza, basati sulle ricostruzioni già in dm-notes-sessione-27/28.md; resto del capitolo trattamento minore/standard) |

---

## ⚠️ Schede ufficiali applicate il 2026-09-13 — i CR sono cambiati

Fabio ha fornito gli stat block ufficiali (MM'25 e DSotDQ). Erano tutti ricostruzioni dichiarate, e in diversi casi il CR reale è **diverso** da quello su cui erano stati calcolati i budget degli scontri. Questa tabella è la ragione per cui alcuni incontri dei capitoli 4-7 vanno ricontrollati.

| Creatura | CR usato prima | CR ufficiale | Effetto sul budget |
|---|---|---|---|
| **Soldato dell'Armata dei Draghi** (p200) | CR 1/4 (50 XP) — e CR 1/8 in S13 | **CR 1 (200 XP)** | ⬆️ **×4-8.** AC 17, 22 PF, due attacchi con +1d4 fuoco. Gli incontri con 8 soldati sono un'altra cosa |
| **Sivak Draconian** (p199) | CR 2 (450 XP) | **CR 4 (1.100 XP)** | ⬆️ **×2,4.** Ed è **Grande** con **Volo 18 m**, 57 PF, 3 attacchi/round |
| **Ufficiale dell'Armata dei Draghi** (p200) | CR 1 in S13, CR 3 altrove | **CR 3 (700 XP)** | ⬆️ solo in S13. AC 19, portata 3 m, Ordini d'Assalto |
| **Kapak Draconian** (p198) | CR 2 in Cap. 4 e 7 | **CR 3 (700 XP)** | ⬆️ e il Multiattacco può **paralizzare** |
| **Bozak Draconian** (p198) | CR 3 (700 XP) | **CR 2 (450 XP)** | ⬇️ e le Spasmi di Morte (*Death Throes*) fanno 2d8 **forza** CD 10, non 4d6 fuoco CD 13 |
| **Dragonnel dell'Armata dei Draghi** (p201) | CR 4 (1.100 XP) | **CR 3 (700 XP)** | ⬇️ |
| **Baaz Draconian** (p197) | CR 1 in S05/S06/Cap. 4 | **CR 1/2 (100 XP)** | ⬇️ **metà**, e picchia molto meno (2× Spada corta 1d6+1) |
| **Aurak Draconian** (p196) | CR 6 | **CR 6 (2.300 XP)** | = ma capacità **completamente diverse** |
| **Guard** (MM'25 p162) | Crossbow + Shortsword | CR 1/8, **solo Lancia** | = come peso, diverso come tattica |
| **Warhorse** (MM'25 p373) | Hooves 2d6+4 + carica con TS | **2d4+4**, carica dentro l'attacco | ⬇️ leggermente |
| **Boilerdrak** (p189) | Costrutto 50 PF, cono 9 m, 4d6 | **Oggetto 100 PF, cono 18 m, 5d10, CD 15** | ⬆️ **molto** |

**Regola pratica:** dove il CR è salito, **riduci il numero di nemici** invece di indebolire il blocco; dove è sceso, **aumentalo**. I blocchi sono quelli veri; si scala con le quantità, come già fatto per il quinto giocatore, e dal 2026-10-20 si allineano solo i PF, gli effetti automatici e le Bonus Action/Reaction dei capi (sezione «Allineamento ai numeri 2024», in fondo).

**Capitoli da ricontrollare prima di giocarli:** 4 (posto di vedetta e forte: baaz ⬇️, kapak ⬆️, sivak ⬆️), 5, 6 e 7 (sivak e soldati ⬆️ in modo sostanziale). I Capitoli 2 e 3 — Sessioni 00, 01 e 02 — sono a posto: usano baaz, guardia (*guard*), warhorse, kapak e boilerdrak già verificati.

---

## Allineamento ai numeri 2024 (decisione del DM, 2026-10-20)

La campagna ha pochi combattimenti e deve essere difficile: quelli che ci sono devono essere seri. Le schede DSotDQ nascono con le regole 2014, quindi le si confronta con i mostri 2024 dello stesso CR e si allinea ciò che resta indietro. **Il CR e gli XP ufficiali non cambiano mai:** restano il «costo» dello scontro nel budget del punto 5, perché alzare il CR vorrebbe dire incontrare meno mostri e lasciare la difficoltà dov'era.

**Come si è deciso.** Confronto fra l'SRD 5.1 e l'SRD 5.2 (dnd5eapi.co, 279 mostri accoppiati per nome, senza quelli con azioni leggendarie): **in nessuna coppia il CR è cambiato.** Mediane per CR:

| CR | PF | CA | Danno a round | CD mediana |
|:--:|--:|--:|--:|--:|
| 1/4 | 13 | 12 | 6 | 10-11 |
| 1/2 | 22 | 12 | 8 | 11 |
| 1 | 26 | 12 | 10 | 11 |
| 2 | 48 | 13 | 16 | 12 |
| 3 | 65 | 14 | 24 | 12 |
| 4 | 91 | 12 | 26 | 13 |
| 5 | 105 | 15 | 34 | 14 |
| 6-8 | 126 | 16 | 44 | 14 |
| 9-12 | 178 | 17 | 66 | 17 |

Nel passaggio 5.1 → 5.2 **PF, CA, bonus di attacco, CD e bonus ai tiri salvezza dei mostri sono rimasti uguali** (mediane invariate, differenze entro ±0,3 sui TS). Sono cambiati: il **danno a round dal CR 3 in su** (circa ×1,4-1,7 al CR 3-4), la presenza di **Bonus Action** (da 0% a circa 15-65% dei mostri, secondo il CR) e, soprattutto, gli **effetti automatici**: dei 69 mostri fino al CR 5 con «TS o condizione» nel 2014, 27 hanno la condizione senza tiro salvezza nel 2024 (il lupo crudele non fa più il TS Forza CD 13: il Prono scatta sul colpo, se il bersaglio è Grande o più piccolo).

**Regole.**
1. **PF:** se la scheda è sotto la mediana del suo CR, sale alla mediana; se è sopra, resta. Mai al ribasso. **I dadi vita si aggiornano insieme ai PF:** la formula (con il modificatore di COS della scheda, invariato) deve dare il totale scritto. Se nessuna formula cade esattamente sulla mediana, si prende la più vicina per eccesso.
2. **CA, danno, CD e TS non si toccano:** le schede DSotDQ sono già in linea o sopra (il sivak fa 34 a round contro una mediana 2024 di 26). Alzare le CD non è supportato dal confronto.
3. **Effetti automatici:** un effetto «TS o Prono/Afferrato» da colpo, che nel 2024 sarebbe automatico, lo diventa. Paralisi, Spaventato e simili restano a tiro salvezza.
4. **Capi:** una Bonus Action e una Reaction fisse (punto 6).

**Applicazione (PF prima → dopo, CR/XP invariati):**

| Creatura | CR | PF | Altro |
|---|:--:|---|---|
| Baaz Draconian | 1/2 | 22 (già alla mediana) | — |
| Dragon Army Soldier | 1 | 22 → **27** (5d8+5) | — |
| Bozak Draconian | 2 | 40 → **49** (11d8) | BA e Reaction già scritte (guado, 05bis) |
| Kapak Draconian | 3 | 39 → **65** (10d8+20) | BA e Reaction nuove (guado, 05bis) |
| Dragon Army Officer | 3 | 65 (10d8+20, già alla mediana) | BA e Reaction già scritte |
| Dragon Army Dragonnel | 3 | 58 → **65** (10d10+10) | cavalcatura, non un capo |
| Sivak Draconian | 4 | 57 → **95** (10d10+40) | coda: Prono automatico, senza TS; BA e Reaction già scritte |
| Hobgoblin Warrior | 1/2 | 11 (scheda MM 2024) | — |

Applicato alle sezioni Sessione 05 (kapak), 05bis e 06 di [capitolo-04.md](capitolo-04.md) e ai dm-notes 05bis e 06. **I blocchi dei capitoli 5-7 e dei dm-notes successivi si allineano quando si prepara quella sessione.** Alla fattoria della 05bis, con il combattimento in corso su Foundry, i PF già assegnati ai nemici in campo restano com'erano.

**Limiti.** L'SRD 5.2 non è tutto il Monster Manual 2024, il campione è di 20-40 mostri per CR e il danno a round è un calcolo grezzo (attacco migliore × numero di attacchi). I PF più alti allungano gli scontri e la difficoltà cresce: `[TODO DM: verificare dopo la sessione reale]`, e se serve si ricontrolla il budget del punto 5.
