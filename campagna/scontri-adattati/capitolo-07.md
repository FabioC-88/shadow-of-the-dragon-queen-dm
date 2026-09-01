# Scontri Adattati — Capitolo 7: Siege of Kalaman

**Copre:** l'intero Capitolo 7 — Sessioni 25-26 (Citadel Depths/Temple Crypts, Priests' Quarters), Sessione 27 (Bastione di Takhisis e fuga) e Sessione 28 (boss fight finale).
**Framework di difficoltà:** vedi [00-framework.md](00-framework.md) — CR budget *Flee, Mortals!* ×5 PG, niente regola Minion, boss Action-Oriented con Villain Actions
**Party:** 5 personaggi, Livello 11 · **Letalità target:** vedi [regole-opzionali.md](../regole-opzionali.md) — fascia bassa preferita, ma Lord Soth e Kansaldi sono **deliberatamente** all'estremo alto (vedi note sotto)
**Lingua:** mostri, stat block e nomi delle azioni in **inglese**; tutto ciò che va letto ai giocatori resta in **italiano**.

> **Perché questo file e non i dm-notes:** `dm-notes-sessione-27.md` e `-28.md` restano la fonte narrativa (testo da leggere al tavolo, PNG, eventi, tesoro, epilogo). Questo documento sostituisce **solo** i blocchi statistici e aggiunge le Villain Actions dove previsto dal framework.
>
> **Nota onestà DM:** i blocchi di Wersten Kern, Karavarix, Lord Soth, Kansaldi e Ignia erano già stati ricostruiti per intero nei dm-notes (appendix B non disponibile nella fonte estratta) — qui li traduco al formato inglese standard del framework e aggiungo Villain Actions solo dove concordato con Fabio (Kansaldi, Lord Soth). Non ho ritoccato i numeri di base: sono già tarati per un party di Livello 11, ed erano già pensati per un combattimento "quasi impossibile da vincere" (Soth) o "letale, il boss fight finale" (Kansaldi+Ignia) — vedi note budget sotto per il perché non li ho gonfiati ulteriormente. `[TODO DM: verificare al tavolo, specialmente Soth se il party lo affronta davvero]`.

---

## Perché serve un adattamento

- **5 giocatori, non 4:** il framework di *Flee, Mortals!* usa l'economia delle azioni (Villain Actions), non solo più PF, per far reggere un boss solitario contro 5 iniziative.
- **Soluzione adottata:** i due veri boss del capitolo — **Kansaldi Fire-Eyes** (+ Ignia, finale di campagna) e **Lord Soth** (contingenza, se il party lo affronta invece di usare lo specchio) — ottengono 3 Villain Actions ciascuno, oltre al kit che avevano già nei dm-notes (Kansaldi ha già Azioni Leggendarie: le Villain Actions si aggiungono, non le sostituiscono). Gli altri nemici nominati del capitolo (Wersten Kern, Karavarix, i cavalieri scheletrici, la veterana posseduta da Caradoc) restano trattamento "minaccia nominata ma minore" — sono ostacoli seri lungo la strada, non il motivo per cui il capitolo esiste.

---

## Sessione 25 — Sotto le Ossa del Drago (S1-S9)

### Lesser Death Dragon (S1, opzionale)

Incontro condizionale: scatta solo se il gruppo fallisce la prova di gruppo Saggezza (Sopravvivenza) CD 16. Creatura solitaria contro 5 PG — l'economia delle azioni è già a favore del party per definizione (1 turno contro 5), quindi nessuna Villain Action: basta un piccolo cuscinetto di PF.

```
LESSER DEATH DRAGON (unchanged stats, +15 HP for 5 PC economy)
Large Undead | AC 17 | HP 168 (was 153) | Speed 40 ft, fly 80 ft | CR 8
Immune: fire, poison | Condition Immunities: exhaustion, frightened, paralyzed, poisoned

Undead Fortitude: on damage that would drop it to 0 HP (non-radiant, non-crit), DC (5 + damage) Constitution save to drop to 1 HP instead.

ACTIONS
Multiattack: 1 Bite + 2 Claws
Bite: +9 to hit, reach 10 ft — 17 (2d10+6) piercing + 7 (2d6) necrotic
Claw: +9 to hit, reach 5 ft — 13 (2d6+6) slashing
Cataclysmic Breath (Recharge 5-6): 60 ft cone, DC 16 Dexterity save, 45 (13d6) fire + 18 (4d8) necrotic damage (half on success). A humanoid killed by this rises as a zombie under Dragon Army control.
```

