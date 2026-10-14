# Napfständer für Hund und Katze 3D-drucken: parametrisch, mit Schwalbenschwanz-Teilung für jedes Druckbett

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3136049-parametric-dog-and-cat-bowl-stand – Profil:
<https://makerworld.com/en/@BetaHydri>

![Raised Pet Feeder – Ein-Napf- und Zwei-Napf-Ständer auf einem Küchenboden](images/01_hero.png)

## Motivation: Ein Ständer, der zum Tier passt – und aufs Druckbett

Erhöhte Futterständer sind sinnvoll, aber die Maße stimmen selten: Der Napf ist
einen Zentimeter zu groß, der Ständer für die Katze zu hoch, der für den
Retriever zu niedrig. Ein eigener Ständer lässt sich im 3D-Druck beliebig
anpassen, hat aber ein praktisches Problem: Ein Doppelständer ist breiter als
fast jedes Druckbett. Der **Parametric Dog & Cat Bowl Stand** löst beides mit
einem Modell: Maße im MakerWorld-Customizer einstellen, und wenn der Ständer
nicht aufs Bett passt, teilt ihn das Modell selbst mit einem
Schwalbenschwanz.

## Funktionen im Überblick

- **Ein oder zwei Näpfe:** `bowl_count` wählt Einzelnapf oder Doppelständer.
- **Zwei Napfgrößen:** `bowl2_diameter` setzt die zweite Mulde unabhängig, etwa
  großer Futternapf plus kleiner Wassernapf.
- **Freie Maße:** Plattenlänge (auch automatisch), Breite, Dicke, Gesamthöhe,
  Beinspreizung, Fußlänge und Rundungen.
- **Mulden mit 45°-Wand:** stützfrei druckbar, abgerundeter Rand, flacher Boden
  ohne Mittelzapfen.
- **Druckerwahl:** `printer` (P1S/P2S, H2C, H2D) und `split_mode` entscheiden,
  ob der Ständer geteilt wird.
- **Schwalbenschwanz mit einstellbarem Spiel:** `dovetail_play` (Standard
  0,15 mm je Seite), `dovetail_depth`, `dovetail_neck`, `dovetail_tip`.
- **Prüfungen im Modell:** Läuft die Trennnaht durch eine Mulde, stoppt das
  Modell mit einer klaren Meldung.
- **Acht fertige Varianten** für Katze sowie kleine, mittlere und große Hunde.

![Ein- und Zwei-Napf-Ständer](images/04_ein-und-zwei-napf-variante.png)

## Entwicklungsprozess

Ausgangspunkt war mein eigener Fusion-360-Entwurf, den ich mit OCP
(OpenCascade für Python) vermessen habe: Plattendicke 18 mm, Beine unter 30°
zur Senkrechten, Mulde mit 45°-Wand und gerundetem Rand. Diese Werte stehen
heute als Voreinstellungen im Customizer. Die ersten Dateien stammen vom
5. August 2026.

Der interessanteste Fehler zeigte sich bei der Teilung: Die Trennnaht liegt in
der Plattenmitte. Bei einem einzelnen Napf sitzt die Mulde genau dort. Unter
der Mulde ist die Platte nur noch `board_thick` − `bowl_depth` dick – für den
Schwalbenschwanz viel zu wenig. Das Modell wäre kaputt gewesen. Seitdem prüft
eine Bedingung, ob die Naht weit genug von jeder Mulde entfernt liegt, und
gibt sonst einen Hinweis aus, was zu tun ist (größeren Drucker wählen,
Abstand erhöhen, Teilung abschalten).

Bei den Bildern gab es einen weiteren Lerneffekt: Eine KI-gestützte
Bildvariante erfand ein Loch statt der flachen Mulde. Das habe ich verworfen
und rendere die Bilder seitdem aus der echten Geometrie.

## Technische Hintergründe

**Das Seitenprofil.** Platte und beide Beine sind ein 2D-Polygon im
Seitenschnitt, das auf die Plattenbreite extrudiert wird. Die äußere Fußkante
ergibt sich aus der halben Plattenlänge plus `total_height` · `tan(leg_splay)`.
Bei 30° entsteht der 120°-Innenwinkel des Originals.

**Die Mulde.** Das Profil besteht aus einem Rundungsbogen am Rand (tangential
zur Oberfläche), einem geraden Kegel mit dem Wandwinkel und einem Bogen an der
Bodenkante. Der Boden bleibt flach; das Profil reicht über die Drehachse hinaus
und wird beschnitten, damit kein Mittelzapfen entsteht. Die Tiefe wird so
begrenzt, dass mindestens 20 % des Radius als flacher Boden bleiben.

**Der Schwalbenschwanz.** Das Trapez ist an der Naht schmal und an der Spitze
breit; dadurch sperrt es das Auseinanderziehen. Die Zunge hat nur an der
hinteren Einführseite eine 45°-Fase, die Vorderseite bleibt bündig. Die
Hälften werden in Y-Richtung zusammengeschoben.

**Die Druckausrichtung.** Die Hälften liegen auf der Stirnseite. So steht der
Schwalbenschwanz senkrecht, und die große Plattenunterseite ist keine Brücke.

**Zwei Napfgrößen.** Die Muldengeometrie ist eine Funktion des Durchmessers.
Die Plattenlänge richtet sich nach dem größeren Napf.

