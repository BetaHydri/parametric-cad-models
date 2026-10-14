# Gridfinity-Schraubgläser 3D-drucken: parametrisch, mit echtem Gewinde und passend zu jeder Grundplatte

Gridfinity bringt Ordnung in Schublade und Werkstatt – nur Kleinteile wie Schrauben, Perlen oder
SD-Karten springen aus offenen Bins, sobald es ruckelt. Deshalb gibt es jetzt den
**Parametric Gridfinity Screw-Top Jar**: ein Schraubglas, das im 42-mm-Raster steht, mit jedem
anderen Bin bündig abschließt und im MakerWorld-Customizer eingestellt wird.

👉 **MakerWorld-Link:**
https://makerworld.com/en/models/3434732-parametric-gridfinity-screw-top-jar – Profil:
<https://makerworld.com/en/@BetaHydri>

![Mehrere Schraubgläser auf einer Gridfinity-Grundplatte](images/01_hero.jpg)

## Motivation: Ein Bin, der sich verschließen lässt

Der Anlass ist einfach: Ein Gridfinity-Bin ist offen. Für Schüttgut, Kleinteile und alles, was beim
Öffnen der Schublade wandern soll, fehlt der Deckel. Ein Schraubglas löst das – wenn es die Gridfinity-
Füße hat und exakt so hoch ist wie die Nachbarn. Beides stellt das Modell sicher: Die geschlossene Höhe
ist immer Einheiten × 7 mm, der Fuß folgt der öffentlichen Spezifikation.

Alle Maße sind Parameter. `grid_size` setzt die Grundfläche (1×1 bis 4×4), `height_units` die Höhe,
`thread_pitch` und `thread_slop` bestimmen, wie das Gewinde greift.

## Funktionen im Überblick

- **Echter Gridfinity-Fuß:** 42-mm-Raster, 0,5 mm Spalt zwischen Bins.
- **Selbsttragendes Gewinde:** Trapez 90° mit 45°-Flanken, optional ISO 60°.
- **Höhe in Einheiten:** geschlossene Höhe = Einheiten × 7 mm.
- **Magnettaschen:** 4 pro Zelle, Einkleben oder Einpressen.
- **Kappenbeschriftung:** Text auf der Kappe, zweifarbig möglich.
- **Grundplatten-Passprobe:** 1–5 Zellen je Seite zum Testen des Sitzes.
- **Keine Stützen:** Glas aufrecht, Kappe mit der Deckfläche nach unten.

