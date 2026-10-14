# Schraubglas 3D-drucken: parametrisch, mit echtem Gewinde, Mustern und Beschriftung

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3243358-parametric-screw-top-jar-options-color-and-text – Profil:
<https://makerworld.com/en/@BetaHydri>

![Sechs Varianten des Schraubglases: Kaffee, Zucker, Tee, Mehl, Gewürze, Nudeln](images/01_hero.png)

## Motivation: Ein Deckel, der nicht vom Drucker abhängt

Mein runder Vorratsbehälter mit Steckdeckel funktioniert, hängt aber am
Reibsitz – und damit an der Maßhaltigkeit des Druckers. Zu stramm, und die
Kappe geht kaum ab. Zu locker, und sie fällt herunter. Ein Gewinde löst das
mechanisch. Das **Parametric Screw-Top Jar** ersetzt den Reibdeckel durch ein
grobes Schraubgewinde, das von Hand mit drei Umdrehungen greift. Größe, Muster
und Beschriftung stellst du im MakerWorld-Customizer ein.

## Funktionen im Überblick

- **Echtes Trapezgewinde** (BOSL2 `threaded_rod`): Standard 2,8 mm Steigung,
  3 Umdrehungen, also 8,4 mm Gewindehöhe.
- **Gewinde mit vollem Körperdurchmesser** auf einer Schulter; die Kappe
  setzt plan auf.
- **Druckspiel einstellbar:** `thread_slop` (Standard 0,12 mm) und
  `lid_tolerance`.
- **Neun Oberflächenmuster**, getrennt für Glas und Kappe wählbar: glatt,
  V-Rillen, runde Rillen, rechteckige Nuten, Ringe, 45°-Diagonale,
  Kreuzschraffur, Noppen, Facetten.
- **Kappe mit Rändel** oder mit dem Muster des Glases.
- **Beschriftung** auf der Glaswand und auf dem Kappendeckel, Buchstabe für
  Buchstabe auf dem Bogen graviert.
- **Zweifarb-Ausgabe** für Glas, Kappe und Text.
- **Beliebige Größe:** Durchmesser 30–200 mm, Höhe 30–300 mm.
- **Sechs fertige Varianten** (Kaffee, Zucker, Tee, Mehl, Gewürze, Nudeln).

![Variante Kaffee: glattes Glas, Kappe mit Rändel](images/02_kaffee-glatt-grip.png)

## Entwicklungsprozess

Das Schraubglas ist am 31. August 2026 aus dem Gefäß-Modell mit Reibdeckel
entstanden. Mein erstes Gewinde war ein selbst gebautes Trapezgewinde auf einem
schmalen, abgesetzten Hals. Das ersetzte ich durch die Architektur eines
öffentlichen MakerWorld-Glases, das ebenfalls BOSL2 `threaded_rod` nutzt: das
Gewinde mit vollem Körperdurchmesser auf einer Schulter, die Kappe ein schlanker
Zylinder mit Innengewinde. Das ist robuster und druckt sich besser als der
schmale Hals. Muster, Beschriftung und Druckoptimierung sind meine eigene
Entwicklung.

Die meiste Arbeit steckte in den Mustern, nicht im Gewinde. Fast jedes Muster
hatte seinen eigenen Stolperstein (siehe unten), und mehrere davon haben mit
dem Renderer zu tun, nicht mit der Geometrie.

## Technische Hintergründe

**Das Gewinde.** Das Außengewinde sitzt mit dem Körperdurchmesser auf der
Schulter, die Kappe hat das Innengewinde mit `thread_slop` als BOSL2-Druckspiel
und etwas zusätzlichem Durchmesser. Die Schulter läuft unten in 45° aus der Wand
aus und druckt deshalb ohne Stützen; die Oberseite bleibt flach als Auflage für
den Kappenrand.

**Der Rechenbaum.** Hunderte Rillen- oder Noppenkörper in derselben Differenz
wie das Gewinde ließen den Baum der OpenCSG-Vorschau und von MakerWorld über die
Grenze wachsen. Seitdem steht die Muster-Differenz getrennt vom Gewinde; die
beiden werden erst am Ende vereinigt.

**Rillen ohne Spitzen.** Verjüngte Rillen hatten entartete Spitzen, aus denen
der Manifold-Renderer Millionen Facetten machte – Dateien im dreistelligen
Megabyte-Bereich. Eine einzige flache Extrusion über das Band zwischen den
Randzonen löste es.

**Facetten per Schnitt.** Subtrahiert man einen Polygonring, schneidet er durch
die Wand. Das Facettenmuster ist deshalb ein Schnitt von Zylinder und
Polygonprisma. Die Facettenzahl folgt aus der Zielbreite: `max(6, round(2πr /
facet_width))`.

**Diagonale per Helix.** Diagonale Rillen sind verdrehte Extrusionen; der
Verdrehwinkel `(57,29578 / r) × Höhe` ergibt 45° am Außenradius. Sie sind
rechenintensiv, deshalb warnt die Dokumentation und das Rillenmuster ist für
die Varianten die bessere Wahl.

**Text auf dem Bogen.** Jeder Buchstabe wird einzeln radial eingraviert. Bei
Facetten wird die Wand im Textfenster rund aufgefüllt, damit die Glyphen nicht
über Facettenkanten laufen.

