# Scontri Adattati — Capitolo 5: The Northern Wastes

**Copre:** l'intero capitolo (Liv. 6→8) — Wrecker's Edge, Blue Phoenix Shrine, Sunward Fortress, Wakenreth, Bluemaw Cave (opzionale), Camp Carrionclay, Wind's End
**Framework di difficoltà:** vedi [00-framework.md](00-framework.md) — CR budget *Flee, Mortals!* ×5, niente regola Minion (iniziativa condivisa per i gruppi), boss Action-Oriented con Villain Actions
**Party:** 5 personaggi · **Letalità target:** Deadly/Hard scalato su 5 PG, fascia bassa preferita — vedi [regole-opzionali.md](../regole-opzionali.md) (critici massimizzati e riposo lungo limitato ai Dadi Vita alzano la letalità reale oltre il budget CR nudo)
**Lingua:** mostri, stat block e nomi delle azioni in **inglese**; tutto ciò che va letto ai giocatori resta in **italiano**.

> **Perché questo file e non i dm-notes:** i `dm-notes-sessione-NN.md` di questo capitolo restano la fonte narrativa (testo da leggere al tavolo, PNG, hook, struttura a hub delle location A-K). Questo documento sostituisce **solo** i blocchi statistici e le regole d'incontro, con rimando esplicito a dove si inseriscono.
>
> **Nota onestà DM:** i valori qui sotto sono ricalibrati a giudizio, non playtestati in modo formale (stesso approccio già usato per Gholcag in `capitolo-03.md`). Diverse creature di questo capitolo (draconian-slaad hybrid, Virruza, Akhviri, anhkolox) non hanno uno stat block completo nella fonte estratta — solo rimandi ad Appendice B — quindi sono ricostruite da zero, ispirate alle creature ufficiali citate (green slaad, adult black dragon) ma non copiate verbatim. `[TODO DM: verificare]` dove il numero è puramente a giudizio.

---

## Perché serve un adattamento

- **2024 vs 2014 + 5 giocatori:** stesso ragionamento di `00-framework.md` — i PG colpiscono più forte/spesso del baseline 2014, e 5 iniziative "consumano" l'azione di un nemico solitario più in fretta di quanto la fonte preveda per un party di 4.
- **Struttura del capitolo:** è un capitolo di viaggio/esplorazione a hub (mappa 5.1), non una sequenza lineare — la maggior parte delle location (B, G, H) è puramente sociale/esplorativa e non necessita adattamento meccanico. Solo gli scontri elencati sotto sono stati toccati.
- **Boss del capitolo (decisi con Fabio):** **Virruza** (D5, Sunward Fortress) e **Akhviri** (I, Camp Carrionclay) ottengono il trattamento pieno con 3 Villain Actions — Virruza perché è l'unico vero scontro scriptato serio del capitolo, Akhviri come contingenza esplicita nel caso il party scelga di combatterla invece di fuggire (la fonte la scrive per essere evitata). Nessun altro boss: il capitolo non ha un climax narrativo proprio, è rimandato al Cap. 6.

---

## A: Wrecker's Edge — Guardiani della Nave Elfica

Due **air elemental** difendono la nave dei maghi Silvanesti da chiunque non sia un elfo (invariato dalla fonte).

```
AIR ELEMENTAL (×2) — standard block
Large Elemental | AC 15 | HP 90 (12d10+24)
Speed 10 ft, fly 90 ft (hover) | CR 5 | Languages: Auran
Immune: lightning, thunder; damage from nonmagical attacks (except those with adamantine)
Condition Immunities: exhausted, grappled, paralyzed, petrified, poisoned, prone, restrained, unconscious

Whirlwind (Recharge 4-6): each creature in its space must make a DC 13 Strength save or take
2d8+5 bludgeoning and be flung up to 20 ft away and knocked prone.

ACTIONS
Multiattack: 2 Slam attacks.
Slam: +8 to hit, reach 5 ft — 2d8+5 bludgeoning.
```

*Consiglio: con 5 PG, 2 air elemental (CR5 ciascuno) sono già un incontro Hard/Deadly a livello 6 — non serve aggiungere nulla, l'economia delle azioni (Multiattack + Whirlwind) regge già bene contro 5 iniziative. Nessuna Villain Action: non è un boss, è un guardiano.*

---

## C: Blue Phoenix Shrine — Guardiani del Tempio

Due incontri distinti nel dungeon, entrambi invariati nella struttura (guardiani che si attivano per una trasgressione specifica) ma con numero adattato per 5 PG.

