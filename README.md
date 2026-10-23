# Musterbook

A 1640s war of pike and shot, cut down to the parts that matter. You shop for up to twenty
companies on a budget and win a war of ten battles with them. There are no recruits, so every
company spent is one fewer for the end. Before each battle you draw up the army: who goes in (up to
ten), where each one stands, and the drill it fights by.

Live: https://musterbook.apps.precogsoftwareservices.com

It is built from [Drillbook Bots](https://github.com/nathandunn/drillbook-bots)' 1640s era, with
the same engine, troops, drills and budget. What was taken out: the 1860s war, epics, forts,
army-wide plans, Sim ×10, the old automatic ranks and type fine-tuning.

## The screens
Choosing an army takes two screens.

1. **Raise your army** (the shop).
   - A shopping basket: each type has a price for a company over your days in the field, with
     − and + buttons. Buy up to twenty companies, or start from one of eight famous armies, cut
     to what you can pay for.
   - Money: £6,000-£20,000. Days in the field: 30-180. Rations: half, full or generous.
   - A running bill shows kit, wages and food. + is greyed out once you can't afford another
     company.
2. **Draw up for battle.** Shown before every battle.
   - Tap companies in or out (up to ten). "A balanced ten" sends ten in the same proportions as
     the whole army.
   - For each company going in, choose:
     - its **wing**: Left, Centre or Right, as seen from your side;
     - its **line**: Front, Second (15 paces behind) or Reserve (held back for the captain to
       send in);
     - its **orders**: any drill from the full list.
   - A 3×3 picture shows the order of battle as the enemy will meet it. "Draw up by the book"
     puts horse on the wings, pikes in the centre with shot either side, and dragoons, archers
     and guns in the second line. It redraws every time the picks change, until you move a
     company yourself.
   - Companies that share a place stand three abreast, horse on the outside and pikes in the
     middle of the foot.
   - The computer draws up by the book and chooses in secret.
3. **The war map.** After each battle the front of eleven fields shows where the fight went and
   what each army has left. It also shows battles won, battles fought out of ten, and companies
   left. The full tables are one tap away.
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