![Split-Vorschau mit Schwalbenschwanz](images/05_split-vorschau-schwalbenschwanz.png)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind mit **Bambu PLA Basic** gebaut und im Slicer getestet:
0,20 mm Layerhöhe, Gyroid 15 %, Wandstärken 2, 3 und 4. Je nach Variante sind
sie für P1S oder H2C erstellt. Für ein tragendes Teil empfehle ich 3–4 Wände
und 20–40 % Infill. Stützen sind nicht nötig.

Beim Zusammenbau schiebst du die Hälften von der Rückseite her zusammen. Das
Spiel von 0,15 mm je Seite ergibt in PLA einen festen Sitz; bei PETG erhöhst du
`dovetail_play` auf rund 0,20 mm. Wer die Verbindung dauerhaft haben möchte,
setzt einen Tropfen Kleber.

Kommen beide Hälften als ein Objekt, trennst du sie im Slicer per Rechtsklick
**Teilen → In Objekte**.

## Einsatzideen

- Ständer in Katzenhöhe (45 mm) mit kleiner Mulde
- Ständer nach Schulterhöhe des Hundes
- Futternapf und Wassernapf in zwei Größen
- Ständer für einen vorhandenen Napf: Randdurchmesser messen, eintragen
- Doppelständer auf einem 256-mm-Bett durch automatische Teilung

![Studio-Render des Zwei-Napf-Ständers](images/02_studio-zwei-naepfe.png)

## Fazit und Aufruf zum Mitmachen

Der Ständer ist ein Baukasten für Näpfe aller Größen. Wenn du ihn druckst,
freue ich mich über **Makes** mit Fotos, besonders mit eigenen Napfmaßen und
anderen Druckern. Rückmeldungen zum Spiel des Schwalbenschwanzes in PETG oder
anderen Materialien helfen, die Voreinstellung zu verbessern. Schreib einfach
einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3136049-parametric-dog-and-cat-bowl-stand

---

## 10 SEO-Titel

1. Napfständer 3D-drucken: parametrisch für Hund und Katze (OpenSCAD)
2. Erhöhter Futternapf-Ständer für Bambu Lab: Maße im Customizer einstellen
3. Hundenapf-Ständer größer als das Druckbett: Teilung mit Schwalbenschwanz
4. Futterstation für Katze und Hund 3D-drucken: ein oder zwei Näpfe
5. Napfständer nach Maß: Napfdurchmesser, Höhe und Beinwinkel einstellen
6. Futternapf groß, Wassernapf klein: zwei Napfgrößen in einem Ständer
7. Stützfrei drucken: 45°-Mulden und Schwalbenschwanz auf der Stirnseite
8. Schwalbenschwanz-Verbindung im 3D-Druck: Spiel für PLA und PETG
9. Parametric Dog & Cat Bowl Stand: One Model – Any Size
10. Napfständer aus dem 3D-Drucker: acht Varianten von Katze bis großer Hund

## 20 relevante Suchbegriffe

- Napfständer 3D-Druck
- Hundenapf Ständer 3D drucken
- Futterstation Katze 3D-Druck
- erhöhter Futternapf
- Hunde-Futterbar 3D-Druck
- Napfhalter parametrisch
- Raised pet feeder 3D print
- Dog bowl stand 3D print
- Cat bowl stand
- Elevated dog feeder
- Dovetail joint 3D print
- Schwalbenschwanz 3D-Druck
- Napfständer Bambu Lab
- MakerWorld Napfständer
- OpenSCAD Customizer Ständer
- Doppelnapf Ständer
- Futternapf Wassernapf Ständer
- Möbel 3D-Druck Hund
- Haustierzubehör 3D-Druck
- funktionale 3D-Drucke

## 10 GitHub-Tags

- pet
- dog
- cat
- feeder
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer

## 5 LinkedIn-Post-Ideen

1. „Ein Modell, jede Napfgröße“: Wie Parameter statt Skalieren den Ständer für
   Katze und Hund liefern.
2. „Teilen, ohne die Verbindung zu zerstören“: Warum die Trennnaht gegen die
   Napfmulde geprüft wird.
3. „Vom Fusion-Entwurf zum Customizer“: Ein Bauteil mit OCP vermessen und
   parametrisch nachbauen.
4. „Stützfrei auf der Stirnseite“: Warum die Druckausrichtung die Konstruktion
   bestimmt.
5. „Wenn die KI ein Loch erfindet“: Warum Produktbilder aus der echten
   Geometrie berechnet werden.

## 5 Reddit-Post-Ideen

1. r/functionalprint – „Parametric raised pet feeder with dovetail split, fits
   any build plate“ mit dem Hero-Bild.
2. r/openscad – „Checking a split seam against a bowl recess with assert():
   fail early with a useful message“ ohne Quelltext.
3. r/BambuLab – „Printing a feeder wider than the P1S bed: halves on the front
   face, no supports“.
4. r/3Dprinting – „Dovetail clearance for PLA vs PETG: what play works for
   you?“ als Diskussionsfrage.
5. r/dogs bzw. r/cats – „Printed an elevated feeder sized to our bowls“ mit
   dem Studio-Render (nur wenn das Forum Selbstvorstellungen erlaubt).
