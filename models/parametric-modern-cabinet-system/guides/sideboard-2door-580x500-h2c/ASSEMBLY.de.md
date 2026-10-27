# Sideboard 580 x 500 x 270 mm, two doors on printed print-in-place leaf hinges (hidden behind the doors), 1 shelf - dovetail + thumbscrews (no tools), scoop handles

## Montageanleitung

![sideboard-2door-580x500](assembly/overview.png)

**Bausatz:** `sideboard-2door-580x500-h2c`  |  **Gedruckte Teile:** 20 tiles + 31 keys  |  **Druckplatten:** 18  |  **Druckzeit (gesliced, PETG, 3 Wände, 15 % Gyroid):** 145 h, 5.8 kg

### Benötigtes Zubehör

- 4 x Leaf hinge (printed in place, in the kit), 50 mm
- 16 x M3 x 10 countersunk screw (ISO 10642 / DIN 7991) for the hinge leaves
- 12 x M4 thumb / wing screw 30 mm
- 12 x M4 hex nut (DIN 934, captive in the shelf)
- 9 x M3 x 16 self-tapping screw (back panel)
- 8 x Neodymium disc magnet 8 x 3 mm
- 2 x Wall screw + plug or anti-tip strap for the 2 anchor holes in the top panel (wall dependent)

**Werkzeug:** Kreuzschlitz PH1; Gummihammer (optional), Sekundenkleber (optional); Bohrer für die Wandbefestigung; Schraubendreher PH1 / T10 für die M3-Scharnierschrauben (Lötkolben nur bei `hinge_inserts`)

---

### 0  Drucken und vorbereiten
Alle Platten in **PETG** drucken (3 Wandlinien, 15 % Gyroid, 0,2 mm). Die **3MF** dieses Modells verwenden: sie enthält Modifier-Volumen, die die Wände um jedes Schrauben- und Einsatzloch mit **6 Wandlinien und 100 % Füllung** drucken (bei reinen STL-Dateien selbst 4-5 Wände um diese Löcher einstellen). Zuerst den **Passungstest** (`fit-test.stl`) drucken: der Schwalbenschwanz-Block muss sich von Hand mit leichter Reibung schieben lassen, der Schmetterlingsschlüssel muss sich mit dem Daumen eindrücken lassen, das **Print-in-Place-Scharnier** muss sofort nach dem Druck frei schwenken und eine **M3 x 10 Senkkopfschraube** muss sich in den Dom schneiden. Ist es zu stramm oder zu locker, `fit` (Standard 0,25) bzw. `hl_gap` (Standard 0,4) im Customizer ändern und die Platten neu erzeugen.

![fit test](assembly/fit_test.png)

### 1  Kacheln der großen Platten verbinden
Große Platten werden als bauplattengroße Kacheln gedruckt. Die Kacheln einer Platte nebeneinander legen, **Feder in Nut**, Sichtseite nach unten. Die **Schmetterlingsschlüssel** in die Taschen der verdeckten Seite drücken (die Seite, die beim Druck *oben* lag: Innenseite der Seitenwände, Unterseite der Böden, Rückseite der Türen). Die Schlüssel liegen 0,4 mm unter der Oberfläche; ein Tropfen Sekundenkleber macht die Fuge dauerhaft. Die Rückwand hat einfache Nut-Feder-Fugen (hinten ein paar Tropfen Kleber oder Klebeband).

![seam and key](assembly/detail_seam.png)

### 2  Sechskantmuttern einsetzen
In jeden Schlitz an der Unterseite der Böden / des Deckels / des Bodens eine M4-Sechskantmutter drücken (4 pro Platte). Etwas Klebeband oder Kleber hält sie während der Montage.

![nut section](assembly/detail_nut.png)

### 3  Böden in die linke Seitenwand schieben
Linke Seitenwand mit der Innenseite nach oben auflegen. **Jede waagerechte Platte von hinten** in ihre Schwalbenschwanz-Nut schieben, bis sie am geschlossenen Nutende vorn anschlägt. Die Zapfenblöcke verriegeln die Platte gegen die Seitenwand - sie lässt sich nicht seitlich herausziehen.

![step 1](assembly/step1.png)

### 4  Rechte Seitenwand aufschieben
Die rechte Seitenwand vor die Bodenenden setzen und **nach hinten** über alle Zapfen gleichzeitig schieben, bis die Nuten anschlagen. Bei straffer Passung mit Gummihammer.

![step 2](assembly/step2.png)

### 5  Rückwand
Rückwand von hinten in den Falz schieben und mit den M3-Schrauben fixieren (Vorbohrungen in der Hinterkante jedes Bodens). Sie sichert alle Böden gegen Herausrutschen nach hinten.

![step 3](assembly/step3.png)

### 6  Schwalbenschwänze festschrauben (optional, bei hoher Last empfohlen)
Von außen die **M4 x 30 Flügel-/Rändelschrauben** von Hand in die Muttern drehen - kein Werkzeug nötig.

![dovetail section](assembly/detail_screw.png)

### 7  Türen einhängen
**Scharniere:** jedes Scharnier ist ein Print-in-Place-Teil (zwei Flügel mit gedrucktem Stift) - nicht auseinanderziehen. Tür mit der Rückseite nach oben legen, einen Scharnierflügel in seine Tasche auf der Türrückseite drücken und mit **zwei M3 x 10 Senkkopfschrauben** befestigen (die Schrauben schneiden ihr Gewinde selbst in den verstärkten Dom; mit `hinge_inserts=true` vorher M3-Heat-Set-Einsätze einschmelzen). Das Scharnier öffnen, den anderen Flügel **von vorn** in die Tasche in der Vorderkante der Seitenwand schieben und mit zwei M3 x 10 Schrauben befestigen. Für jedes Scharnier wiederholen, dann die Tür schließen: sie liegt als Aufschlagtür über der Öffnung, die Scharniere sind dahinter verborgen. Prüfen, dass die Tür frei schwenkt; steht ein Schraubenkopf vor, ist die Senkung zu flach - Flügel neu drucken oder `hinge_fit` verringern.