### Cripta Sigillata — Guardiani (S3)

**2 Skeletal Knight → 3** (stesso blocco già usato sopra in questo file) **+ 1 Minotaur Skeleton**, scalati per il quinto giocatore.

```
MINOTAUR SKELETON
Large Undead | AC 12 (natural armor) | HP 67 | Speed 40 ft | CR 2

Charge: if it moves at least 10 ft straight toward a target and hits with a Gore attack, target takes 9 (2d8) extra piercing damage and, if a creature, DC 14 Strength save or knocked prone.

ACTIONS
Multiattack: 2 attacks — Gore and Battleaxe, or 2 Gore
Gore: +6 to hit, reach 5 ft — 6 (1d6+4) piercing
Battleaxe: +6 to hit, reach 5 ft — 10 (1d12+4) slashing
```

Estrazioni dalla tabella "Contenuti delle Cripte" (se il tavolo apre più cripte, gestisci ogni estrazione come incontro isolato, non cumulativo):

```
WIGHT (if drawn)
Medium Undead | AC 14 (chain shirt) | HP 45 | Speed 30 ft | CR 3
Skills: Perception +3, Stealth +4
Sunlight Sensitivity.

ACTIONS
Multiattack: 2 attacks, longsword or longbow only
Longsword: +4 to hit, reach 5 ft — 6 (1d8+2) slashing
Longbow: +4 to hit, range 150/600 ft — 6 (1d8+2) piercing
Life Drain: +4 to hit, reach 5 ft — 11 (2d6+4) necrotic; target's HP max reduces by the damage taken (until a long rest), wight regains that much HP. A humanoid slain this way rises as a zombie under the wight's control in 24 hours unless the body is destroyed or the target is healed first.
```

```
BLACK PUDDING (if drawn) — unchanged, single ooze
Large Ooze | AC 7 | HP 85 | Speed 20 ft, climb 20 ft | CR 4
Resistant to acid, cold, fire, lightning, slashing | Immune: acid
Corrosive Form: nonmagical metal/wood weapons that hit it corrode (-1 to hit cumulative, destroyed at -5).

ACTIONS
Pseudopod: +5 to hit, reach 5 ft — 11 (2d6+4) acid; DC 12 Constitution save or target's HP max reduces by the acid damage until a long rest. Nonmagical armor worn takes -1 AC (destroyed at 10).
Split: when it takes lightning or slashing damage, splits into two puddings if it has 10+ HP left.
```

### Il Santuario di Chemosh — Figura Colossale (S4, opzionale)

Scatta solo se un PG rifiuta l'offerta di Chemosh. Creatura solitaria — GS9 è già "molto sopra la norma" per scelta della fonte (punizione divina, non guardiano standard); lasciato invariato, nessun scaling ulteriore necessario a Livello 11.

```
UNDEAD CLAY GOLEM (base clay golem, reclassified undead per source)
Large Undead | AC 14 (natural armor) | HP 133 | Speed 20 ft | CR 9
Immune: poison, psychic; charmed, exhaustion, frightened, paralyzed, petrified, poisoned
Acid Absorption: takes no damage from acid, regains HP equal to the acid damage instead.
Berserk: at the start of each turn while at half HP or less, roll 1d6 — on a 6, attacks the nearest creature until destroyed or brought above half HP.
Immutable Form. Magic Resistance: advantage on saves vs spells/magic.

ACTIONS
Multiattack: 2 Slam attacks
Slam: +8 to hit, reach 5 ft — 9 (2d6+2) bludgeoning + 4 (1d8) necrotic
Haste (self, at half HP or less, next turn): double speed, +2 AC, extra attack, extra bonus action; takes 6 (1d12) necrotic damage each turn used.
```

### Alstare Bellis (S9)

Trattamento minore — non pensato per essere combattuto (offre un patto), ma può degenerare in tattiche mordi-e-fuggi se rifiutato/attaccato. Niente Villain Actions (non è il boss per cui il capitolo esiste), ma la sua natura di vampiro gli dà già economia delle azioni sufficiente per un incontro ricorrente/opzionale.