**Zweifarb-3MF.** Bambu Studio übernimmt die Farben einer OpenSCAD-3MF nicht
und meldet „invalid config, load geometry data only“. Ursache ist, dass Bambu
die eingebettete Projektkonfiguration nur akzeptiert, wenn die Anwendungsangabe
in der Datei mit `BambuStudio` beginnt. Die Farben stehen dann als Malfarbe je
Dreieck in der Datei. Über den Parametric Maker auf MakerWorld bekommst du das
fertig.

![Variante Tee mit Facettenmuster](images/04_tee-facetten.png)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für den **P1S** mit **Bambu PLA Basic** gebaut und im Slicer
getestet: 0,20 mm Layerhöhe, 3 Wände, 15 % Gyroid. Das Glas steht mit dem
flachen Boden auf dem Bett, die Kappe liegt mit der Deckelplatte unten; Stützen
sind nicht nötig. Drucke zuerst mit den Standardwerten und prüfe die Passung,
bevor du Größe und Muster änderst.

Das Gewindespiel hängt von Drucker, Düse und Material ab. Ist die Kappe zu
stramm, erhöhst du `thread_slop` auf etwa 0,15 mm; ist sie zu locker, senkst du
ihn. Bei `diagonal` oder `crosshatch` hältst du `pattern_count` niedrig,
sonst werden Vorschau und Export langsam.

## Einsatzideen

- Küchenvorrat: Kaffee, Zucker, Tee, Mehl, Nudeln, Gewürze
- Werkstatt: Schrauben, Muttern, Kabelbinder in beschrifteten Gläsern
- Homelab: Rack-Schrauben, Käfigmuttern, SD-Karten
- Basteln: Perlen, Knöpfe, Pailletten (Rändelkappe)
- Gartenbedarf: Saatgut mit Beschriftung
- Zweifarb-Etiketten: helles Glas, Kappe und Schrift in Kontrastfarbe

![Variante Zucker mit Noppenmuster](images/03_zucker-noppen.png)

## Fazit und Aufruf zum Mitmachen

Das Schraubglas ist ein Baukasten für Vorratsgläser aller Art. Wenn du es
druckst, freue ich mich über **Makes** mit Fotos, besonders mit ungewöhnlichen
Maßen, Mustern und Beschriftungen. Rückmeldungen zum Gewindespiel auf anderen
Druckern und in anderen Materialien helfen, den Standardwert zu verbessern.
Schreib einfach einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3243358-parametric-screw-top-jar-options-color-and-text

---

## 10 SEO-Titel

1. Schraubglas 3D-drucken: parametrisch, mit echtem Gewinde (OpenSCAD)
2. Vorratsglas mit Schraubdeckel für Bambu Lab: Größe und Muster einstellen
3. Gewinde im 3D-Druck: Spiel einstellen mit `thread_slop`
4. Schraubglas mit Beschriftung: Text auf Glas und Kappe
5. Neun Oberflächenmuster für Vorratsgläser: Rillen, Noppen, Facetten
6. Gewinde mit vollem Durchmesser auf einer Schulter: stützenfrei drucken
7. Zweifarb-Schraubglas für Bambu Lab: Schrift in Kontrastfarbe
8. Kaffeeglas, Zuckerglas, Mehlglas: sechs fertige Varianten zum Anpassen
9. Parametric Screw-Top Jar: One Model – Endless Jars
10. BOSL2 `threaded_rod` im Praxistest: Schraubglas aus dem 3D-Drucker

## 20 relevante Suchbegriffe

- Schraubglas 3D-Druck
- Vorratsglas 3D drucken
- Glas mit Schraubdeckel 3D-Druck
- parametrisches Schraubglas
- Gewinde 3D-Druck
- Gewinde Spiel 3D-Druck
- Screw top jar 3D print
- Screw cap container 3D print
- BOSL2 threaded rod
- OpenSCAD Gewinde
- Vorratsdose mit Gewinde
- Kaffeedose 3D-Druck
- Gewürzglas 3D-Druck
- Dose mit Rändelkappe
- Glas mit Text und Muster
- Bambu Lab P1S Vorratsglas
- MakerWorld Schraubglas
- Customizer Vorratsglas
- Mehrfarbdruck Glas
- funktionale 3D-Drucke

## 10 GitHub-Tags

- jar
- container
- screw-thread
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- kitchen

## 5 LinkedIn-Post-Ideen

1. „Vom Reibdeckel zum Gewinde“: Warum ein Schraubverschluss weniger vom Drucker
   abhängt.
2. „Wenn der Renderer das Problem ist, nicht die Geometrie“: Millionen Facetten
   durch eine verjüngte Rille.
3. „Subtrahieren oder schneiden?“: Warum das Facettenmuster ein Schnitt statt
   eines Abzugs ist.
4. „Warum Bambu Studio meine Farben ignorierte“: Die Anwendungsangabe in der
   3MF-Datei.
5. „Ein Muster-Baukasten für Gläser“: Neun Muster, ein gemeinsames Modul.

## 5 Reddit-Post-Ideen

1. r/functionalprint – „Parametric screw-top jar with a real coarse thread, nine
   surface patterns and engraved text“ mit dem Hero-Bild.
2. r/openscad – „Keeping a BOSL2 thread and hundreds of pattern cutters from
   blowing up the CSG tree“ ohne Quelltext.
3. r/BambuLab – „Why Bambu Studio dropped the colours of my OpenSCAD 3MF and how
   to get them through“.
4. r/3Dprinting – „Printing threads without supports: full-diameter thread on a
   shoulder with a 45° flare“.
5. r/3Dprinting – „Thread clearance for printed jars: what works for your
   printer?“ als Diskussionsfrage.
