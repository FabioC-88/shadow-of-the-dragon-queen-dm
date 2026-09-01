# Map: Adattamento campagna a 5 PG + regole opzionali brutali

## Destinazione

`campagna/scontri-adattati/` completo per tutta la campagna giocabile (Cap. 2, 3, 4, 5, 6, 7 — Cap.1 escluso, solo background), più un nuovo documento `campagna/regole-opzionali.md` con le 4 regole brutali, e `00-framework.md` aggiornato di conseguenza.

Fatto = ogni capitolo ha i suoi incontri ricalcolati per 5 PG senza regola Minion, i boss selezionati hanno le loro Villain Actions scritte, e le regole opzionali sono documentate e referenziate. Nessuna sessione è mai stata giocata realmente (vedi `campagna/party.md`, note Sessione 28), quindi nessun vincolo di materiale storico blocca la modifica di qualunque capitolo — ma i `campagna/sessioni/dm-notes-sessione-NN.md` restano la fonte narrativa di riferimento e non vanno toccati, solo i blocchi statistici.

## Notes

- **Override "plan, don't do":** questa mappa produce direttamente i deliverable (file di gioco), non solo decisioni — ogni ticket "task" scrive/modifica i file reali del repo.
- Dominio: D&D 5.5e (regole 2024), campagna Dragonlance "Shadow of the Dragon Queen", 5 PG invece dei 4 assunti dal manuale.
- Fonte matematica/design: `fonti/Flee, Mortals! (MCDM)` — terminologia di design ("Villain Actions", "Minion", "Villain Party"), non testo riprodotto dal libro: numeri e voci scritti da zero per questa campagna.
- Stile di scrittura per ogni ticket che produce Villain Actions o testo da leggere ai giocatori: seguire lo stile già stabilito in `capitolo-03.md`/`capitolo-04.md` — testo umano/mostruoso, non da IA; niente costruzioni a contrasto tipo "non è X, è Y"; non riciclare lo stesso schema tra villain diversi (apertura=rinforzi/controllo=area+prono/ultimate=colpo+HP temp copiato con nomi diversi è già successo una volta, ricontrollare ogni volta).
- Lingua: mostri/stat block/nomi azioni (Actions, Bonus Action, Reaction, Villain Actions, Multiattack) sempre in inglese; testo da leggere ad alta voce ai giocatori e prosa/commentario DM sempre in italiano.
- Cosa NON cambia: narrativa, PNG, dialoghi, hook dei `dm-notes-sessione-NN.md` restano la fonte di riferimento; nessuna mappa/tattica su griglia (gestita da Foundry).

### Regole fisse decise (valgono per ogni ticket)

- **Party:** 5 PG, non 4.
- **Minion:** regola rimossa del tutto — gruppi numerosi restano stat block classici, gestiti con iniziativa condivisa per creature con lo stesso blocco statistico.
- **Critici massimizzati:** simmetrico, vale per PG e mostri. Formula esatta da fissare nel ticket "Scrivere regole-opzionali.md" (esempio grezzo dato da Fabio: dado di danno portato al massimo invece di raddoppiato — va chiarito live col DM in quel ticket).
- **Esaurimento su cura da 0 PF:** si applica ogni volta che un PG viene curato dopo essere sceso a 0 PF (anche più volte a sessione), esaurimento 2024 cumulativo (-1 ai tiri, -3m velocità per livello, morte al 6° livello), nessun tetto.
- **Riposo lungo:** niente Gritty Realism. Variante 2014: si recupera il 100% dei Dadi Vita (non solo metà come da regola standard); durante il riposo lungo ogni giocatore sceglie quanti Dadi Vita spendere (tiro dado+COS, come un riposo breve) e quanti tenerne di riserva. Niente guarigione automatica dei PF con il riposo lungo.
- **Lingering Injuries:** al posto della morte per danno massiccio (quando i danni in eccesso oltre lo 0 superano i PF massimi del PG). Tabella ufficiale DMG 2014 come base meccanica, narrazione della singola voce riscritta in stile Dragonlance quando applicata a un PG specifico. Guaribili solo con magia dedicata di alto livello (Rigenerare o simile) — non guariscono con il tempo o il passaggio di capitolo.
- **`regole-opzionali.md`:** file unico, sintesi "in parole povere" per i giocatori in cima + dettaglio meccanico sotto per il DM. Referenziato da `00-framework.md`.

### Boss per capitolo (Villain Actions — Opener/Control/Ultimate, dove previste)

- **Cap. 2:** nessun boss (preludio fuggevole "Scales of War", 1 kapak + 4 baaz draconian, party livello 1).
- **Cap. 3:** Fewmaster Gholcag — già scritto (`capitolo-03.md`, "Fatto"), da rivedere nel ricontrollo.
- **Cap. 4:** Caradoc, Knight Sarlamir — già scritti (`capitolo-04.md`, "Fatto"), da rivedere nel ricontrollo. Lord Soth appare ma resta non affrontabile in questo capitolo.
- **Cap. 5:** **Virruza** (draconico mutato in slaad verde + red slaad con tadpole, dungeon Sunward Fortress/D5) e **Akhviri** (drago nero, scritto in fonte per essere evitato/si fugge, ma con Villain Actions di contingenza nel caso il party attacchi comunque) — nessun altro boss nel capitolo (è un capitolo di viaggio/hub, non ha un climax combattivo proprio).
- **Cap. 6:** **Belephaion** (drago blu travestito da prete, "fights to the death", boss vero) — **Lohezet** resta incontro sociale/persuasione: solo trattamento "minaccia nominata ma minore" (Bonus Action + Reaction fisse) se la sua imboscata opzionale scatta, niente Villain Actions.
- **Cap. 7:** **Kansaldi Fire-Eyes** (+ drago alleato Ignia) — final boss di campagna, "Amethyst Knife" (Flee, Mortals!, cap.3 del libro) utilizzabile come scheletro meccanico (5 boss umanoidi custom, non legati a creature specifiche del Manuale dei Mostri). **Lord Soth** ottiene Villain Actions di contingenza per il suo scontro finale, nel caso il party scelga di affrontarlo invece di seguire la via narrativa prevista — verificare l'esatta collocazione nel capitolo durante il ticket.

