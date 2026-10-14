# Eierbecher 3D-drucken: parametrisch, für jede Eigröße und mit 13 Texturen

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3137233-ultimate-parametric-egg-cup – Profil:
<https://makerworld.com/en/@BetaHydri>

![Parametric Egg Cup – Tumbler, Pedestal und Weinglas-Form](images/01_hero.png)

## Motivation: Ein Eierbecher, der zum Ei passt

Ein Eierbecher gehört zu den ersten Dingen, die man im 3D-Druck ausprobiert.
Ein gutes Modell ist trotzdem selten. Entweder passt er nur zu einer
Eigröße, oder der Boden ist spitz, sodass das Ei kippelt, oder die Oberfläche
ist glatt und langweilig. Der **Parametric Egg Cup** ist mein Versuch, daraus
ein Werkzeug zu machen: Du gibst Eigröße, Form und Struktur vor, das Modell
rechnet den Rest.

## Funktionen im Überblick

- **Drei Körperformen:** `tumbler` (Fass), `pedestal` (klassisch mit Fuß und
  Taille) und `wineglass` (Pokal mit Stiel und Fuß).
- **Eigröße als Vorgabe:** `egg_size` mit `S` (ca. 40 × 52 mm), `M` (43 × 55),
  `L` (45 × 58), `XL` (48 × 62) oder `custom` mit eigenem Durchmesser und
  eigener Länge.
- **13 Wandstrukturen:** vertikale Flutes (erhaben oder genutet), vertikale
  Rippen, horizontale Ringe (erhaben oder genutet), 45°-Diagonale (erhaben oder
  genutet), 45°-Kreuzschraffur, einstellbare Spirale, Chevron, Noppenraster und
  Facetten – plus eine glatte Variante.
- **Reliefs ohne Durchbrüche:** Der Becher bleibt dicht und lässt sich
  abwischen.
- **Auslaufende Textur:** `fade_top` und `fade_bottom` (Standard je 9 mm) lassen
  die Struktur weich in die glatten Bereiche übergehen.
- **Texturband:** Mit `margin_bottom` und `margin_top` legst du fest, wo die
  Struktur beginnt und endet.
- **Zweifarbige Textur** als Option.
- **Stützenfrei,** aufrecht gedruckt, auch als Set (`set_2`, `set_4`).

![Tumbler-Becher mit erhabenen vertikalen Flutes](images/02_tumbler-flutes.png)

## Entwicklungsprozess

Ausgangspunkt war die Frage, wie man bei einem Becher eine strukturierte Wand
bekommt, ohne dass sie bricht. Aus der Antwort wurde eine Reliefbibliothek, die
zu einem Becher mit drei Formen und 13 Strukturen wuchs. Dazwischen lagen ein
paar Lehrstücke:

Die Rundung des Cradles war zuerst linear gezeichnet und ergab einen spitzen
Boden. Das Ei lag dann auf einem Ring und wackelte. Heute folgt das Profil einer
Viertelellipse: waagerechte Tangente unten, senkrechte am Rand. Der
zweifarbige Akzent lag zuerst bündig in der Nut und flimmerte in der Vorschau
(Z-Fighting). Jetzt sitzt er leicht vertieft. Und ein harter Texturabschluss am
Rand wirkte billig – deshalb laufen die Reliefs standardmäßig aus.

Die Profile entstanden für den Bambu Lab P1S mit PLA. Beim Erzeugen blieb ein
Spiral-Render bei `$fn = 120` über eine Stunde hängen; die Profile wurden
deshalb mit `$fn = 60` gerechnet.

![Pedestal-Becher mit horizontalen Nuten](images/03_pedestal-rings.png)

## Technische Hintergründe

**Das Cradle.** Aus dem Eidurchmesser ergibt sich der Cradle-Radius
`egg_D / 2 − cradle_inset / 2`, aus der Eilänge die Tiefe
`egg_L × cradle_depth_frac`. Für ein M-Ei sind das mit den Standardwerten
20,75 mm Radius und 23,1 mm Tiefe. Der Außenradius am Rand kommt dazu aus
Cradle-Radius, `wall` und `rim_extra`.

**Reliefs mit konstanter Tiefe.** Ein Muster flach in eine gewölbte Wand zu
schneiden, funktioniert nicht: An der dicksten Stelle des Bauchs würde der
Schnitt einen Hohlraum in der Wand lassen. Das Modell bildet deshalb eine
Schale, die der Kontur folgt, und schneidet das Muster nur mit dieser Schale.
Nuten sind die Schnittmenge aus innerer Schale und Muster, erhabene Rippen die
aus äußerer Schale und Muster. So kann die Textur nie durch die Wand brechen.

**Diagonalen und Spiralen.** Ein senkrechter Balken wird mit dem Twist von
`linear_extrude` verdreht. Der Winkel ergibt sich aus dem Umfang auf Höhe der
Textur, sodass die Linie bei 45° liegt. Kreuzschraffur ist die Vereinigung aus
Rechts- und Linksdrehung, Chevron die untere Hälfte in die eine und die obere
in die andere Richtung.

**Zweifarb-Akzent.** Bei erhabenen Reliefs ist die Rippe ein eigener Körper.
Bei vertieften Reliefs sitzt der Akzent 0,35 mm unter der Oberfläche und hat
0,35 mm Abstand zu den Nutwänden. Damit fallen keine Flächen zusammen.

**Prüfungen.** Eingebaute `assert`-Bedingungen verhindern unsinnige
Kombinationen, zum Beispiel einen Boden unter 4 mm, eine Randwand unter 1,2 mm,
Nuten, die in den Cradle durchbrechen würden, oder einen Weinglas-Fuß, der für
die Schale zu schmal ist.

