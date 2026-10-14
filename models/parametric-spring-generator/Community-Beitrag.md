# Federn 3D-drucken: Serpentine, Druckfeder, Blattfeder und Spirale parametrisch

👉 **MakerWorld-Link:** <https://makerworld.com/en/models/3188130-parametric-springs-with-flexible-mounting-options> – Profil:
<https://makerworld.com/en/@BetaHydri>

![Parametric Spring Generator – vier Federtypen](images/01_hero.png)

## Motivation: Federn mit der passenden Befestigung

Ich brauchte Federn mit unterschiedlichen Befestigungsarten und fand kein
parametrisches Modell, das das flexibel abdeckt. Es gab Einzelmodelle für einen
Federtyp mit festen Anschlüssen, aber nichts, bei dem ich Zapfen, Schraubauge,
Montageplatte oder Verankerungsring wählen kann. Also entstand der **Parametric
Spring Generator**: vier Federfamilien in einer Datei, mit einer gemeinsamen
Gruppe für Befestigungslöcher.

Dazu kam die Druckorientierung. Gedruckter Kunststoff ist entlang der Schichten
stabil und quer dazu schwach. Eine Feder muss deshalb so liegen oder stehen, dass
die Biegung die Schichten nicht auseinanderzieht. Das war von Anfang an
Entwurfsgrundlage, nicht ein Slicer-Detail danach.

## Funktionen im Überblick

- **Serpentinenfeder:** runde oder eckige Windungen (`ser_style`), Endkappen,
  Schwalbenschwanz-Zapfen, optional mit Bohrung in den Zapfen.
- **Druckfeder:** rechteckiges Bandprofil, plan geschliffene, offene oder mit
  Montageplatte versehene Enden; Länge über Windungszahl (`coil_turns`) oder
  Zielhöhe (`coil_len`).
- **Print-in-Place-Stützrippe:** Die Druckfeder druckt stehend ohne
  Slicer-Support und trägt ihre eigene, nach dem Druck entfernbare Stütze.
- **Blattfeder:** gewölbte Klinge mit massiven Befestigungsaugen.
- **Spiralfeder:** flache archimedische Spirale mit Nabe und Verankerungsring,
  Stiftlasche oder Haken.
- **Befestigungslöcher wählbar:** glatt oder gedrucktes metrisches Gewinde M2–M6.
- **Zwei-Material-Export:** Feder, Stütze und Abreißnadeln als getrennte
  Farbgruppen (`print_multicolor`).
- **Montagehilfe** für die Serpentine.
- **Zehn Referenzvarianten** mit Profilen für den Bambu Lab P2S (PETG).

![Druckfeder mit Montageplatte](images/03_druckfeder.jpg)

## Entwicklungsprozess

Am 18. August 2026 entstanden Modell, Profile und Beschreibung. Die Serpentine
basiert auf einem bewährten flachen Muster, die Druckfeder auf einer gedruckten
Probe: Bandbreite, ein Trennabstand der Stützrippe von rund 0,4 mm und die
Einrückung der Stütze von den Enden wurden von dort übernommen und im Modell
parametrisiert. Im Praxistest stand die Feder ohne Slicer-Support auf dem
Bett, die Stütze ließ sich anschließend mit einem stumpfen Messer lösen, ohne
die Feder zu beschädigen.

Ein Entwurfsentscheid war, auf Gewindekanäle für waagerechte Bohrungen zu
verzichten. Ein seitlich gedrucktes Gewinde wird rau; stattdessen bekommt das
Zapfenloch eine Tropfenform und, wenn „threaded“ gewählt ist, ein Kernloch für
selbstschneidende Schrauben.

## Technische Hintergründe

**Serpentine.** Die Mittellinie ist eine Punktfolge aus waagerechten Zeilen und
Halbkreis-Wendungen. Benachbarte Punkte werden mit Kreisprofilen verhüllt (Hull)
und einmal extrudiert, das ergibt ein einziges Band. Der Zeilenabstand ist das
Doppelte der Drahtstärke, die Lücke also so breit wie der Draht. Härte
bestimmen vor allem `ser_wire` und `ser_depth`; mehr Windungen machen die Feder
weicher.

**Druckfeder.** Das Drahtprofil ist ein gefastes Rechteck mit senkrechten Wänden.
Die Steigung ist `max(coil_gap + coil_wire_h, coil_wire_h + 0,4)`, damit
Windungen nie verschmelzen. Die Endwindungen laufen flach aus, danach werden Ober-
und Unterseite plan abgeschnitten.

**Stützrippe.** Eine zweite Helix liegt in jeder Lücke, hält je Seite
`coil_clearance` Abstand (Standard 0,4 mm) und folgt der lokalen Steigung. Dadurch
ist fast der ganze Querschnitt je Schicht massiv: kein Durchhängen. Sie ist ein
getrennter Körper; dünne Abreißnadeln halten sie beim Druck in Position. Die Rippe
entsteht nur, wenn `coil_gap` − 2 × `coil_clearance` mindestens 0,4 mm beträgt.

**Blattfeder.** Der Bogen ist ein Kreisabschnitt mit dem Radius
R = (Länge² / 4 + Höhe²) / (2 × Höhe). Die Augen sitzen auf einem massiven Pad
(Lochdurchmesser plus 4 mm), damit die Bohrung die dünne Klinge nie
durchtrennt. Im Druck liegt der Bogen in der Ebene und die Breite steht nach
oben, die Biegung läuft entlang der Schichten.

**Spirale.** Der Radius wächst um `spiral_wire + spiral_gap` je Windung. Der
Spalt bleibt offen, damit benachbarte Windungen nicht verschmelzen. Der
Verankerungsring verschmilzt das freie Ende mit einem konzentrischen Ring.