### Altar Guardians

```
WATER WEIRD (×3, era invariato — confermato adeguato per 5 PG)
Large Elemental | AC 13 | HP 58 (9d10+9)
Speed 0 ft, swim 60 ft | CR 3 | Languages: Aquan
Damage Resistance: acid, cold, fire | Damage Immunity: none extra
Invisible in water.

ACTIONS
Constrict: +6 to hit, reach 10 ft (water only), one creature — 2d6+4 bludgeoning,
  target grappled (escape DC 14), and can't breathe unless it can breathe water.
```

*3× CR3 = incontro Hard per 5 PG a livello 6-7 — coerente col budget, nessuna modifica necessaria oltre a confermarlo (la fonte già usa 3 invece del classico 2).*

### Shrine Guardians

```
BLACK PUDDING (×3, era invariato — confermato adeguato per 5 PG)
Large Ooze | AC 7 | HP 85 (10d10+30)
Speed 20 ft, climb 20 ft | CR 4 | Languages: —
Immune: acid, cold, lightning, slashing; blinded, charmed, deafened, exhausted, frightened,
  prone
Amorphous. Corrosive Form (damages nonmagical weapons/armor on hit). Spider Climb.

ACTIONS
Pseudopod: +8 to hit, reach 5 ft — 4d6+4 acid, and nonmagical armor worn corrodes (-1 AC,
  destroyed at 0).
```

*3× CR4 = Deadly per 5 PG — al limite alto della fascia raccomandata. `[TODO DM: verificare]`: se il party arriva già provato dagli Altar Guardians (niente auto-heal dal riposo lungo, vedi regole opzionali), valuta di scendere a 2 black pudding.*

---

## D: Sunward Fortress — Il Covo di Virruza

### D3 — Dracophage Subjects

**4× Draconian-Slaad Hybrid** — usa il blocco **Kapak Draconian** già scritto in [capitolo-03.md](capitolo-03.md), sostituendo l'attacco Dagger con:

```
Claw (replaces Dagger): +5 to hit, reach 5 ft — 1d4+3 piercing + 2d6 poison.
  Target (if Humanoid): DC 12 Constitution save or infected with a slaad egg
  (see D5 — Virruza's experiments accelerate the usual 3-month gestation to hours;
  treat as a ticking clock, not an instant threat, unless the table wants urgency).
```

*Niente Villain Actions — non è il boss, è un ostacolo lungo la strada verso D5 (test del framework, punto 3). 4 nemici, iniziativa condivisa.*

### Resting near Camp (evento condizionale)

50% di possibilità **2× Red Slaad** (vedi statistiche sotto D5) attaccano se il party riposa vicino al campo/fortezza — invariato dalla fonte.

### D5 — Virruza (Boss — Action-Oriented)

Il vero climax meccanico del capitolo: Virruza difende la Spawning Shard su un ponte/crepaccio infiammabile. Budget Hard/Deadly per un party di 5 al 6°-8° livello (CR cap ~6-7).

```
RED SLAAD (accompagna Virruza, coperto da 5 slaad tadpole)
Large Aberration | AC 13 (natural armor) | HP 93 (11d10+33)
Speed 30 ft | CR 5 | Languages: Slaad (can't speak)
Darkvision 60 ft | Passive Perception 11

ACTIONS
Multiattack: 2 Claw attacks.
Claw: +7 to hit, reach 5 ft — 2d6+4 slashing, and if target is Humanoid, DC 15 Constitution
  save or infected with a slaad egg (as D3 above).

SLAAD TADPOLE (×5, swarm — treat as a single hazard, not 5 separate turns)
Tiny Aberration | AC 12 | HP 1 (dies to any hit) | Speed 30 ft, climb 30 ft | CR 0
Bite: +4 to hit, reach 5 ft — 1 piercing. Gestisci come sciame decorativo: attaccano solo
  se il red slaad muore prima (schizzano fuori, 1 danno a chi è adiacente, poi fuggono).
```