![hinge into its pocket](assembly/detail_hinge.png)
![hinge into its pocket](assembly/detail_hinge_done.png)
![step 4](assembly/step4.png)

### 8  Magnete und Griffe
Magnete in die Taschen drücken (Türrückseite + Bodenvorderkante), **vor dem Verkleben die Polung testen**.

Griffmulde: nichts zu montieren.

### 9  Schrank an der Wand sichern
**Pflicht.** Die zwei Löcher im Deckel nehmen Wandwinkel oder einen Kippschutz-Gurt auf. Freistehend kippt ein leerer Schrank dieser Art schon bei geringer Last auf der Vorderkante nach vorn (siehe *Kippen* in der Verifikations-Zusammenfassung unten).

![finished](assembly/overview_open.png)

---

## Zusammenfassung der Verifikation

### Durch Simulation verifiziert

| | Check | Result |
|---|---|---|
| OK | S1 3 horizontal panels slide from the rear into the left side (tool-free) | worst intersection 0.00 mm3 over 16 positions each |
| OK | S2 right side slides from the front over all tenons simultaneously | worst 0.00 mm3 |
| OK | S3 back panel slides into the rabbet from the rear | worst 0.00 mm3 |
| OK | S4 2 door(s) slide in from the front onto the hinge side | worst 0.00 mm3 |
| OK | S5 doors swing 0..110 deg without touching the carcass | worst 0.00 mm3 |
| OK | S5b neighbouring doors do not touch while swinging | worst 0.00 mm3 |
| OK | S6 printed leaf hinges seat in their pockets from the front (M3 screws from the front, door swung open) | worst 0.00 mm3 |
| OK | L1a shelves cannot be pushed out backwards once the back panel is on |  |
| OK | L1b shelves cannot slide forwards (blind groove stop) |  |
| OK | L2 sides cannot be pulled apart (half-dovetail locks every shelf) |  |
| - | mass model | cabinet 5.8 kg (solid PETG 22.3 kg, fill factor 0.26 calibrated on the slicer weight); centre of mass x=290 y=111 z=270 mm |
| - | tip-over (front edge load) | load that tips the empty cabinet forward: 16 kg; loaded 26 kg: 86 kg (lever = toe-kick 30 mm) |
| OK | stability class: wall anchor REQUIRED | top panel carries the 2 anchor holes (wall_anchor = true) |
| OK | centre of mass is centred between the sides | offset -0 mm |
| OK | free-standing with all doors open at 90 deg | door moment 2.4 N*m vs stabilising 3.6 N*m -> TIPS when empty: wall anchor is MANDATORY (anchor holes are part of the top panel) |
| OK | door-open tipping is covered by the wall anchor | wall_anchor holes present |
| OK | shelf rating: 10 kg evenly distributed per shelf (stress and deflection <= L/200) | span 548 mm, shelf 18 mm thick |
| OK | shelf seam (bow-tie keys as tension ties) carries the bending moment | capacity 41.8 N*m vs demand 10.08 N*m (15 kg), safety 4.1 |
| OK | dovetail bearing pressure on the sloped flank | 0.10 MPa (allow 3.0) per shelf end, 3 blocks |
| OK | tenon neck shear (across layers) | 0.025 MPa (allow 1.33) |
| OK | leaf hinge: screw withdrawal under the open-door couple (safety 4 vs 120 N per M3) | door 0.68 kg, 3.1 N on the outer hinge, 1.6 N per screw |
| OK | leaf hinge: door weight per hinge (shear on the leaf / screws) | 3.3 N per hinge (2 hinges) |

*Berechnet mit dokumentierten Annahmen für gedrucktes PETG (E 600 MPa, Biegung 8 MPa, Schlüsselzug 15 MPa); immer mit eigenem Drucker und Material testen.*

### Printability

| | Check | Result |
|---|---|---|
| - | catalog | 8 parts, 20 tiles, dims {'W': '580', 'H': '500', 'D': '270', 'comp_h': '198', 'n_sh': '1', 'n_doors': '2', 'hinge': 'lea |
| OK | all 20 tiles fit the bed (330x320) |  |
| OK | all tiles lie flat on the bed (zmin = 0) |  |
| OK | every tile is ONE connected body |  |
| OK | no large unsupported overhangs / long bridges (>10.5 mm) |  |
| OK | tile seams (13): tongues sit in grooves without interference |  |
| OK | assembly (closed): no part-part interference (29 pairs) |  |
| OK | shelf 1 <-> left side clearance | gap=0.150 (design 0.15) |
| OK | back panel <-> side clearance | gap=0.200 (design 0.1) |
| OK | assembly (doors open 60 deg): no part-part interference (29 pairs) |  |
| OK | assembly (doors open 110 deg): no part-part interference (29 pairs) |  |
| OK | hardware part 'key' prints flat, one body, no steep overhang | z0=0.00 bodies=1 overhangs=[] size=[40.0, 18.0, 6.6] |
| OK | hinge (print-in-place): flat on the bed, exactly two separate leaves (they must not fuse) | z0=0.00 bodies=2 size=[22.4, 50.0, 8.0] |
| OK | hinge leaves swing 0..180 deg without touching each other | worst overlap 0.00 mm3 |

Prüfungen: Druckbarkeit, Fugen, Kollisionen und Spiele wurden an den echten exportierten Netzen gemessen; die Montage wurde mit Schiebeweg-Kollisionstests simuliert.
