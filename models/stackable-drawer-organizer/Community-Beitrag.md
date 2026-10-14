# Stapelbare Schubladen 3D-drucken: parametrisch, mit Schiene, Rast und Einsätzen

Ich wollte kein starres Schubladenkästchen, sondern ein System, das mitwächst:
Gehäuse, die sich ineinanderstecken, Schubladen mit einstellbarer Höhe und
Einsätze, die man tauschen kann, wenn sich der Bedarf ändert. Daraus ist das
**Stackable Parametric Drawer System** geworden – ein OpenSCAD-Modell, das du im
MakerWorld-Customizer einstellst.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3024548-parametric-stackable-drawer-system – Profil:
<https://makerworld.com/en/@BetaHydri>

![Drei Schubladen in Grau, Grün und Rosa in einem hellen Gehäuse auf einem Holzschreibtisch](images/01_hero.png)

## Motivation: Eine Box, die sich dem Inhalt anpasst

Kleinteile haben unterschiedliche Größen: Büroklammern brauchen eine flache
Schublade, Klebebandrollen eine tiefe. Fertige Schubladenboxen kennen meist nur
eine Höhe, und ihre Außenmaße passen selten in das Fach, in dem sie stehen
sollen. Beim System sind Breite und Tiefe frei, jede Schublade hat ihre eigene
Höhe, und die Fächeraufteilung steckt in einem losen Einsatz. Ändert sich der
Bedarf, tauschst du den Einsatz statt der Schublade.

## Funktionen im Überblick

- **1 bis 6 Ebenen** (`drawer_count`), jede Ebene ein Gehäuse mit einer
  Schublade.
- **Höhen einzeln einstellbar** (`h1` bis `h6`) oder einheitlich
  (`uniform_height`).
- **Umkehrbare Schiene:** Nut im Gehäuse und Rippe an der Schublade – oder
  umgekehrt (`rail_mode`).
- **Weiche Rast** gegen Herausfallen (`pull_stop`, `pull_stop_h`).
- **Stapelbar** über einen 45°-Fuß mit passender Tasche.
- **Fünf Fronttexturen** und eine Griffmulde.
- **Zehn Einsatz-Layouts** pro Schublade, inklusive „ein großes Fach + zwei
  geteilte Fächer“.
- **Mehrfarbiger Export** mit eigener Farbe je Schublade.

![Turm mit geöffneter oberer Schublade und Einsatz in isometrischer Ansicht](images/02_iso.png)

## Entwicklungsprozess

Die ersten Renderings stammen vom 7. Juli 2026: der zusammengebaute Turm in der
Standardkonfiguration und eine Variante mit Rippenfronten. Am 10. Juli kamen die
asymmetrischen Einsätze und eine ausführliche Parameteranleitung dazu, am
11. Juli Renderings des Dreier-Turms geschlossen und geöffnet. Anfang August
2026 folgten die Studio-Renderings und zwei Varianten mit Profilen für den P1S.
Die letzte Änderung am Modell ist vom 21. August 2026.

## Technische Hintergründe

**Die Schiene.** Nut und Rippe sind höchstens halb so tief wie die Wand
(`rail_wall_frac` = 0,5). Deshalb bleibt die Wand immer mindestens halb stehen,
auch wenn die Nut im Gehäuse sitzt. Bei der Standardwand von 4,0 mm sind Nut
und Rippe 2,0 mm tief. Das Gleitspiel `rail_clear` (0,35 mm je Seite) ist der
wichtigste Passungswert: Klemmt die Schublade, erhöhst du ihn in 0,05-mm-Schritten.

**Bündiges Schließen.** Die Schubladentiefe wird aus dem Einschubanschlag
`rail_backstop` abgeleitet, mit einer festen Reserve von 0,6 mm. Dadurch
erreicht die Schublade immer die geschlossene Position. Zwei `assert`-Prüfungen
melden, wenn extreme Einstellungen das verhindern würden.

**Die Rastnase.** Eine kleine Kugel nahe der Vorderkante der Schiene, halb in der
Wand oder Rippe vergraben. Die Rippe biegt sich beim Einschieben leicht darüber
und wird beim Herausziehen weich gehalten. Mit `pull_stop_h` stellst du die
Festigkeit ein: größer hält fester, zu groß lässt die Schublade nicht mehr
hinein.

**Stapeln ohne Support.** Der Fuß unten und die Tasche oben haben eine
45°-Flanke. Beides druckt ohne Stützen und zentriert die Ebenen von selbst. Die
Decke des Gehäuses ist dicker als die Tasche, damit das Gehäuse oben
geschlossen bleibt.

**Druckausrichtung.** Das Gehäuse steht auf der Rückseite, die Schiene läuft
senkrecht, die Öffnung zeigt nach oben. Die Schublade liegt mit dem Boden auf
dem Bett: Das ist eine offene Kiste, und die Front steht als senkrechte Wand.
Auf der Rückseite würde die Front über der offenen Wanne frei überhängen –
deshalb nicht so. Die Einsätze liegen flach.

**Einsatzhöhe.** Die Höhe der Einsätze wird unter die Griffmulde begrenzt (rund
2 mm Abstand), damit der Griff frei bleibt. Bei der Standardkonfiguration
ergibt das 21,4 / 36,4 / 56,4 mm für die drei Schubladenhöhen.

**Asymmetrische Einsätze.** Eine durchgehende Trennwand grenzt das einzelne Fach
ab (`insert_split_frac`, Standard 40 %), eine halbe Querwand teilt den Rest in
zwei Fächer.

