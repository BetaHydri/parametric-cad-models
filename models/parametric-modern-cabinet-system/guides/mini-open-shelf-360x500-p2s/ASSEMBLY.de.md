# Open mini bookshelf 360 x 500 x 230 mm, 1 shelf, back panel - tool-free dovetail

## Montageanleitung

![mini-open-shelf-360x500](assembly/overview.png)

**Bausatz:** `mini-open-shelf-360x500-p2s`  |  **Gedruckte Teile:** 16 tiles + 24 keys  |  **Druckplatten:** 15  |  **Druckzeit (gesliced, PETG, 3 Wände, 15 % Gyroid):** 68 h, 2.7 kg

### Benötigtes Zubehör

- 2 x Wall screw + plug or anti-tip strap for the 2 anchor holes in the top panel (wall dependent)

**Werkzeug:** Gummihammer (optional), Sekundenkleber (optional); Bohrer für die Wandbefestigung

---

### 0  Drucken und vorbereiten
Alle Platten in **PETG** drucken (3 Wandlinien, 15 % Gyroid, 0,2 mm). Zuerst den **Passungstest** (`fit-test.stl`) drucken: der Schwalbenschwanz-Block muss sich von Hand mit leichter Reibung schieben lassen, der Scharnierstift muss sich frei drehen und der Schmetterlingsschlüssel muss sich mit dem Daumen eindrücken lassen. Ist es zu stramm oder zu locker, `fit` (Standard 0,25) bzw. `hinge_fit` im Customizer ändern und die Platten neu erzeugen.

![fit test](assembly/fit_test.png)

### 1  Kacheln der großen Platten verbinden
Große Platten werden als bauplattengroße Kacheln gedruckt. Die Kacheln einer Platte nebeneinander legen, **Feder in Nut**, Sichtseite nach unten. Die **Schmetterlingsschlüssel** in die Taschen der verdeckten Seite drücken (die Seite, die beim Druck *oben* lag: Innenseite der Seitenwände, Unterseite der Böden, Rückseite der Türen). Die Schlüssel liegen 0,4 mm unter der Oberfläche; ein Tropfen Sekundenkleber macht die Fuge dauerhaft. Die Rückwand hat einfache Nut-Feder-Fugen (hinten ein paar Tropfen Kleber oder Klebeband).

![seam and key](assembly/detail_seam.png)

### 3  Böden in die linke Seitenwand schieben
Linke Seitenwand mit der Innenseite nach oben auflegen. **Jede waagerechte Platte von hinten** in ihre Schwalbenschwanz-Nut schieben, bis sie am geschlossenen Nutende vorn anschlägt. Die Zapfenblöcke verriegeln die Platte gegen die Seitenwand - sie lässt sich nicht seitlich herausziehen.

![step 1](assembly/step1.png)

### 4  Rechte Seitenwand aufschieben
Die rechte Seitenwand vor die Bodenenden setzen und **nach hinten** über alle Zapfen gleichzeitig schieben, bis die Nuten anschlagen. Bei straffer Passung mit Gummihammer.

![step 2](assembly/step2.png)

### 5  Rückwand
Rückwand von hinten in den Falz schieben. Sie sichert alle Böden gegen Herausrutschen nach hinten. Reibpassung - für dauerhaften Halt ein paar Tropfen Kleber oder Klebeband.

![step 3](assembly/step3.png)

### 9  Schrank an der Wand sichern
**Pflicht.** Die zwei Löcher im Deckel nehmen Wandwinkel oder einen Kippschutz-Gurt auf. Freistehend kippt ein leerer Schrank dieser Art schon bei geringer Last auf der Vorderkante nach vorn (siehe *Kippen* in der Verifikations-Zusammenfassung unten).

![finished](assembly/overview.png)

---

## Zusammenfassung der Verifikation

### Durch Simulation verifiziert

| | Check | Result |
|---|---|---|
| OK | S1 3 horizontal panels slide from the rear into the left side (tool-free) | worst intersection 0.00 mm3 over 16 positions each |
| OK | S2 right side slides from the front over all tenons simultaneously | worst 0.00 mm3 |
| OK | S3 back panel slides into the rabbet from the rear | worst 0.00 mm3 |
| OK | L1a shelves cannot be pushed out backwards once the back panel is on |  |
| OK | L1b shelves cannot slide forwards (blind groove stop) |  |
| OK | L2 sides cannot be pulled apart (half-dovetail locks every shelf) |  |
| - | mass model | cabinet 2.7 kg (solid PETG 10.2 kg, fill factor 0.27 calibrated on the slicer weight); centre of mass x=180 y=127 z=265 mm |
| - | tip-over (front edge load) | load that tips the empty cabinet forward: 9 kg; loaded 23 kg: 66 kg (lever = toe-kick 30 mm) |
| OK | stability class: wall anchor REQUIRED | top panel carries the 2 anchor holes (wall_anchor = true) |
| OK | centre of mass is centred between the sides | offset +0 mm |
| OK | shelf rating: 15 kg evenly distributed per shelf (stress and deflection <= L/200) | span 328 mm, shelf 16 mm thick |
| OK | shelf seam (bow-tie keys as tension ties) carries the bending moment | capacity 36.0 N*m vs demand 6.03 N*m (15 kg), safety 6.0 |
| OK | dovetail bearing pressure on the sloped flank | 0.15 MPa (allow 3.0) per shelf end, 2 blocks |
| OK | tenon neck shear (across layers) | 0.044 MPa (allow 1.33) |

*Berechnet mit dokumentierten Annahmen für gedrucktes PETG (E 600 MPa, Biegung 8 MPa, Schlüsselzug 15 MPa); immer mit eigenem Drucker und Material testen.*

### Printability

| | Check | Result |
|---|---|---|
| - | catalog | 6 parts, 16 tiles, dims {'W': '360', 'H': '500', 'D': '230', 'comp_h': '201', 'n_sh': '1', 'n_doors': '0', 'hinge': 'lea |
| OK | all 16 tiles fit the bed (256x256) |  |
| OK | all tiles lie flat on the bed (zmin = 0) |  |
| OK | every tile is ONE connected body |  |
| OK | no large unsupported overhangs / long bridges (>10.5 mm) |  |
| OK | tile seams (11): tongues sit in grooves without interference |  |
| OK | assembly (closed): no part-part interference (8 pairs) |  |
| OK | shelf 1 <-> left side clearance | gap=0.150 (design 0.15) |
| OK | back panel <-> side clearance | gap=0.200 (design 0.1) |
| OK | hardware part 'key' prints flat, one body, no steep overhang | z0=0.00 bodies=1 overhangs=[] size=[40.0, 18.0, 6.6] |

Prüfungen: Druckbarkeit, Fugen, Kollisionen und Spiele wurden an den echten exportierten Netzen gemessen; die Montage wurde mit Schiebeweg-Kollisionstests simuliert.