```
VIRRUZA — mutated draconian (Villain — Action-Oriented, ~CR 7)
Large Aberration (mutated draconian) | AC 15 (natural armor) | HP 120
Speed 30 ft | Chaotic Evil | Languages: understands Draconic and Slaad, can't speak

STR 18 (+4), DEX 12 (+1), CON 16 (+3), INT 8 (-1), WIS 10 (+0), CHA 8 (-1)
Darkvision 60 ft | Passive Perception 10

ACTIONS
Multiattack: 2 Claw attacks, or Hurl Flame (recharge on a natural 5-6 per turn, replaces
  one Claw when available).
Claw: +7 to hit, reach 5 ft — 2d8+4 slashing.
Hurl Flame: ranged spell attack +5, range 60 ft — 3d6 fire; on a hit against a creature on
  a bridge, the bridge begins to smolder (see hazard below).

BONUS ACTION — Warty Lunge
Moves up to half its speed toward a creature it can see, ignoring difficult terrain from
the chasm's edge.

REACTION — Death Throes (passiva, non un vero reaction: si attiva a 0 HP)
Quando Virruza scende a 0 PF, esplode in una pozza d'acido. Ogni creatura entro 5 ft:
DC 12 Dexterity save o è coperta d'acido (7 danni acido all'inizio di ogni turno finché
non se lo pulisce di dosso con un'azione).

VILLAIN ACTIONS (una per round, dopo il turno di un nemico; ciascuna usabile una sola volta)
1. Opener — Lo Shard Sussurra: Virruza tocca la Spawning Shard alle sue spalle. Una
   creatura a sua scelta entro 30 ft deve superare un TS su Costituzione CD 14 o essere
   Spaventata per 1 minuto (vede la propria pelle iniziare a incresparsi, come la sua).
2. Control — Il Ponte Cede: Virruza colpisce il ponte/crepaccio sotto i piedi del party.
   Ogni creatura sul ponte: DC 14 Dexterity save o cade nel crepaccio (3d6 danni da caduta,
   atterra su una sporgenza 15 ft più in basso, deve arrampicarsi per tornare — 1 azione,
   Athletics CD 12).
3. Ultimate — Sputo Corrosivo: Virruza rigurgita un getto d'acido in cono di 20 ft. Ogni
   creatura nell'area: DC 15 Dexterity save, 4d10 acid (metà danni con successo). Le armi
   e armature non magiche colpite corrodono di -1 CA/danno finché non riparate.
```

**Testo da leggere (boss di capitolo — testo + Aggiunta atmosferica, legata al tema "corruzione/mutazione"):**

1. *Opener — Lo Shard Sussurra:*
   > Virruza posa il palmo sulla gemma arancione dietro di sé, senza guardarla — non ne ha bisogno, la conosce a memoria ormai, come si conosce una ferita che non guarisce. Quando si volta di nuovo verso di voi, un pezzo di pelle gli si stacca dalla guancia e cade a terra, ancora umida.
   >
   > *[Aggiunta atmosferica]: Non sembra accorgersene. O forse è già successo troppe volte perché importi ancora.*

2. *Control — Il Ponte Cede:*
   > L'artiglio scende sul legno del ponte con un suono che non è uno schianto — è più simile a uno strappo, come pelle vecchia. Le assi si aprono sotto i vostri piedi in una crepa che sa di zolfo.
   >
   > *[Aggiunta atmosferica]: Sotto, il crepaccio non ha fondo visibile. Solo buio, e il rumore lontano di qualcos'altro che si muove.*

3. *Ultimate — Sputo Corrosivo:*
   > Virruza spalanca una bocca troppo larga per la sua faccia e vomita un getto verdastro che fuma a contatto con l'aria. Dove tocca il metallo, il metallo si scioglie con un sibilo sottile.
   >
   > *[Aggiunta atmosferica]: L'odore arriva un istante prima del colpo — uova marce e qualcosa di dolce, sbagliato.*

*Ordine consigliato: Opener quando il party si avvicina alla Shard (stabilisce che Virruza non è "solo" un altro draconiano), Control appena qualcuno è sul ponte (usa l'hazard ambientale richiesto dal framework), Ultimate quando Virruza è insanguinato (l'acido come ultima risorsa disperata, non calcolata).*

---

## E: Wakenreth — La Torre Infestata

```
WRAITH (×2) — standard block, emergono dalle cripte se i corpi vengono disturbati
Medium Undead | AC 13 | HP 67 (9d8+27)
Speed 0 ft, fly 60 ft (hover) | CR 5 | Languages: the languages it knew in life
Immune: necrotic, poison; charmed, exhaustion, frightened, grappled, paralyzed, petrified,
  poisoned, prone, restrained
Damage Resistance: acid, cold, fire, lightning, thunder; bludgeoning/piercing/slashing from
  nonmagical attacks
Sunlight Sensitivity. Incorporeal Movement.

ACTIONS
Life Drain: +6 to hit, reach 5 ft — 4d8+3 necrotic; target's hp max reduces by the same
  amount until a long rest.
```