![1×1-Glas mit Kappenaufschrift „M3" neben einem offenen Glas](images/02_1x1-schrauben-m3.jpg)

## Technische Hintergründe

**Die Maße.** Die Grundfläche ist Zellen × 42 mm minus `base_gap` (bei einer Zelle 41,5 mm). Daraus folgt
der Kappenradius (halbe Grundfläche minus `cap_margin`) und der Glasradius (Kappenradius minus
`cap_wall` minus halbe `lid_tolerance`). Mit den Voreinstellungen ist das Gewinde rund 36 mm dick.

**Die Höhe.** Das Modell rechnet aus, wie viele Einheiten mindestens nötig sind, damit Fuß, Glaskörper,
Schulterrand und Kappe samt Gewinde passen, und hebt `height_units` bei Bedarf an. Mit den
Voreinstellungen sind das 4 Einheiten, also 28 mm.

**Das Gewinde.** Ein grobes Trapezgewinde mit 90° Flankenwinkel hat auf beiden Seiten 45°-Flanken und
braucht daher keine Stützen. Die Kappe wird mit der Deckfläche nach unten gedruckt. Für einen
leichtgängigen Sitz sorgen `thread_slop` und `lid_tolerance`.

**Der Boden.** Bei mehreren Zellen liegt der Innenboden mindestens 1 mm über den Spalten zwischen den
Füßen, damit der Boden nicht durchsichtig wird. Über Magnettaschen wird er um die Taschenhöhe plus
0,8 mm angehoben.

![Grundplatten-Passprobe mit zwei eingesetzten Gläsern](images/06_grundplatte-passprobe.jpg)

## Druck-Erfahrungen und Empfehlungen

Material PLA für trockene Lagerung oder PETG für ein zäheres Gefühl, 0,20 mm Layerhöhe, 4 Wände
(das Gewinde besteht aus Perimetern), 15 % Gyroid, keine Stützen. Das Modell ist auf Bambu Lab H2C, P2S
und P1S ausgelegt und getestet und lässt sich auf jedem FDM-Drucker drucken.

Klemmt die Kappe, erhöhe `thread_slop` auf etwa 0,15; sitzt sie locker, verringere ihn. Sitzen die Gläser
stramm in der Grundplatte, hilft `base_gap` = 0,6 mm. Wer eine Grundplatte von anderswo nutzt, druckt
zuerst die Passprobe. Ab 3×3 sind Glas und Kappe getrennte Objekte; der Slicer legt sie gegebenenfalls
auf zwei Platten.

## Einsatzideen

- Schrauben, Muttern und Dübel im Raster sortieren, Kappe mit „M3" beschriften
- SD-Karten, Jumper und Elektronik-Kleinteile
- Perlen, Knöpfe und Nähzubehör
- Gewürze in der Küchenschublade
- Schüttgut im großen 3×3-Glas
- Gläser und Kappen in verschiedenen Farben für verschiedene Inhalte

![2×2-Glas mit gelber Kappe „SPICE" auf einer Grundplatte](images/04_2x2-gewuerze.jpg)

## Fazit und Aufruf zum Mitmachen

Das Glas ist ein Baukasten: ein Fuß nach Gridfinity-Spezifikation, ein selbsttragendes Gewinde und ein
Dutzend Zahlen. Wenn du es druckst, freue ich mich über **Makes** mit Fotos – besonders über Rückmeldungen
zur Gewinde-Passung auf deinem Drucker und zum Sitz in Grundplatten anderer Hersteller. Schreib einfach
einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:**
https://makerworld.com/en/models/3434732-parametric-gridfinity-screw-top-jar

---

## 10 SEO-Titel

1. Gridfinity-Schraubglas 3D-drucken: parametrisch mit echtem Gewinde
2. Gridfinity Bin mit Deckel: Schraubglas für jede Grundplatte
3. Parametric Gridfinity Screw-Top Jar: one model, every baseplate
4. Schraubenbox im Gridfinity-Raster: Gläser 1×1 bis 4×4
5. Selbsttragendes Gewinde 3D-Druck: 45°-Flanken ohne Stützen
6. Gridfinity Gläser mit Magneten: Taschen zum Einkleben oder Einpressen
7. Gewürzglas für die Schublade: Gridfinity-kompatibel drucken
8. Kappe mit Beschriftung: Gridfinity-Gläser sortieren und beschriften
9. Gridfinity-Passprobe drucken: Sitz testen vor der großen Grundplatte
10. Schraubglas ohne Stützen drucken: Glas aufrecht, Kappe kopfüber

## 20 relevante Suchbegriffe

- Gridfinity Schraubglas
- Gridfinity Bin mit Deckel
- Gridfinity jar
- Gridfinity screw top
- Gridfinity container lid
- Schraubglas 3D-Druck
- Schraubgewinde 3D-Druck
- Gridfinity Magnete
- Gridfinity Gewürze
- Gridfinity Schrauben sortieren
- Gridfinity parametrisch
- Gridfinity OpenSCAD
- Gridfinity Customizer
- Gridfinity Grundplatte Test
- Gridfinity 42 mm
- Kleinteile Aufbewahrung 3D-Druck
- Werkstattordnung 3D-Druck
- Bambu Lab P1S Gridfinity
- MakerWorld Gridfinity
- funktionale 3D-Drucke

## 10 GitHub-Tags

- gridfinity
- storage
- organizer
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- screw-thread

## 5 LinkedIn-Post-Ideen

1. „Ein Bin, der sich verschließen lässt“: Warum Gridfinity ein Schraubglas braucht.
2. „45° statt Überhang“: Wie ein Trapezgewinde ohne Stützen druckt.
3. „Höhe in Einheiten statt Millimetern“: Wie das Modell die Mindesthöhe selbst berechnet.
4. „Erst die Passprobe“: Warum eine kleine Grundplatte Drucke spart.
5. „Vom Standard zum Modell“: Wie aus der öffentlichen Gridfinity-Spezifikation ein parametrisches Glas wird.

## 5 Reddit-Post-Ideen

1. r/gridfinity – „Parametric screw-top jar that fits every Gridfinity baseplate“ mit dem Hero-Bild.
2. r/functionalprint – „Support-free coarse trapezoid thread with 45° flanks“.
3. r/openscad – „Why the closed height must equal units × 7 mm“: Erklärung ohne Quelltext.
4. r/BambuLab – „Gridfinity jars with magnet pockets: glue-in vs press-fit“.
5. r/3Dprinting – „What thread slop works on your printer?“ als Diskussionsfrage zu `thread_slop`.
