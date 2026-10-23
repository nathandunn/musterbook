# Musterbook

A 1640s war of pike and shot, cut down to the parts that matter. You raise twenty companies on
a budget and win a war of ten battles with them. There are no recruits, so every company spent is
one fewer for the end. Before each battle you choose who goes in (up to ten) and the drill each one
fights by.

Live: https://musterbook.apps.precogsoftwareservices.com

It is built from [Drillbook Bots](https://github.com/nathandunn/drillbook-bots)' 1640s era, with
the same engine, troops, drills and budget. What was taken out: the 1860s war, epics, forts,
army-wide plans, Sim ×10, ranks and type fine-tuning.

## The four screens
1. **Raise your army** (the muster).
   - Pick one of eight period armies, then change any company's type or drill.
   - Money: £6,000-£20,000. Days in the field: 30-180. Rations: half, full or generous.
   - A running bill shows kit, wages and food. An army over budget cannot march.
2. **The war map.** After each battle the front of eleven fields shows where the fight went and
   what each army has left. It also shows battles won, battles fought out of ten, and companies
   left out of twenty. The full tables are one tap away.
3. **Choose companies and orders.** Tap up to ten companies in, and pick each one's drill from
   the full list. The computer chooses in secret: it reads what you sent last time and answers it.
4. **Watch the battle.** 1×, 2× or 4× speed, Pause, Skip to result, Retreat, Sound, and the
   camera pad.

**Practice battle**: one battle on any field, nothing lost.

**Winning**: carry the enemy's last field, or leave him with no companies. Otherwise, after ten
battles the war goes to whoever holds more of the front.

## Troops and drills
Musketeer (matchlock), Firelock, Pikeman, Pike and shot (mixed company), Archer, Clubman,
Dragoon, Harquebusier, Cuirassier, Hussar (lance) and Saker (guns). The kit for each is in
`scripts/kit.gd`, and the armies, budgets and war rules are in `scripts/era.gd`.

Drills are in `drills/`. The 1640s ones are 50-60: Shot, Salvee, Pike Block, Pike and Shot,
Charge Home, Gallop, Caracole, Lance Charge, Archers, Clubmen and Dragoons. The seed drills are
there too. Drills are written in the Drillbook DSL. Lint a drill with
`godot --headless --path . -- --lint=drills/x.drill`.

## Checks
- `--ui --uitest1640 --shots=dir`: the screens.
- `--ui --war1640 [--both] [--shots=dir]`: a whole war, every battle simulated.
- `./build.sh`: web export and pack check (Godot 4.7.2 with web templates).