*Niente Villain Actions (non sono il boss del capitolo, sono un ostacolo — test framework). 2 nemici, gestibili con blocco classico. Si dissolvono se un PG restituisce oggetti rubati e si scusa — invariato dalla fonte, nessuna modifica meccanica necessaria.*

```
ANKHOLOX (compare dopo i wraith, attratto dall'attività)
Large Undead | AC 14 (natural armor) | HP 105 (14d10+28)
Speed 30 ft, climb 30 ft | CR 6 | Languages: —
Immune: necrotic, poison; exhaustion, frightened, poisoned
Darkvision 120 ft | Passive Perception 12

ACTIONS
Multiattack: 2 Rend attacks.
Rend: +8 to hit, reach 10 ft — 2d10+5 slashing plus 2d6 necrotic (target's hp max
  reduces by the necrotic damage dealt until a long rest).
```

*Trattamento "minaccia nominata ma minore": solo un nemico solitario CR6 contro 5 PG livello 7-8 non regge l'economia delle azioni senza un aiuto — dagli una Reaction extra (attacco di opportunità automatico su chi si allontana) invece delle 3 Villain Actions, dato che non è un boss di capitolo. Niente testo boxed dedicato, basta l'introduzione già nei dm-notes.*

---

## F: Bluemaw Cave (opzionale)

Non esplorato in dettaglio dalla fonte oltre a "crawling with monsters and draconians" — se il tavolo lo visita, riusa i blocchi Baaz/Kapak Draconian di `capitolo-03.md` più eventuali predatori dalla tabella "Wastes Predators". Nessun boss, nessuna Villain Action: è opzionale e secondario per definizione. `[TODO DM: dettagliare al bisogno se il party lo esplora davvero]`.

---

## I: Camp Carrionclay — Akhviri (Boss di Contingenza)

La fonte scrive questo scontro per essere **evitato**: "i personaggi non sono pronti a combattere Akhviri e dovrebbero essere incoraggiati a fuggire" — lei usa il soffio acido una volta, poi richiama le truppe e non insegue oltre il campo. Il blocco sotto esiste **solo** per il caso in cui il party attacchi comunque (deciso da Fabio: "se sono così idioti da combattere, che facciano" — non è ammorbidito, è pensato per essere davvero pericoloso).

```
AKHVIRI — adult black dragon (Villain — Action-Oriented, ~CR 9, ridimensionata da CR16
canonico per restare un rischio serio-ma-non-automatico-TPK contro 5 PG di livello 7-8)
Huge Dragon | AC 18 (natural armor) | HP 195
Speed 40 ft, fly 80 ft, swim 40 ft | Chaotic Evil | Languages: Common, Draconic

STR 23 (+6), DEX 14 (+2), CON 21 (+5), INT 14 (+2), WIS 13 (+1), CHA 17 (+3)
Darkvision 120 ft | Passive Perception 15
Resistant to acid | Frightful Presence (Recharge 5-6, DC 16 Wisdom or frightened 1 min)

ACTIONS
Multiattack: 1 Bite + 2 Claw.
Bite: +11 to hit, reach 10 ft — 2d10+6 piercing plus 1d8 acid.
Claw: +11 to hit, reach 5 ft — 2d6+6 slashing.
Acid Breath (Recharge 5-6): 60 ft line, 5 ft wide, DC 18 Dexterity save, 12d8 acid
  (half damage on success).

BONUS ACTION — Wing Buffet
Each creature within 10 ft: DC 18 Strength save or take 2d6+6 bludgeoning and be knocked
prone.

REACTION — Acid Retort
When hit by a melee attack, can spit acid at the attacker (no action): +11, 2d6 acid.

VILLAIN ACTIONS (una per round, dopo il turno di un nemico; ciascuna usabile una sola volta)
1. Opener — Non Siete Degni: Akhviri decolla, guadagnando 30 ft di quota. Finché resta in
   volo, gli attacchi in mischia contro di lei hanno svantaggio, mentre lei continua a
   colpire normalmente con Bite/Claw in picchiata.
2. Control — Pozza Corrosiva: sputa un getto d'acido a terra in un'area di 15 ft di
   raggio a sua scelta entro 60 ft. L'area diventa terreno difficile e corrosivo: ogni
   creatura che vi entra o inizia il turno lì subisce 2d8 acid (nessun TS).
3. Ultimate — Il Prezzo dell'Orgoglio: se qualcuno l'ha ferita sul serio (sotto la metà
   dei PF), Akhviri smette di trattenersi — attacco extra con Bite (+11, 2d10+6+1d8 acid)
   e il suo prossimo Acid Breath non richiede recharge.
```

