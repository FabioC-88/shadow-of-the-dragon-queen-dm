![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAnEAAAACCAYAAAA3pIp+AAAABmJLR0QA/wD/AP+gvaeTAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAANklEQVR4nO3OQQmAABRAsScYxpg/h5VMYARvRrCCNxG2BFtmZquOAAD4i3Ot7mr/egIAwGvXA224BcUMk6pDAAAAAElFTkSuQmCC)  
**name: statblock-5e**  
 **  
 description: Recupera il blocco statistiche di u** **n mostro o PNG di D&D 5e e lo restituisce in inglese in un formato canonico, pronto da dare in pasto a modelli, agenti o import su VTT. Usa questa skill ogni volta che l'utente nomina un mostro, un PNG o una creatura di D&D e vuole le sue statistiche — anc** **he se dice solo "dammi l'owlbear", "che statistiche ha un gibberling", "mi serve il blocco del troll", o incolla un blocco statistiche chiedendo di sistemarlo. Usala anche quando chiede di convertire, normalizzare o riformattare statistiche di creature 5e.**  
**Blocchi statistiche 5e**  
Restituisce blocchi statistiche di creature D&D 5e in un formato fisso e prevedibile, pensato per essere consumato da altri modelli e agenti.  
**Input**  
Il nome della creatura, in italiano o in inglese. Se l'utente scrive in italiano, traduci il nome in inglese prima di cercare (orsogufo → owlbear, coboldo → kobold, troll → troll).  
Modificatori opzionali che l'utente può aggiungere: una CR specifica, una fonte preferita ("versione SRD", "versione Tome of Beasts"), o json se vuole anche la versione strutturata.  
**Fonti ammesse**  
Tutte nel seguente ordine di preferenza:  
- https://5e.tools/bestiary.html  
- SRD 5.1 e SRD 5.2 (CC-BY-4.0)  
- Open5e (open5e.com, api.open5e.com) — aggrega SRD più materiale OGL/ORC di terze parti  
- 5esrd.com  
- Tome of Beasts / Creature Codex (Kobold Press, OGL)  
- Level Up A5e Monstrous Menagerie  
- Black Flag SRD (ORC)  
**Procedura di lookup**  
1. web_search con <nome inglese> 5e stat block open5e SRD. Se la creatura è di terze parti, aggiungi la fonte: <nome> tome of beasts stat block.  
2. Scegli fra i risultati una pagina di una fonte ammessa e falle web_fetch.  
3. Se i risultati contengono solo fonti non ammesse, non copiare nulla: passa al percorso "Creatura non coperta".  
Note operative apprese sul campo:  
- web_fetch accetta solo URL già comparsi in una ricerca o fetch precedente. Non costruire URL a mano (né slug tipo /v1/monsters/owlbear/): vengono rifiutati.  
- Anche quando l'URL base dell'API passa, **la query string viene scartata**: ?search=owlbear non filtra niente e torna una pagina intera dell'indice. Non contare sui parametri.  
- Per questo il percorso affidabile è sempre: ricerca → fetch della pagina del singolo mostro.  
**Formato di output**  
Sempre in inglese, sempre in questo ordine, dentro un blocco di codice ```markdown così che sia copiabile intero:  
# {Name}  
 *{Size} {type}{, subtype}, {alignment}*  
   
 **Armor Class** {AC} ({armor description})  
 **Hit Points** {HP} ({hit dice})  
 **Speed** {speeds}  
   
 | STR | DEX | CON | INT | WIS | CHA |  
 |:---:|:---:|:---:|:---:|:---:|:---:|  
 | {score} ({mod}) | ... | ... | ... | ... | ... |  
   
 **Saving Throws** {only if present}  
 **Skills** {only if present}  
 **Damage Vulnerabilities** {only if present}  
 **Damage Resistances** {only if present}  
 **Damage Immunities** {only if present}  
 **Condition Immunities** {only if present}  
 **Senses** {senses}, passive Perception {n}  
 **Languages** {languages, or —}  
 **Challenge** {CR} ({XP} XP)   **Proficiency Bonus** +{PB}  
   
 ### Traits  
 ***{Trait}.*** {text}  
   
 ### Actions  
 ***{Action}.*** {text}  
   
 ### Bonus Actions  
 ### Reactions  
 ### Legendary Actions  
   
Regole sul formato:  
- Le righe opzionali si **omettono** se il dato non c'è. Non scrivere mai Damage Resistances: none: una riga assente è più pulita da parsare di una riga vuota.  
- Le sezioni Bonus Actions, Reactions, Legendary Actions si includono solo se popolate.  
- **Non inventare mai un valore.** Se la fonte non riporta un campo che di norma esiste (tipico: hit_dice mancante, proficiency bonus non esplicitato), scrivi UNKNOWN invece di stimarlo. Un agente a valle deve poter distinguere un dato mancante da un dato inventato. Il bonus di competenza derivato dalla CR è l'unica eccezione: si può calcolare, ma segnalalo con (derived).  
- Fuori dal blocco di codice, in italiano, aggiungi due righe: la **fonte** (documento e licenza) e, se ci sono più versioni della creatura (es. SRD vs Tome of Beasts vs A5e), l'elenco delle alternative trovate, così l'utente può chiederne un'altra.  
- Chiudi sempre con la riga di attribuzione richiesta dalla licenza della fonte usata. Per l'SRD:  
 This work includes material taken from the System Reference Document 5.1 ("SRD 5.1") by Wizards of the Coast LLC, licensed under CC-BY-4.0.  
**Variante JSON**  
Se l'utente chiede json, aggiungi dopo il blocco markdown un secondo blocco con questo schema piatto — stesse regole su UNKNOWN:  
{  
   "name": "", "size": "", "type": "", "subtype": "", "alignment": "",  
   "armor_class": 0, "armor_desc": "", "hit_points": 0, "hit_dice": "",  
   "speed": {"walk": 0},  
   "abilities": {"str": 0, "dex": 0, "con": 0, "int": 0, "wis": 0, "cha": 0},  
   "saving_throws": {}, "skills": {},  
   "damage_vulnerabilities": "", "damage_resistances": "",  
   "damage_immunities": "", "condition_immunities": "",  
   "senses": "", "passive_perception": 0, "languages": "",  
   "challenge_rating": "", "proficiency_bonus": 0,  
   "traits": [{"name": "", "desc": ""}],  
   "actions": [{"name": "", "desc": ""}],  
   "bonus_actions": [], "reactions": [], "legendary_actions": [],  
   "source": {"document": "", "license": "", "url": ""}  
 }  
   
**Creatura non coperta dalle fonti aperte**  
Capita per parecchie creature del Monster Manual 2024 e per i PNG nuovi. In quel caso, in italiano, di' brevemente che la creatura non è in una fonte e offri le due strade:  
1. **L'utente incolla il blocco** dal manuale che possiede. Tu lo normalizzi nel formato qui sopra senza cambiare un solo numero: solo riordino dei campi, traduzione in inglese se serve, UNKNOWN per i campi assenti. Non aggiungere tratti, non "migliorare" il bilanciamento, non arrotondare.  
2. **Costruire un equivalente originale**: stesso ruolo tattico e stessa CR, ma tratti e testo scritti da zero. Segnalalo sempre come [homebrew] accanto al nome nel blocco, così a valle è distinguibile da un blocco ufficiale.  
Non proporre la strada 2 di default: chiedi quale delle due vuole, a meno che non l'abbia già detto.  
**Richieste multiple**  
Se l'utente chiede più creature in una volta ("i mostri per l'incontro nella palude"), fai un lookup per ciascuna e restituisci un blocco per ciascuna, separati da ---. Non accorpare, non riassumere: ogni blocco deve restare autonomo e copiabile.  
