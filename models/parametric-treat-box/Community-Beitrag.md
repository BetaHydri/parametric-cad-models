# Leckerli-Box für Hunde 3D-drucken: Taschen-Box mit Print-in-Place-Scharnier

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3200091-ultimative-treats-box – Profil:
<https://makerworld.com/en/@BetaHydri>

![Parametric Dog Treat Pocket Box – Leckerli-Box mit Namen und Motiv auf dunklem Holz](images/01_hero.jpg)

## Motivation: Leckerli griffbereit, Krümel bleiben drin

Beim Hundetraining ist die Hand schnell in der Tasche, und genauso schnell ist die
Tüte aufgerissen oder die Tasche voller Krümel. Eine Dose mit Deckel löst das – wenn
sie flach genug für die Tasche ist, sicher zubleibt und sich mit einer Hand öffnen
lässt. Genau dafür ist die **Parametric Dog Treat Pocket Box** gebaut: eine
Leckerli-Box, die in einem Stück gedruckt wird, ohne Stützen und ohne Montage.

## Funktionen im Überblick

- **Print-in-Place-Scharnier:** Box und Deckel liegen flach nebeneinander auf dem
  Bett, das Scharnier ist direkt nach dem Druck beweglich.
- **Übergreifender Deckel:** Die Schürze (`lid_rim` = `On`) liegt außen über Front
  und Seiten. Krümel bleiben drin, und der Deckel sitzt seitlich fest.
- **Schnapper außen:** Eine Feder an der Front rastet in eine Nut der Deckelschürze;
  Zahl (`latch_count`) und Haltekraft (`latch_grip`) sind einstellbar.
- **Taschenfreundlich:** Standardmaß 90 × 60 × 20 mm, gerundete Ecken, gefaste
  Deckelkante.
- **Name, Motiv und Fronttext:** `top_text`, `lid_decor` (`Paw`, `Bone`, `Dots`,
  `Ribs`, `Diagonal`) und `front_text`; Größe und Versatz werden automatisch auf
  die Fläche begrenzt.
- **Optionale Fächer:** `cells_x` und `cells_y` unterteilen den Innenraum mit
  Print-in-Place-Trennwänden.
- **Zweifarb-Modus:** Box und Deckel getrennte Farbkörper, Gravur als Farbfüllung.

![Variante TREATS mit Pfotenmotiv](images/02_variante-treats-paw.jpg)

## Entwicklungsprozess

Die Box ist Teil einer Familie parametrischer OpenSCAD-Modelle mit
Print-in-Place-Scharnier. Das Scharnier folgt den bewährten Regeln dieser
Familie: Die Achse liegt auf halber Höhe von Box und Deckel, sodass die flache
Deckelplatte über die Wandoberkanten klappt. Die Trommel sitzt knapp hinter der
Rückwand, damit der Footprint klein bleibt.

Beim Verschluss gab es mehrere Stufen. Ursprünglich saß eine federnde Zunge innen
an der Frontwand. Das funktioniert, kollidiert aber mit Fächern: Eine Zunge, die auf
einer Trennwand landet, verschweißt und federt nicht mehr. Der aktuelle Standard
verlegt den Schnapper deshalb nach außen: Eine Feder an der Box rastet in eine Nut
in der Deckelschürze. Der Innenraum bleibt frei, und die Haltekraft lässt sich mit
einem einzigen Parameter einstellen. Der alte Innen-Schnapper existiert in der
Datei weiter als Rückfall für Deckel ohne Rand.

## Technische Hintergründe

**Falttransformation.** Alles, was am Deckel hängt (Schnapper, Füllkeil, Nuten),
wird in geschlossenen Koordinaten modelliert und per 180°-Drehung um die
Scharnierachse in das flache Druck-Layout gelegt. Eine 180°-Drehung ist ihre eigene
Umkehrung, deshalb passt beides exakt zusammen.

**Scharnier.** Die Knuckle-Anzahl ergibt sich aus der Breite (ungerade, bei
Standardmaß 15), die Enden gehören zur Box, ein durchgehender Pin läuft durch. Die
Segmente haben jeweils `hinge_gap` Abstand (Standard 0,32 mm). Eine schmale Rippe
entlang der Scharnierkante verbindet die Deckelsegmente zu einer steifen Schiene.

**Rückwand.** Eine 45°-Fase an der Oberkante der Rückwand schafft Platz, damit der
Deckel beim Zuklappen nicht an der Kante hängt. Ein passender Keil an der
Deckelunterseite schließt den Spalt, wenn die Box zu ist.

**Text und Motiv.** Die Textgröße wird automatisch aus der Deckelfläche und der
Zeichenzahl berechnet (bis etwa ein Viertel der Fläche) und zusätzlich an die
Breite angepasst. Versätze werden auf die Fläche abzüglich Randabstand begrenzt;
das Motiv hält Abstand zum Text.

**Schnapper.** Die Feder hat eine flache Unterseite (sperrt gegen Anheben) und eine
angefaste Oberseite (schließt leicht). Eine kleine Fase an der Vorderkante dient
als Auslöserampe, damit sich der Deckel nicht erst mit Gewalt lösen muss.

![Variante LECKERLI mit Knochenmotiv](images/03_variante-leckerli-bone.jpg)

## Druck-Erfahrungen und Empfehlungen

Die mitgelieferten Profile sind für den **Bambu Lab P1S** mit **Bambu PLA Basic**
erstellt: 0,4-mm-Düse, 0,20 mm Layerhöhe, 3 Wände, Gyroid mit 15 % Infill, ohne
Stützen. Gedruckt wird flach, so wie das Modell ausgegeben wird.