```
ALSTARE BELLIS — Vampire (base block), Medium Undead, Neutral Evil
AC 16 (natural armor) | HP 144 | Speed 30 ft, climb 30 ft
Regeneration 20/turn (none if in sunlight or running water) | Immune: necrotic; bludgeoning, piercing, slashing from nonmagical, non-silvered weapons
Legendary Resistance (3/day, if fought as a serious encounter — omit for a quick skirmish)
Shapechanger: can polymorph into a Tiny bat or Medium cloud of mist, or back.
Spider Climb, Vampire Weaknesses (forbiddance, running water, stakes, sunlight)

ACTIONS
Multiattack (only in vampire form): 2 attacks, only 1 can be a bite
Unarmed Strike: +9 to hit, reach 5 ft — 8 (1d8+4) bludgeoning, target grappled (escape DC 18) if not already grappled by Alstare
Bite (grappled/incapacitated/restrained target only): +9 to hit, reach 5 ft — 7 (1d6+4) piercing + 10 (3d6) necrotic, Alstare regains HP equal to necrotic dealt, target's HP max reduces by that amount
```

*Budget: blocco standard vampire, invariato — a Livello 11 con 5 PG non è pensato per essere vinto in combattimento diretto la prima volta (fugge), coerente con la fonte. `[TODO DM: verificare]` se il tavolo lo affronta ripetutamente in tattiche mordi-e-fuggi: valuta di aggiungergli Legendary Resistance stabile se diventa un antagonista ricorrente.*

---

## Sessione 26 — Sotto lo Sguardo di Soth (S10-S20)

### Corridoi Sorvegliati (S10)

**2 Skeletal Knight → 3** (stesso blocco di S3), scalati per il quinto giocatore.

### Lorry Wanwillow (S11)

Incontro pensato per il dialogo, non per il combattimento — diventa ostile solo se derubata. Niente Villain Actions. Nessuno stat block esplicito nella fonte: usa il blocco vampire base sopra (Alstare Bellis) come riferimento se il tavolo la spinge al combattimento, con Mutaforma verso ratto invece di pipistrello. `[TODO DM: verificare]` — non c'è motivo meccanico per differenziarla da Alstare, dato che la fonte non fornisce un blocco dedicato.

### Santuario Profanato — Drayan e i Bozak (S12)

**Drayan (Aurak Draconian) + 6 Bozak Draconian → 7 Bozak**, scalati per il quinto giocatore. Trattamento minore per Drayan (comandante ricorrente, non il boss per cui il capitolo esiste) — ha già economia delle azioni discreta (Sguardo Dominante, Respiro Nocivo, Portale Dimensionale per fuggire verso S18), sufficiente contro 5 PG senza Villain Actions.

```
BOZAK DRACONIAN (×7)
Medium Dragonborn | AC 15 (natural armor) | HP 65 | Speed 30 ft, glide | CR 3
Glide: no fall damage, can glide horizontally.
Death Throes: on death, explodes in magical fire — DC 13 Dexterity save, 14 (4d6) fire (half on success), 15 ft radius.

ACTIONS
Multiattack: 2 attacks with Spiked Mace
Spiked Mace: +4 to hit, reach 5 ft — 6 (1d8+2) bludgeoning
Heavy Crossbow: +2 to hit, range 100/400 ft — 6 (1d10+1) piercing
```

```
DRAYAN — Aurak Draconian, Medium Dragonborn, Lawful Evil
AC 18 (natural armor) | HP 114 | Speed 30 ft, fly 60 ft | CR 6
Saving Throws: Wis +4, Cha +6 | Magic Resistance: advantage on saves vs spells/magic
Death Throes: on death, dissolves into corrosive vapor — DC 15 Constitution save, 10 (3d6) acid (half on success), 10 ft radius.
Dimension Door (1/day, bonus action, no spell slot) — how she flees to S18 if losing.

ACTIONS
Multiattack: 2 attacks with Short Sword
Short Sword: +6 to hit, reach 5 ft — 8 (1d6+3) piercing + 3 (1d6) acid
Dominating Gaze (Recharge 5-6): one creature within 30 ft — DC 15 Wisdom save or charmed for 1 min (repeats save each turn end)
Noxious Breath (Recharge 5-6): 15 ft cone, DC 15 Constitution save, 22 (4d10) poison, poisoned 1 min (half damage, no poison on success; repeats save each turn end)
```

### Altare Primordiale — Wraith (S14, opzionale)