![Weinglas-förmiger Eierbecher mit Rippen](images/04_wineglass-ribs.png)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für den **P1S** mit **Bambu PLA Basic** gebaut und im Slicer
getestet: 0,20 mm Layerhöhe, drei Wände, 15 % Gyroid. Die Orientierung ist
aufrecht, Öffnung nach oben, ohne Stützen; die Fase an der Unterkante hilft
gegen Elefantenfuß. Für schärfere Texturen kannst du auf 0,12–0,16 mm
Layerhöhe gehen. Der Infill betrifft nur die massive Basis und die Randbänder.

Ein ehrlicher Hinweis zum Thema Lebensmittel: Ein FDM-Teil ist nicht automatisch
lebensmittelecht. Die Modellbeschreibung empfiehlt einen lebensmitteltauglichen
Einsatz oder eine dünne lebensmittelechte Beschichtung.

Für die **zweifarbige Textur** gibt es drei Wege: die Struktur im Slicer mit dem
Farbmal-Werkzeug füllen, `part = print_2color` wählen und den STL direkt aus der
OpenSCAD-Vorschau exportieren (ohne F6/Render), oder im MakerWorld-Customizer
online das zweifarbige Modell erzeugen lassen. Der Druck dauert wegen der
Farbwechsel länger.

## Einsatzideen

- Frühstückstisch-Set mit vier gleichen Bechern (`set_4`)
- Fass-Becher mit Diagonal-Nuten in Akzentfarbe als Geschenk
- Pokal-Form für Brunch und Ostertisch
- Texturband für einen glatten Fuß und Kragen
- Eigene Eigröße über `custom`

![Tumbler-Becher mit Diagonalnuten](images/05_tumbler-diagonal.png)

## Fazit und Aufruf zum Mitmachen

Der Egg Cup ist als Baukasten gedacht: Eigröße einstellen, Form wählen,
Struktur aussuchen, drucken. Wenn du das Modell druckst, freue ich mich über
**Makes** mit Fotos – besonders über Zweifarb-Varianten und Ergebnisse mit
anderen Eigrößen. Rückmeldungen zu Texturen, die dir fehlen, gern als Kommentar
auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3137233-ultimate-parametric-egg-cup

---

## 10 SEO-Titel

1. Eierbecher 3D-drucken: parametrisch für jede Eigröße (OpenSCAD)
2. Parametrischer Eierbecher für Bambu Lab: Tumbler, Pedestal und Weinglas
3. Eierbecher mit Textur 3D-Druck: 13 Reliefs im MakerWorld-Customizer
4. 3D-gedruckter Eierbecher ohne Stützen: aufrecht drucken, sofort nutzen
5. Eierbecher in Zweifarb-Optik: Textur als Akzentfarbe drucken
6. Egg Cup 3D Print: parametrisches Modell mit Eigröße S bis XL
7. Eierbecher selbst gestalten: Form, Struktur und Eigröße einstellen
8. 45°-Diagonal-Nuten, Flutes und Ringe am Eierbecher (OpenSCAD)
9. Eierbecher-Set drucken: vier gleiche Becher auf einer Platte
10. Relief-Texturen in OpenSCAD: konstante Tiefe auf gewölbten Wänden

## 20 relevante Suchbegriffe

- Eierbecher 3D-Druck
- Eierbecher 3D drucken
- parametrischer Eierbecher
- Egg Cup 3D Print
- Eierbecher OpenSCAD
- Eierbecher MakerWorld
- Eierbecher Bambu Lab
- Eierbecher P1S PLA
- Eierbecher mit Textur
- Eierbecher Weinglas-Form
- Eierbecher Pedestal
- Eierbecher Set drucken
- Eierbecher zweifarbig
- Eierbecher Zweifarb-Druck
- Eierbecher ohne Stützen
- Eierbecher Customizer
- OpenSCAD Relief Textur
- OpenSCAD Diagonal Nuten
- 3D-Druck Küche
- funktionale 3D-Drucke

## 10 GitHub-Tags

- egg-cup
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- kitchen
- texture
- functional-print

## 5 LinkedIn-Post-Ideen

1. „Warum ein Eierbecher ein gutes Parametrik-Beispiel ist“: Eigröße als
   Eingabe, Cradle-Radius und -Tiefe als abgeleitete Größen.
2. „Konstante Tiefe auf gewölbter Fläche“: Die Oberflächen-Schale als Trick,
   damit Texturen nie durch die Wand brechen.
3. „Von der Spitze zur Viertelellipse“: Wie ein falsch gezeichnetes Cradle
   ein Ei zum Kippeln brachte.
4. „Foolproof-Parameter“: Wie `assert`-Prüfungen im Customizer
   Fehlbedienung abfangen.
5. „Ein Modell, drei Formen, 13 Texturen“: Aufbau einer kleinen
   Reliefbibliothek in OpenSCAD.

## 5 Reddit-Post-Ideen

1. r/3Dprinting – „Parametric egg cup with 13 relief textures, prints upright
   without supports“ mit dem Hero-Bild.
2. r/openscad – „Constant-depth relief on a curved wall via a surface shell“:
   Erklärung des Schalen-Ansatzes, ohne Quelltext.
3. r/BambuLab – „Two-colour texture on a single-nozzle printer: paint vs. export“
   mit den drei Wegen für die Zweifarb-Textur.
4. r/functionalprint – „Egg cup that fits S to XL eggs – cradle derived from egg
   size“.
5. r/3Dprinting – „Texture band on a tumbler: `margin_bottom` and
   `margin_top`“ mit den Diagonal-Nuten.