**Gewinde.** Das gedruckte Innengewinde ist ein verdrehter Zahnquerschnitt mit
Einlaufkonus. Es klappt nur bei senkrechter Achse sauber, deshalb nutzen
Blattfeder-Auge, Druckfeder-Platte und Spiral-Nabe echte Gewinde, der waagerechte
Zapfen nicht.

![Blattfeder mit Befestigungsaugen](images/04_blattfeder.jpg)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für den **P2S** mit **PETG** erstellt: 4 Wände, Gyroid 40 %.
Kein PLA für arbeitende Federn, es ist zu spröde. TPU liefert weiche,
rückfedernde Federn.

- **Serpentine und Blattfeder** liegen flach, 0,15–0,20 mm Layerhöhe, 3–4 Wände.
- **Druckfeder** stehend, 0,10–0,20 mm, hoher Infill, langsam, 5–8 mm Brim. Nie
  liegend drucken, nie Slicer-Support aktivieren.
- **Spirale** flach, 0,10–0,15 mm, langsam.
- **Zwei-Material-Trick:** Feder in PETG oder TPU, Stütze und Nadeln in PLA. PLA
  haftet schlecht an PETG über den 0,4-mm-Abstand und löst sich leichter. Den STL
  dafür direkt aus der OpenSCAD-Vorschau exportieren, ohne F6/Render.
- **Plastik kriecht:** Federn nicht dauerhaft voll zusammengedrückt lagern.
- **Federrate:** Die Metallfeder-Formel gilt nicht. Mit Gewichten belasten
  (F = m · 9,81 N), Weg x ablesen, k = F / x.

## Einsatzideen

- Rückstellfedern in Klappen und Gehäusen (Serpentine)
- Federnde Stößel und Taster (Druckfeder mit Montageplatte)
- Andruck- und Klemmelemente (Blattfeder)
- Torsionsrückstellung auf einer Achse (Spirale mit Ring)
- Prototypen im Homelab: Blenden, Klappen, federnde Kabelhalter

![Spiralfeder mit Verankerungsring](images/05_spiralfeder.jpg)

## Fazit und Aufruf zum Mitmachen

Der Generator ist ein Baukasten für Federn mit passender Befestigung. Wenn du
eine Feder druckst, freue ich mich über **Makes** mit Fotos. Besonders hilfreich
sind Messwerte: welche Federrate du mit welchen Parametern, welchem Material und
welchem Drucker erreichst. Schreib einfach einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** <https://makerworld.com/en/models/3188130-parametric-springs-with-flexible-mounting-options>

---

## 10 SEO-Titel

1. Federn 3D-drucken: parametrischer Generator für vier Federtypen
2. Druckfeder 3D-drucken ohne Support: stehend mit Print-in-Place-Stütze
3. Serpentinenfeder 3D-Druck: flache Feder mit Schwalbenschwanz-Zapfen
4. Blattfeder 3D-drucken: Bogenhöhe und Dicke im Customizer einstellen
5. Spiralfeder und Torsionsfeder drucken: Nabe, Ring, Haken oder Lasche
6. Gedruckte Federn: PETG oder TPU statt PLA, und warum
7. Gedrucktes Gewinde M2 bis M6: Befestigungslöcher für 3D-gedruckte Federn
8. Feder mit Montageplatte 3D-drucken: Schraubkanal und geschlossener Deckel
9. Parametric Spring Generator: Four Spring Types, Print-Ready Flex
10. Zwei-Material-Druck für Federn: Stützrippe in PLA, Feder in PETG

## 20 relevante Suchbegriffe

- Feder 3D-Druck
- Druckfeder 3D drucken
- Blattfeder 3D-Druck
- Spiralfeder 3D-Druck
- Torsionsfeder 3D-Druck
- Serpentinenfeder
- parametrische Feder OpenSCAD
- 3D printed spring
- Compression spring 3D print
- Leaf spring 3D print
- Torsion spring 3D print
- Print in place spring
- Feder ohne Support drucken
- PETG Feder 3D-Druck
- TPU Feder 3D-Druck
- gedrucktes Gewinde M3
- Federrate 3D-Druck messen
- MakerWorld Feder
- Bambu Lab P2S Feder
- funktionale 3D-Drucke

## 10 GitHub-Tags

- spring
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- functional-print
- compression-spring
- print-in-place

## 5 LinkedIn-Post-Ideen

1. „Warum PLA keine Feder sein kann“: Schichten, Spröde und Kriechen am Beispiel
   gedruckter Federn.
2. „Support, der Teil des Modells ist“: die Print-in-Place-Stützrippe der
   Druckfeder und der Zwei-Material-Trick.
3. „Das Loch, das waagerecht druckt“: Tropfenform statt Gewinde und warum.
4. „Eine Gruppe Befestigungslöcher für vier Federtypen“: Modularität in einem
   parametrischen Modell.
5. „Federrate messen statt rechnen“: Warum die Metallfeder-Formel für gedruckte
   Bänder nicht passt.

## 5 Reddit-Post-Ideen

1. r/3Dprinting – „Parametric spring generator: serpentine, compression, leaf and
   spiral in one customizer model“ mit dem Hero-Bild.
2. r/functionalprint – „Printing a compression spring standing, with its own
   removable support helix“ mit dem Praxisfoto.
3. r/openscad – „Building a helical ribbon spring with a ramped flat end:
   integrating the pitch function“ (ohne Quelltext, nur Ansatz).
4. r/BambuLab – „Two-material trick: PETG spring, PLA support helix that peels
   away“.
5. r/3Dprinting – „What spring rate do you get from printed PETG springs? Share
   your k = F / x numbers“ als Diskussionsfrage.