## Decisions so far

- [Scrivere regole-opzionali.md](issues/01-regole-opzionali.md): fatto — critici = dado tirato una volta + valore massimo come bonus fisso (simmetrico); esaurimento 2024 -2/livello su cura da 0 PF, ogni volta; riposo lungo = 100% Dadi Vita, guarigione a scelta del giocatore; Lingering Injuries su tabella DMG 2014, guaribili solo con magia alta. File in `campagna/regole-opzionali.md`.
- [Aggiornare 00-framework.md](issues/02-aggiorna-framework.md): fatto — Minion rimosso (iniziativa condivisa per tutti i gruppi), rimando a `regole-opzionali.md` aggiunto, Letalità target rivista (preferire fascia bassa Hard/Deadly), tabella Stato per capitolo corretta con la lista boss reale (Cap.1 escluso, Cap.2 nessun boss, Cap.3-4 in ricontrollo, Cap.5 Virruza+Akhviri, Cap.6 Belephaion senza Lohezet, Cap.7 Kansaldi+Lord Soth).
- [Ricontrollo capitolo-03.md](issues/04-ricontrollo-capitolo-03.md): fatto — nessun Minion reale da convertire (solo riferimenti testuali alla vecchia soglia, aggiornati), nota regole opzionali aggiunta, Villain Actions di Gholcag ok (nessun riciclo, è il primo boss scritto).
- [Costruire capitolo-02.md](issues/03-capitolo-02.md): fatto — preludio "Scales of War" adattato a 5 PG (3 baaz attaccano invece di 2, su 5 totali; kapak fugge con gli altri 2), nessun boss/Villain Actions. File in `campagna/scontri-adattati/capitolo-02.md`.
- [Ricontrollo capitolo-04.md](issues/05-ricontrollo-capitolo-04.md): fatto — 12 Goblin e Dragon Army Soldier convertiti da Minion a stat block classico (iniziativa condivisa); Villain Actions di Caradoc/Sarlamir riviste, nessun riciclo letterale ma due echi strutturali segnalati per vigilanza futura (PF temp sul colpo, AoE+prono).
- [Costruire capitolo-05.md](issues/06-capitolo-05.md): fatto — tutti gli incontri con nemici coperti (Wrecker's Edge, Blue Phoenix Shrine, Sunward Fortress, Wakenreth, Bluemaw Cave, Camp Carrionclay, Dread Wolf Cove, Wind's End). Virruza (~CR7, base green slaad + Death Throes acido) e Akhviri (~CR9, ridimensionata da CR16) con 3 Villain Actions ciascuno, nessun riciclo di schema. Nessuno stat block ufficiale nella fonte per questo capitolo — tutto ricostruito da zero, `[TODO DM: verificare]` dove a giudizio.
- [Costruire capitolo-06.md](issues/07-capitolo-06.md): fatto — letto l'intero Cap.6 (righe 4354-5285), molti più incontri del previsto (Path of Memories, incontri casuali città, Occupied Mansion, Temple of Paladine, Threshold of the Heavens) oltre a Lohezet/Belephaion. Belephaion boss vero con 3 Villain Actions innestate sul blocco young blue dragon; Lohezet confermato trattamento minore, niente Villain Actions.
- [Costruire capitolo-07.md](issues/08-capitolo-07.md): fatto — Kansaldi Fire-Eyes/Ignia e Lord Soth erano già ricostruiti per intero in dm-notes-sessione-27/28.md: tradotti in formato standard e aggiunte 3 Villain Actions ciascuno (Kansaldi sopra le Azioni Leggendarie esistenti; Lord Soth come contingenza collocata al suo scontro in Sessione 27). Aggiunti PNG minori (Wersten Kern, Karavarix, cavalieri scheletrici, veterana posseduta) con trattamento minore. **Nota:** Alstare Bellis/Lorry Wanwillow e le scene di Sessioni 25-26 NON coperte — lasciato `[TODO DM]` esplicito nel file.

- [Lacune capitolo-07.md](issues/09-capitolo-07-lacune.md): fatto — aggiunte le Sessioni 25-26 (S1-S20) mancanti: Lesser Death Dragon, guardiani Cripta Sigillata, Figura Colossale, Alstare Bellis, Lorry Wanwillow, Drayan+Bozak, Wraith Altare Primordiale, Guarnigione, Sivak Sala di Guerra. Gruppi scalati +1, solitari invariati, nessun nuovo boss con Villain Actions. `capitolo-07.md` ora copre l'intero Capitolo 7.

## Not yet specified

## Out of scope