![Alle Teile in Druckausrichtung: Gehäuse stehend, Schubladen und Einsätze flach](images/04_print_orientation.png)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für den **Bambu Lab P1S** mit **Bambu PLA Basic** gebaut:
0,20 mm Layerhöhe, 3 Wände, 15 % Gyroid, im Slicer getestet. Es gibt zwei
Varianten: „standard“ mit 120 × 150 mm und „schmal“ mit 90 × 130 mm. Das Modell
ist für P1S, P2S und H2C ausgelegt.

Bei PETG erhöhst du `rail_clear` und `insert_clear` leicht. Prüfe vorab die
Bauhöhe: Gehäuse und Schublade stehen im Druck, die Bauhöhe entspricht etwa
`unit_depth`. Ich empfehle, zuerst ein Gehäuse und eine Schublade zu drucken
und das Gleitspiel zu prüfen, bevor du den ganzen Turm druckst.

Für den **mehrfarbigen Export** (`part` = 6) exportierst du den STL direkt aus
der OpenSCAD-Vorschau, ohne F6/Render und ohne Kommandozeile; sonst werden die
Farbgruppen zu einem Körper vereinigt. Bei drei Schubladen sind es fünf Gruppen
(Gehäuse, drei Schubladen, Einsätze), die mehr als vier Farben brauchen.
Ohne AMS druckst du Gehäuse und Schubladen einfach getrennt in
verschiedenen Farben.

## Einsatzideen

- Schreibtisch: Büroklammern, Klebeband, Stifte, Notizzettel
- Elektronik und Homelab: Widerstände, Schrauben, Stecker, SSDs
- Werkstatt und Basteln: Bits, Dübel, Perlen, Nähzubehör
- Regalfach nach Maß mit angepasster Breite und Tiefe
- Farbcodierter Turm mit je einer Farbe pro Schublade

![Variante mit horizontalen Rippen an den Fronten und gefüllten Schubladen](images/03_ribs.png)

## Fazit und Aufruf zum Mitmachen

Das System ist ein Baukasten für Schubladen aller Art. Wenn du es druckst,
freue ich mich über **Makes** mit Fotos, besonders mit eigenen Farben und
Einsatz-Layouts. Rückmeldungen zum Gleitspiel auf anderen Druckern helfen, die
Voreinstellung zu verbessern. Schreib einfach einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3024548-parametric-stackable-drawer-system

---

## 10 SEO-Titel

1. Stapelbare Schubladenbox 3D-drucken: parametrisch mit Schiene (OpenSCAD)
2. Schubladen-Organizer für Bambu Lab: 1 bis 6 Ebenen im Customizer
3. Schublade mit Rast 3D-drucken: Gleitspiel und Anschlag einstellen
4. Austauschbare Einsätze im Schubladensystem: 10 Fächer-Layouts
5. Stapelbare Gehäuse ohne Stützen: 45°-Fuß und Tasche
6. Schreibtisch-Organizer nach Maß: Höhe jeder Schublade einzeln wählen
7. Schubladensystem für Homelab und Elektronik: Kleinteile sortieren
8. Mehrfarbiger Schubladen-Turm: eigene Farbe je Schublade
9. Stackable Parametric Drawer System: one model, endless variants
10. Schublade 3D-Druck: Schiene mit halber Wandtiefe, Wand bleibt intakt

## 20 relevante Suchbegriffe

- Schubladenbox 3D-Druck
- stapelbare Schubladen 3D drucken
- Schubladen Organizer 3D-Druck
- parametrische Schublade OpenSCAD
- Drawer System 3D Print
- Stackable drawers 3D print
- Schublade mit Schiene 3D-Druck
- Schreibtisch Organizer 3D-Druck
- Kleinteile Schublade 3D-Druck
- Einsätze für Schubladen 3D-Druck
- Schublade ohne Stützen drucken
- Bambu Lab P1S Organizer
- Bambu Lab H2C Mehrfarbdruck
- MakerWorld Schubladen
- Customizer Organizer
- Mehrfarbdruck Organizer
- Elektronik Kleinteile Aufbewahrung
- Homelab Organizer 3D-Druck
- Werkstatt Organizer 3D-Druck
- funktionale 3D-Drucke

## 10 GitHub-Tags

- storage
- organizer
- drawer
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- stackable
- functional-print

## 5 LinkedIn-Post-Ideen

1. „Eine Schiene, die die Wand nicht schwächt“: Warum Nut und Rippe höchstens
   die halbe Wandstärke tief sein sollten.
2. „Drucken ohne Stützen – wie man ein Teil richtig hinstellt“: Gehäuse auf der
   Rückseite, Schublade flach.
3. „Weiche Rast statt Anschlag“: Eine Kugel, die nur Zehntelmillimeter
   übersteht.
4. „Ein Modell, zehn Einsatz-Layouts“: Fächer als austauschbare Teile statt
   fester Aufteilung.
5. „Constraints im Code“: Wie `assert` in OpenSCAD verhindert, dass die
   Schublade nicht mehr schließt.

## 5 Reddit-Post-Ideen

1. r/functionalprint – „Parametric stackable drawer system with swappable
   inserts and a soft detent“ mit dem Hero-Bild.
2. r/openscad – „Using asserts to keep a parametric drawer from breaking“:
   Erklärung des Ansatzes ohne Quelltext.
3. r/BambuLab – „One colour per drawer: multicolour export straight from the
   preview“.
4. r/3Dprinting – „Print orientation for drawers: why the drawer lies flat and
   the housing stands on its back“.
5. r/3Dprinting – „What rail clearance works on your printer for PLA vs PETG?“
   als Diskussionsfrage.