**Testo da leggere (nemesi di contingenza — testo lungo, il peso di un vero drago):**

1. *Opener — Non Siete Degni:*
   > Akhviri non carica. Si solleva, senza fretta, come se il vostro attacco fosse un'osservazione più che una minaccia — e per la prima volta capite cosa significhi davvero la parola "drago" in questo mondo, oltre ai racconti.
   >
   > *[Aggiunta atmosferica]: L'ombra delle sue ali copre l'intero accampamento prima ancora che finisca di salire.*

2. *Control — Pozza Corrosiva:*
   > Sputa a terra, non contro di voi — un lungo getto verde-giallo che scioglie roccia e tenda con lo stesso disinteresse. Non sta mirando a uccidervi. Sta scegliendo dove potrete stare.
   >
   > *[Aggiunta atmosferica]: Il terreno sibila ancora molto dopo che ha smesso di fumare.*

3. *Ultimate — Il Prezzo dell'Orgoglio:*
   > Per la prima volta, Akhviri emette un suono che non è un ruggito da manuale — è più basso, quasi umano nella sua rabbia. Chi l'ha ferita davvero lo capisce nello stesso istante: ha smesso di giocare.
   >
   > *[Aggiunta atmosferica]: Non c'è più disprezzo negli occhi. C'è solo fame.*

*`[TODO DM: verificare]` con enfasi — questo è pensato per essere uno scontro che il party può ragionevolmente perdere o dover abbandonare a metà (ritirata, non sconfitta netta). Se il tavolo lo affronta, valuta di lasciare aperta un'uscita narrativa (es. crollo di una struttura, fuga verso il resto del campo) invece di forzare il combattimento fino alla morte di uno dei due lati.*

---

## J: Dread Wolf Cove (opzionale)

**1× Anhkolox** (blocco identico a quello di Wakenreth sopra) — Dalamar aiuta se presente. Opzionale, nessuna modifica oltre a riusare il blocco già scritto per Wakenreth.

---

## K: City of Lost Names — Wind's End (Battaglia di Distrazione)

Schermaglia su larga scala, non un duello — riusa **Dragon Army Soldier** (blocco in `capitolo-03.md`) e aggiungi:

```
DRAGON ARMY DRAGONNEL (wasteland dragonnel, mount + rider)
Large Beast | AC 14 (natural armor) | HP 55 | Speed 30 ft, fly 80 ft | CR 3
Languages: understands Draconic and Common but can't speak

ACTIONS
Multiattack: 1 Bite + 1 Tail.
Bite: +6 to hit, reach 5 ft — 2d6+3 piercing.
Tail: +6 to hit, reach 10 ft — 2d8+3 bludgeoning.
```

Niente boss, niente Villain Actions — è una battaglia campale con eventi ambientali a Iniziativa 0 (tabella "Wind's End Battlefield Events", invariata dalla fonte). Gestisci i Dragon Army Soldier/Dragonnel con iniziativa condivisa per gruppo, niente Minion. Il capitolo si chiude sul cliffhanger verso il Cap. 6 — nessuna modifica narrativa, solo meccanica.

---

## Riepilogo Modifiche

| Scontro | Originale | Adattato | Motivo |
|---|---|---|---|
| A — Air Elementals | invariato | invariato | già Hard/Deadly per 5 PG col budget nudo |
| C — Water Weirds / Black Puddings | invariato (3+3) | invariato | numero già adeguato a 5 PG |
| D3 — Dracophage Subjects | 4 hybrid | invariato | riusa blocco Kapak di cap.3, niente Villain Actions (ostacolo, non boss) |
| D5 — Virruza | CR non specificato in fonte | ~CR 7, Villain Actions + Bonus Action + Reaction passiva | unico vero boss del capitolo (deciso da Fabio) |
| E — Wraiths / Anhkolox | invariato / CR6 solitario | Anhkolox + Reaction extra | economia delle azioni contro 5 iniziative, resta comunque minore |
| I — Akhviri | CR16 canonico, pensata per la fuga | ~CR9, Villain Actions + Bonus Action + Reaction | contingenza voluta da Fabio, resta un rischio serio non un TPK garantito |
| K — Wind's End | invariato | invariato | battaglia campale, blocchi già esistenti riusati |

## Prossimi Passi

Capitolo 6 (City of Lost Names, Liv. 8) — Belephaion come boss vero, Lohezet trattamento minore, quando Fabio conferma.
