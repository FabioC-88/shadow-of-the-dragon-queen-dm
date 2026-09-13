# Scontri Adattati — Capitolo 2: Preludio "Scales of War"

**Copre:** Preludio "Scales of War" (introduzione ai draconiani, prima dell'arrivo a Vogler — Cap. 3)
**Framework di difficoltà:** vedi [00-framework.md](00-framework.md) — CR budget *Flee, Mortals!*, niente regola Minion, nessun boss/Villain Actions in questo capitolo
**Party:** 5 personaggi, Livello 1 · **Letalità target:** incontro leggero ed evitabile per costruzione — vedi [regole-opzionali.md](../regole-opzionali.md) (attivo da qui in poi, ma il fight è pensato per restare breve e opzionale)
**Lingua:** mostri, stat block e nomi delle azioni in **inglese**; tutto ciò che va letto ai giocatori resta in **italiano**.

> **Rapporto con i dm-notes:** il preludio è ora scritto per esteso in **`campagna/sessioni/dm-notes-sessione-00.md`** (PRELUDIO 3 — *I Pesi della Guerra*), che è la fonte narrativa da portare al tavolo: Rhys, il carro assaltato, i Cavalieri uccisi, il tesoro, i testi da leggere. **Questo documento resta la fonte di verità solo per i blocchi statistici e per il numero di nemici.** I due file sono allineati (verificato il 2026-09-13).

---

## Perché (a malapena) serve un adattamento

- Incontro di 1° livello, pensato dalla fonte come introduzione ai draconiani, non come vero banco di prova: i PG possono restare nascosti e non combattere affatto (Destrezza (Furtività) contro Percezione passiva 13 del kapak), oppure affrontare solo una parte dei baaz — già dimezzati negli HP — mentre il kapak fugge con gli altri.
- **5 giocatori, non 4:** l'unico adattamento reale è scalare leggermente quanti baaz il kapak manda all'attacco (3 su 5 totali, invece di 2 su 4), così l'incontro resta proporzionato senza trasformarsi in un vero combattimento a tutto campo.
- Nessun boss, nessuna Villain Action: il kapak non è scritto per combattere (fonte: i draconiani in ritirata "won't fight the characters under any circumstances").

---

## L'Imboscata al Carro

### Stat Block

```
BAAZ DRACONIAN (×5; 3 combattono se il party viene notato) — DSotDQ p197
Medium Monstrosity, typically Lawful Evil | AC 14 (natural armor)
Initiative +0 (10) | HP 11 (dimezzati — 22 a piena salute, già provati dai cavalieri) | Speed 30 ft.
STR 13 (+1, save +1)   DEX 11 (+0, save +0)   CON 13 (+1, save +1)
INT  8 (-1, save -1)   WIS  8 (-1, save -1)   CHA 10 (+0, save +0)
Gear Shortsword | Senses Darkvision 60 ft., Passive Perception 9
Languages Common, Draconic | CR 1/2 (XP 100; PB +2)

TRAITS
Controlled Fall. When the draconian falls and isn't incapacitated, it subtracts
  up to 100 ft from the fall when calculating the fall's damage.
Death Throes. When reduced to 0 HP, its body turns to stone and releases a
  petrifying gas. Each creature within 5 ft must succeed on a DC 11 Constitution
  save or be restrained as it begins to turn to stone. The restrained creature
  repeats the save at the end of its next turn: on a success the effect ends,
  otherwise the creature is PETRIFIED for 1 minute. After 1 minute, the body
  crumbles to dust.
Draconic Devotion. While it can see a Dragon that isn't hostile to it, the
  draconian has advantage on attack rolls.

ACTIONS
Multiattack. Two Shortsword attacks.
Shortsword. +3 to hit, reach 5 ft — 4 (1d6+1) piercing.
```

> ✅ **Scheda ufficiale DSotDQ p197**, verificata con Fabio il 2026-09-13 — sostituisce la ricostruzione precedente (AC 13, Claw + Javelin, Death Throes con esplosione 2d8). È ora identica in tutta la campagna.
>
> ⚠️ **Death Throes:** due TS falliti di fila = **Pietrificato per 1 minuto**, cioè un PG fuori dallo scontro. Il gas colpisce tutti entro 1,5 m: non ammucchiare il party attorno a un baaz ferito, e ricordati di far ripetere il tiro alla fine del turno successivo.
>
> ⚠️ **Il baaz non vola e non plana lateralmente:** l'unico tratto di caduta è *Controlled Fall*, che attutisce i danni senza concedere movimento.

```
KAPAK DRACONIAN (non combatte se può evitarlo — vedi "Come si svolge")
Medium Monstrosity | AC 15 (natural armor) | HP 39 (6d8+12)
Speed 40 ft, climb 40 ft (NON vola — solo planata, vedi Glide) | CR 3 (700 XP)
Languages: Common, Draconic

STR +0, DEX +3, CON +2, INT +1, WIS +1, CHA +0
Saving Throws: Dex +5 | Skills: Deception +4, Perception +3, Stealth +7
Immune: poison | Condition Immunities: poisoned
Darkvision 60 ft | Passive Perception 13

Glide: quando cade e non è incapacitato, sottrae fino a 30 m dall'altezza nel
  calcolo dei danni e può spostarsi di 60 cm in orizzontale ogni 30 cm di discesa.
  Non è volo: non può guadagnare quota.
Draconian Death Throes: si dissolve in acido che schizza chi gli sta attorno.
  Creature entro 1,5 m: TS Destrezza CD 12 o vengono ricoperte di acido per
  1 minuto, subendo 7 (2d6) danni acidi all'inizio di ogni proprio turno.

ACTIONS
Multiattack: 2 attacchi con Dagger. Se entrambi colpiscono la stessa creatura,
  quel bersaglio deve superare un TS Costituzione CD 12 o è avvelenato fino
  alla fine del suo turno successivo; mentre è avvelenato così, è anche paralizzato.
Dagger: +5 al colpo, portata 1,5 m o gittata 6/18 m — 1d4+3 perforanti + 2d6 veleno
```

*Nota: qui il Kapak è il blocco base, **senza** le aggiunte homebrew "Sneak Attack" e "Glide Away" scritte per l'incontro "Assassino dal Cielo" del Cap. 3 — in questa scena non è pensato per ingaggiare.*

⚠️ **Corretto il 2026-09-13** sullo stesso stat block ufficiale già usato in `capitolo-03.md`: il Kapak **non vola** (la versione precedente gli dava `fly 40 ft`, un errore che cambiava completamente la tattica), ha AC 15 e 39 PF, e la sua Death Throes è **acida**, non velenosa.

### Come si svolge

- **Se il party resta nascosto:** Destrezza (Furtività) di ciascun PG contro Percezione passiva 13 del kapak. Se non notati, i draconiani finiscono di saccheggiare il carro e se ne vanno — zero combattimento, solo narrazione.
- **Se notati:** il kapak ordina a **3 dei 5 baaz** (invece di 2 su 4 — scalato per il quinto giocatore) di attaccare, poi fugge nel bosco con gli altri 2. I baaz che restano a combattere non si ritirano; quelli che fuggono col kapak non attaccano in nessun caso — hanno l'ordine di ricongiungersi col Dragon Army altrove e riferire sulla sorte dei cavalieri.
- **Se lo scontro va male per il party:** un altro gruppo di viandanti diretto a Vogler si avvicina sulla strada; i draconiani feriti si ritirano per non rischiare uno scontro più grande, e il party viene di fatto salvato da questi viandanti (fonte, fine sezione).
- Nessuna Villain Action, nessun testo boxed dedicato oltre a quello già nella fonte ("A wrecked wagon lies toppled...").

**Nota di continuità:** i dettagli narrativi (Rhys, i tre Cavalieri di Solamnia uccisi, il tesoro recuperabile, i tiri di Intelligenza (Religione)/Intelligenza (Storia) CD 12) restano quelli della fonte — non riscritti qui, solo referenziati.

---

## Riepilogo Modifiche

| Scontro | Originale | Adattato | Motivo |
|---|---|---|---|
| Imboscata al Carro | 1 Kapak + 4 Baaz, 2 attaccano / 2 fuggono col kapak | 1 Kapak + 5 Baaz, 3 attaccano / 2 fuggono col kapak | scala leggermente sul quinto giocatore, mantenendo l'incontro evitabile e breve com'è nella fonte |

## Prossimi Passi

Capitolo 3 (When Home Burns) già adattato — vedi [capitolo-03.md](capitolo-03.md).