Scatta solo se un PG tocca l'altare. **3 Wraith → 4**, scalati per il quinto giocatore.

```
WRAITH (×4)
Medium Undead | AC 13 | HP 67 | Speed 0 ft, fly 60 ft (hover) | CR 5
Resistant to acid, cold, fire, lightning, thunder; bludgeoning, piercing, slashing from nonmagical weapons
Immune: necrotic, poison
Incorporeal Movement, Sunlight Sensitivity

ACTIONS
Multiattack: 2 Life Drain attacks
Life Drain: +6 to hit, reach 5 ft — 21 (4d8+3) necrotic; DC 15 Constitution save or target's HP max reduces by the damage taken (until a long rest), wraith regains that much HP. Target dies if HP max reduced to 0.
```

### Guarnigione Draconiana (S15, evitabile con furtività)

**4 Bozak → 5 Bozak** (blocco sopra) **+ 3 Kapak**, scalati per il quinto giocatore.

```
KAPAK DRACONIAN (×3)
Medium Dragonborn | AC 15 (natural armor) | HP 45 | Speed 30 ft, glide | CR 2
Skills: Perception +2, Stealth +4
Glide.
Poison Coating (bonus action): next weapon hit deals +7 (2d6) poison, DC 12 Constitution save or poisoned 1 min.
Death Throes: on death, liquefies into acid — DC 12 Dexterity save, 7 (2d6) acid (half on success), 5 ft radius.

ACTIONS
Multiattack: 2 attacks with Scimitar
Scimitar: +4 to hit, reach 5 ft — 5 (1d6+2) slashing (+ poison if coated)
Light Crossbow: +4 to hit, range 80/320 ft — 5 (1d6+2) piercing
```

### Sala di Guerra Draconiana — Sivak (S18)

**6 Sivak → 7** (o **4→5 + Drayan** se è fuggita qui da S12), scalati per il quinto giocatore.

```
SIVAK DRACONIAN (×7, or ×5 if Drayan present)
Medium Dragonborn | AC 17 (natural armor) | HP 44 | Speed 30 ft, fly 40 ft | CR 2
Death Curse (Reaction): on killing a humanoid with a melee attack, can assume its exact appearance for 1 hour or until it takes damage.
Dive Attack: if it flies 20+ ft straight toward a target and hits with a Claw, +10 (3d6) damage.

ACTIONS
Multiattack: 1 Bite + 2 Claws
Bite: +5 to hit, reach 5 ft — 12 (2d6+3) piercing
Claw: +5 to hit, reach 5 ft — 8 (1d6+3) slashing
```

*Se Drayan è presente (blocco sopra): il suo Respiro Nocivo è un'azione preparata sul primo PG a portata — applicalo appena entra in raggio, prima dell'iniziativa formale, come da fonte.*

---

## Wersten Kern (S23, Mourning Sanctum)