- **Scharnier-Spiel:** `hinge_gap` ist der wichtigste Wert. Für Bambu liegt der
  sinnvolle Bereich bei etwa 0,30–0,40 mm. Klemmt das Scharnier, erhöhen; wackelt es,
  verringern. Bei PETG das Spiel etwas erhöhen.
- **Haltekraft:** Mit `latch_grip` (0,2–1,2 mm) lässt sich einstellen, wie fest der
  Deckel hält.
- **Zweifarbig:** `part` auf `Print flat (2 color)` stellen und direkt aus der
  OpenSCAD-OpenCSG-Vorschau exportieren, ohne F6. Der Name erscheint in der
  Boxfarbe.
- **Bauraum:** Das flache Layout ist beim Standardmaß etwa 94 × 128 mm groß. Bei
  größeren Boxen den Parameter `printer` setzen; das Modell warnt in der Konsole,
  wenn es nicht passt.

![Variante SNACKS mit Punkten und zwei Fächern](images/04_variante-snacks-dots.jpg)

## Einsatzideen

- Hundetraining mit zwei Sorten Belohnung (`cells_x` = 2)
- Dritte Kammer für Clicker oder Kotbeutel (`cells_x` = 3)
- Namensbox als Geschenk für Hundebesitzer
- Werkbank-Etui für Kleinteile mit beschriftetem Deckel
- Adapter- und Kabeldose für die Laptop-Tasche

![Variante GASSI mit diagonalen Rillen und drei Fächern](images/05_variante-gassi-diagonal.jpg)

## Fazit und Aufruf zum Mitmachen

Die Leckerli-Box ist ein parametrisches Werkzeug, kein Einzelstück: Du wählst Maß,
Fächer, Namen und Motiv, und das Modell hält Scharnier, Deckel und Schnapper
konsistent. Das Modell mit den Bambu-Studio-Profilen gibt es ausschließlich auf
**MakerWorld**. Ich freue mich über **Makes**, Fotos aus dem Training und
Rückmeldung zu `hinge_gap` und `latch_grip` bei anderen Druckern und Filamenten.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3200091-ultimative-treats-box

---

## 10 SEO-Titel

1. Leckerli-Box 3D-drucken: Taschen-Box mit Print-in-Place-Scharnier
2. Hundeleckerli-Dose aus dem 3D-Drucker mit Namen und Pfotenmotiv
3. Parametrische Leckerli-Box für Bambu Lab P1S: Maße, Fächer, Schnapper
4. 3D-gedruckte Leckerli-Tasche für das Hundetraining ohne Stützen
5. Treat Box für Hunde: Scharnier, Krümelrand und Verschluss einstellen
6. Print-in-Place-Box mit übergreifendem Deckel (OpenSCAD-Customizer)
7. Leckerli-Box mit Fächern für zwei Sorten oder Clicker
8. Dose für Hundetraining selbst drucken: Einstellungen und Profile
9. Taschenbox mit Schnapper: Haltekraft über `latch_grip` anpassen
10. Personalisierte Hunde-Geschenke aus dem 3D-Drucker: Leckerli-Dose

## 20 relevante Suchbegriffe

- Leckerli Box 3D-Druck
- Leckerli Dose drucken
- Hunde Leckerli Tasche
- dog treat box 3D print
- dog treat pouch 3D printed
- Hundetraining Zubehör 3D-Druck
- Print-in-Place Scharnier Box
- Box mit Klappdeckel 3D-Druck
- Schnapper Deckel 3D-Druck
- parametrische Box OpenSCAD
- OpenSCAD Customizer Dose
- Bambu Lab P1S Box
- MakerWorld Leckerli Box
- Box mit Namen 3D-Druck
- Pfotenmotiv 3D-Druck
- Fächer Box 3D-Druck
- Taschenbox 3D-Druck
- Dose ohne Stützen drucken
- personalisierte Hundebox
- funktionale 3D-Drucke Haustier

## 10 GitHub-Tags

- dog-treat-box
- parametric
- openscad
- print-in-place
- 3d-printing
- bambu-lab
- makerworld
- customizer
- pet-accessories
- functional-print

## 5 LinkedIn-Post-Ideen

1. Vom Gebrauchsproblem zum Parametermodell: Wie eine Leckerli-Box für die
   Hosentasche entstanden ist.
2. Konstruktionsfehler als Lernmaterial: Warum der Schnapper von innen nach außen
   gewandert ist, als Fächer dazukamen.
3. Print-in-Place ohne Montage: Warum die 180°-Falttransformation in OpenSCAD
   Konstruktions-Aufwand spart.
4. Ein Parameter, ein Effekt: `latch_grip` und `hinge_gap` als Beispiele für
   gutes Parameter-Design in Customizer-Modellen.
5. Personalisierung ohne Zusatzaufwand: Namen, Motiv und Fächer in einem Modell
   für Serien und Geschenke.

## 5 Reddit-Post-Ideen

1. r/3Dprinting – „Print-in-place treat box with a wrap-over lid and outer snap
   latch, printed flat on a P1S".
2. r/BambuLab – „Parametric pocket box in four variants with tested P1S PLA
   profiles" (Bilder der Varianten).
3. r/openscad – „Modelling fold-over lid accessories in closed coordinates and
   flipping them into the flat print layout with a 180° rotation".
4. r/functionalprint – „Pocket-sized dog treat box with dividers, name and motif
   engraved in the lid".
5. r/dogtraining oder r/dogs – „3D-printed treat box for training walks: how I made
   it crumb-proof" (Anwendungsfokus).