**Trattamento minore** — già ha un kit action-oriented-lite nei dm-notes (multiattacco + Litania Terrificante a ricarica + reazione Guardia dell'Impalcato): sufficiente contro 5 PG senza bisogno di altro. Nessuna Villain Action.

```
WERSTEN KERN — Undead, Lawful Evil
AC 18 (blackened plate) | HP 110 (13d8+52) | Speed 30 ft
STR 18 (+4), DEX 12 (+1), CON 18 (+4), INT 10 (+0), WIS 14 (+2), CHA 15 (+2)
Saving Throws: Wis +6, Cha +6
Resistant to bludgeoning, piercing, slashing from nonmagical attacks; necrotic
Immune: frightened, exhaustion, poisoned
Darkvision 60 ft | Passive Perception 12 | Languages: Solamnic (Common), Draconic

ACTIONS
Multiattack: 2 Pike attacks
Pike: +7 to hit, reach 10 ft — 2d6+4 piercing
Terrifying Litany (Recharge 5-6): each creature of its choice within 30 ft that can hear it — DC 15 Wisdom save or frightened for 1 minute (repeats save at end of each turn)

REACTION — Platform Guard
When a creature it can see hits the brazier, the platform, or a support pillar, Kern can make one Pike attack against that creature if in range.
```

*CR budget: HP/CD invariati rispetto ai dm-notes, già adeguati a 5 PG livello 11 — nessuna modifica necessaria.*

---

## Karavarix, Death Dragon Maggiore

**Trattamento minore** — un ostacolo drammatico ma non il boss per cui esiste il capitolo (quello è Kansaldi). Nessuna Villain Action; il kit da drago solitario (multiattacco + soffio a ricarica) regge già bene contro 5 PG per un singolo scontro d'impatto prima della fuga finale.

```
KARAVARIX — Undead Dragon (Gargantuan), Chaotic Evil
AC 19 (bony scales) | HP 250 (20d20+40) | Speed 40 ft, fly 80 ft
STR 25 (+7), DEX 10 (+0), CON 15 (+2), INT 10 (+0), WIS 14 (+2), CHA 17 (+3)
Saving Throws: Dex +5, Con +7, Wis +7, Cha +8
Resistant to necrotic | Immune: fire, poison | Condition Immunities: frightened, exhaustion, poisoned, paralyzed
Darkvision 120 ft | Passive Perception 16 | Languages: Draconic (understands Common, can't speak it)

Inner Cataclysmic Flame: creatures hitting it in melee with a nonmagical weapon take 4 (1d8) fire damage.

ACTIONS
Multiattack: 1 bite + 2 claws
Bite: +12 to hit, reach 10 ft — 19 (2d10+7) piercing + 9 (2d8) necrotic
Claw: +12 to hit, reach 5 ft — 15 (2d6+7) slashing
Cataclysmic Flame Breath (Recharge 5-6): 60 ft cone, DC 18 Dexterity save, 55 (10d10) fire and necrotic damage combined (half on a success)
```

*CR budget: invariato — GS14 contro 5 PG livello 11 è un incontro Hard/Deadly ben gestibile in un singolo scontro isolato, coerente col ritmo "fuga dal Bastione" della sessione.*

---

## Cavalieri Scheletrici (×2) e Veterana posseduta da Caradoc

Trattamento standard, invariato dai dm-notes — CR troppo basso per giustificare qualunque trattamento speciale anche a 5 PG.

```
SKELETAL KNIGHT (×2)
Medium Undead | AC 16 (worn plate) | HP 45 | Speed 30 ft
Resistant to bludgeoning, piercing, slashing from nonmagical attacks | Immune: poison | Condition Immunities: exhaustion, poisoned

ACTIONS
Multiattack: 2 Longsword attacks (two-handed) — +4 to hit, reach 5 ft — 8 (1d10+2) slashing
```

```
VETERAN (Amelia Ghallen, possessed by Caradoc)
Medium Humanoid | AC 17 (splint) | HP 58 | Speed 30 ft

ACTIONS
Multiattack: 3 attacks (2 shortsword + 1 dagger, or 2 dagger at range)
Shortsword: +5 to hit, reach 5 ft — 6 (1d6+3) piercing
Dagger: +5 to hit, reach 5 ft, or +3 at range 20/60 ft — 4 (1d4+2) piercing
Heavy Crossbow: +3 to hit, range 100/400 ft — 6 (1d10+1) piercing
```

---

## Lord Soth — Boss di Contingenza (S25 e oltre)

**Solo se il party sceglie di combatterlo apertamente** invece di usare lo specchio dei passati riflessi (l'esito narrativamente previsto). Trattamento pieno con 3 Villain Actions — è soprannaturale e non ha bisogno di chiamare rinforzi, coerente con l'esempio già scritto in `00-framework.md`.

```
LORD SOTH — Death Knight, Undead Medium, Lawful Evil
AC 20 (blackened plate) | HP 220 (21d8+126) | Speed 30 ft
STR 20 (+5), DEX 11 (+0), CON 22 (+6), INT 12 (+1), WIS 16 (+3), CHA 20 (+5)
Saving Throws: Wis +9, Cha +11
Resistant to necrotic; bludgeoning, piercing, slashing from nonmagical attacks
Immune: poison | Condition Immunities: frightened, poisoned
Magic Resistance: advantage on saving throws against spells and other magical effects
Darkvision 60 ft | Passive Perception 13 | Languages: Solamnic (Common), Draconic

Aura of Despair: each creature hostile to Soth within 60 ft, at the start of its turn, must succeed on a DC 19 Wisdom save or be frightened until the start of its next turn.
Aura of Foreboding: if a creature hostile to Soth starts its turn within 10 ft of him, and Soth isn't incapacitated, he can force it to repeat a saving throw it just made against an effect that frightened or charmed it, with disadvantage.

ACTIONS
Multiattack: 3 attacks with Hellsword.
Hellsword: +11 to hit, reach 5 ft — 13 (2d6+6) slashing plus 18 (4d8) fire.
Cataclysmic Fire (Recharge 5-6): 30 ft cone, DC 19 Dexterity save, 45 (10d8) fire and necrotic damage combined, pushed 10 ft back (half damage, no push on a success).
Command Undead (Recharge 5-6): one undead within 30 ft — DC 19 Wisdom save or follows Soth's verbal commands for 24 hours.

LEGENDARY ACTIONS (3/round, one at a time, only at the end of another creature's turn)
Attack: Soth makes one Hellsword attack.
Spectral Step (costs 2 actions): Soth teleports up to 60 ft to an unoccupied space he can see.
Call of Will (costs 2 actions): one creature within 30 ft repeats a saving throw against an active fear or charm effect on it.

VILLAIN ACTIONS (one per round, after an enemy's turn; each usable once — solo se il combattimento va per le lunghe, oltre le sue Azioni Leggendarie già presenti)
1. Opener — Il Peso di Trecento Anni: l'Aura di Disperazione si intensifica per un istante — ogni creatura ostile entro 18 m deve ripetere immediatamente il tiro salvezza contro l'Aura, con svantaggio.
2. Control — Passo tra le Rovine: Soth si teletrasporta accanto a due creature diverse in rapida successione (fino a 18 m ciascun passo) e attacca entrambe con la Spada Infernale.
3. Ultimate — "Isolde": Soth sussurra il nome, ed è come se il tempo si spezzasse — ogni creatura entro 6 m deve superare un TS Saggezza CD 19 o essere incapacitata (nessuna azione, nessuna reazione) fino alla fine del proprio turno successivo, sopraffatta da un dolore non suo.
```

**Testo da leggere (nemesi ricorrente/finale — testo lungo ed evocativo, coerente col peso in campagna):**

1. *Opener — Il Peso di Trecento Anni:*
   > L'aria intorno a Soth si fa più fredda, e per un istante il ricordo di ogni cosa che avete perso in questa guerra torna a galla tutto insieme, troppo vicino, troppo reale.
   >
   > *[Aggiunta atmosferica]: Non è magia che vi tocca la mente. È solo la sua vicinanza — trecento anni di rimpianto che non trova più spazio dentro un'armatura sola, e trabocca.*

2. *Control — Passo tra le Rovine:*
   > Non lo vedete muoversi. Un istante è davanti a un compagno, quello dopo è già oltre, la spada infernale che ha finito di colpire prima ancora che il suono vi raggiunga.
   >
   > *[Aggiunta atmosferica]: Cammina tra le rovine del Bastione come se le conoscesse da sempre — perché in un certo senso, per lui, sono sempre state rovine.*

3. *Ultimate — "Isolde":*
   > Per la prima volta, la sua voce non è un comando. È un nome, sussurrato, quasi perso nel fragore — e per un istante il tempo stesso sembra inciampare intorno a lui.
   >
   > *[Aggiunta atmosferica]: Nessuno di voi la conosce. Non ne avrete mai bisogno. Ma per quell'istante, siete tutti dentro un dolore che non vi appartiene.*

*Budget: numeri invariati dai dm-notes (GS19, già esplicitamente "quasi impossibile da vincere a Livello 11" per scelta narrativa — vedi `dm-notes-sessione-27.md`). Le Villain Actions aggiunte sono pensate come extra per un party di 5 che decide comunque di ingaggiarlo a viso aperto: non servono per renderlo vincibile, servono per rendere onesta la minaccia se il tavolo lo sceglie davvero. `[TODO DM: se il party affronta Soth sul serio, considera di NON usare tutte e 3 le Villain Actions nello stesso combattimento — sono già un'aggiunta sopra un boss pensato per essere quasi imbattibile].*

---

## Kansaldi Fire-Eyes + Ignia — Boss Finale di Campagna

Trattamento pieno. Kansaldi ha già Azioni Leggendarie nei dm-notes (repeatable, più deboli) — le Villain Actions si **aggiungono**, non sostituiscono, per lo scontro pensato per essere il vero climax meccanico della campagna. Scheletro d'ispirazione per l'economia delle azioni: **Amethyst Knife** (`fonti/Flee, Mortals!.md`, Villain Parties cap.3, liv.11) — principio preso in prestito: più fonti di minaccia simultanee (qui: Kansaldi + Ignia + le sue Azioni Leggendarie + Villain Actions), non le creature specifiche del party.

```
KANSALDI FIRE-EYES — Dragon Highmaster, Medium Humanoid, Lawful Evil
AC 18 (blackened plate) | HP 204 (24d8+96) | Speed 30 ft
STR 18 (+4), DEX 14 (+2), CON 18 (+4), INT 14 (+2), WIS 15 (+2), CHA 20 (+5)
Saving Throws: Con +9, Wis +7, Cha +10
Resistant to fire
Skills: Intimidation +10, Perception +7, Athletics +9
Legendary Resistance (3/day)
Darkvision 60 ft (from the gem) | Passive Perception 17 | Languages: Common, Draconic, Solamnic

Eye of Fire: the ruby fused into Kansaldi's left eye burns with an eternal flame, granting resistance to fire damage and darkvision even in total darkness.
Fanatic Devotion: advantage on saving throws against being frightened or charmed.
Ignia's Rider: while mounted on Ignia, advantage on saving throws against effects that would unseat her, and never a target of Ignia's Wing Buffet.

ACTIONS
Multiattack: 2 attacks with Hellish Pike, or 1 Pike attack + 1 Blazing Glare.
Hellish Pike: +9 to hit, reach 10 ft — 13 (2d10+4) piercing.
Blazing Glare: +9 to hit, range 60 ft — 24 (7d6) fire.
Command Shout (Recharge 5-6): Kansaldi shouts a battle-cry to Ignia — the dragon can immediately make one Bite attack as a reaction.

LEGENDARY ACTIONS (3/round, one at a time, only at the end of another creature's turn)
Pike Attack: Kansaldi makes one Hellish Pike attack.
Blazing Glare: Kansaldi makes one Blazing Glare attack.
Order Ignia (costs 2 actions): Kansaldi commands Ignia to fly up to her speed and/or make one Bite attack against a creature in range.

VILLAIN ACTIONS (one per round, after an enemy's turn; each usable once)
1. Opener — Il Segno della Regina Dragone: Kansaldi solleva l'occhio di rubino verso un nemico a scelta entro 18 m — quella creatura ha svantaggio al prossimo tiro salvezza contro un attacco di Ignia, e Ignia sa esattamente dove colpire.
2. Control — Muro di Fiamme: Ignia spazza basso il campo di battaglia lungo una linea di 18 m per 3 m di larghezza a scelta di Kansaldi — quell'area diventa terreno difficile in fiamme fino alla fine del prossimo turno di Kansaldi (chi vi entra o inizia il turno lì: DC 18 Destrezza o 14, 4d6, danni da fuoco, metà al successo).
3. Ultimate — L'Ultimo Sacrificio: quando Kansaldi è insanguinata (metà PF o meno), l'occhio di rubino arde al massimo — attacco extra con Blazing Glare contro ogni creatura entro 12 m da lei (singolo tiro per colpire per bersaglio, stesso bonus), poi guadagna 25 PF temporanei.
```

**Testo da leggere (nemesi ricorrente/finale — testo lungo ed evocativo):**

1. *Opener — Il Segno della Regina Dragone:*
   > Kansaldi alza il mento, e la gemma nel suo occhio sinistro non brucia più soltanto — punta. Un fascio di luce cremisi attraversa il campo di battaglia e si posa su uno di voi, freddo come una condanna già firmata.
   >
   > *[Aggiunta atmosferica]: Ignia lo vede prima ancora che voi capiate cosa significhi. I draghi non hanno bisogno di parole quando la loro cavaliera ha già scelto per loro.*

2. *Control — Muro di Fiamme:*
   > Ignia scende bassa, un ruggito che scuote le macerie della citadella sotto i vostri piedi, e dove passa il terreno stesso prende fuoco — non per il soffio, ma per il solo calore del suo passaggio.
   >
   > *[Aggiunta atmosferica]: Il fuoco non insegue nessuno. Semplicemente resta, e decide da solo chi può ancora attraversarlo.*

3. *Ultimate — L'Ultimo Sacrificio:*
   > Sanguinante, Kansaldi non arretra di un passo. Alza il volto verso di voi, l'occhio di rubino ormai quasi accecante, e per un solo istante brucia più di quanto un occhio dovrebbe poter bruciare.
   >
   > *[Aggiunta atmosferica]: Non sta cercando di sopravvivere. Sta cercando di portarsi dietro più di voi possibile, e crede — davvero crede — che sia lo stesso genere di vittoria.*

*Ordine consigliato: Opener appena il party ingaggia seriamente (mostra subito la sinergia col drago), Control quando il party si divide o si avvicina troppo, Ultimate quando Kansaldi è insanguinata — coerente con la sua morte già scritta in `dm-notes-sessione-28.md` ("non urla, non implora, muore convinta della propria causa").*

*Budget: HP/CD invariati dai dm-notes — 204 PF + 230 PF (Ignia) per un party di 5 PG livello 11 è già un incontro Deadly pieno, coerente col ruolo di vero boss finale di campagna. Le 3 Villain Actions aumentano la pressione dell'economia delle azioni contro 5 iniziative senza bisogno di alzare ulteriormente HP o CD.*

---

## Ignia (invariata)

Nessuna modifica — il duo con Kansaldi (2 creature + Azioni Leggendarie + Villain Actions di Kansaldi) è già sufficiente economia delle azioni; dare Villain Actions anche a Ignia renderebbe lo scontro ingestibile.

```
IGNIA — Dragon (Huge, young red dragon resized), Chaotic Evil
AC 19 (natural armor) | HP 230 (20d12+100) | Speed 40 ft, climb 40 ft, fly 80 ft
STR 25 (+7), DEX 10 (+0), CON 21 (+5), INT 14 (+2), WIS 13 (+1), CHA 19 (+4)
Saving Throws: Dex +5, Con +10, Wis +6, Cha +9
Immune: fire
Skills: Perception +11
Blindsight 30 ft, Darkvision 120 ft | Passive Perception 21 | Languages: Draconic

ACTIONS
Multiattack: 3 attacks — 1 Bite + 2 Claw.
Bite: +12 to hit, reach 10 ft — 21 (3d10+7) piercing + 7 (2d6) fire.
Claw: +12 to hit, reach 5 ft — 15 (2d6+7) slashing.
Fire Breath (Recharge 5-6): 40 ft cone, DC 18 Dexterity save, 55 (16d6) fire damage (half on a success).
Wing Buffet (Recharge 5-6): each creature within 10 ft — DC 18 Dexterity save or 15 (2d6+7) bludgeoning and knocked prone. Ignia can then fly up to half her speed.
```

---

## Riepilogo Modifiche

| Scontro | Originale (dm-notes) | Adattato | Motivo |
|---|---|---|---|
| Wersten Kern | Kit già action-oriented-lite | Invariato, tradotto in inglese | già sufficiente contro 5 PG |
| Karavarix | Solo dragon | Invariato, tradotto in inglese | ostacolo drammatico, non il boss del capitolo |
| Cavalieri scheletrici, Veterana | Standard | Invariato, tradotto in inglese | CR troppo basso per trattamento speciale |
| Lord Soth | GS19, Azioni Leggendarie | + 3 Villain Actions di contingenza | solo se il party lo affronta davvero invece di usare lo specchio |
| Kansaldi Fire-Eyes | GS16, Azioni Leggendarie | + 3 Villain Actions | vero boss finale, deve reggere 5 round contro 5 PG |
| Ignia | GS13 | Invariata | il duo con Kansaldi basta già come economia delle azioni |

## Copertura e prossimi passi

Questo file copre l'intero Capitolo 7: Sessioni 25-26 (Citadel Depths, Temple Crypts, Priests' Quarters — S1-S20), Sessione 27 (Bastione di Takhisis e fuga) e Sessione 28 (boss fight finale). Nessuna scena rimane fuori dall'adattamento.

Note di scaling generali per le Sessioni 25-26: i gruppi numerosi (Bozak, Sivak, Skeletal Knight, Wraith) sono scalati di +1 unità per il quinto giocatore, coerente col resto della campagna; le creature solitarie (Lesser Death Dragon, Undead Clay Golem, Alstare Bellis) restano sostanzialmente invariate perché l'economia delle azioni gioca già a favore di 5 PG contro 1 nemico. Nessun nuovo boss con Villain Actions in questa parte del capitolo — Drayan e Alstare Bellis restano trattamento minore, come deciso con Fabio.
