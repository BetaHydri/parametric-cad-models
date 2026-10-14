# Kerzenständer 3D-drucken: parametrisch, jede Form, jede Kerze, kippsicher

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3077107-parametric-candlestick – Profil:
<https://makerworld.com/en/@BetaHydri>

![Parametric Candlestick – vier Kerzenständer in verschiedenen Formen und Oberflächen](images/01_hero.jpg)

## Motivation: Der Ständer, der zur Kerze passt

Kerzen gibt es in vielen Durchmessern, Kerzenständer meistens für einen. Wer
einen Ständer für Stabkerzen kauft, kann Teelichter oder Stumpen nicht darin
unterbringen. Gedruckt ist das Problem lösbar – aber nur, wenn die Form als
Parameter vorliegt und die Kerzenaufnahme aus dem Kerzendurchmesser berechnet
wird. Ich wollte zusätzlich, dass die Kerze **nicht kippen kann**, und dass
sich Form und Dekor trennen lassen: zuerst die Silhouette, dann die
Oberfläche.

## Funktionen im Überblick

- **Sieben Grundformen:** `Saeule`, `Kelch`, `Baluster`, `Sanduhr`, `Konisch`,
  `Vase`, `Frei`.
- **Sieben Oberflächenstile:** `Glatt`, `Riefen`, `Spiralriefen`, `Wellen`,
  `Perlen`, `Kordel`, `Facetten`.
- **Freie Maße:** Höhe, Fuß-, Taillen- und Kopfdurchmesser.
- **Kerzentyp-Voreinstellungen:** Stabkerze 22, Haushaltskerze 20, Spitzkerze
  13, Teelicht 38, Stumpen 50 und 68 mm – oder `Frei`.
- **Kippsichere Aufnahme:** Tiefe, Passung (Standard 0,6 mm) und Einführfase.
- **Optionen:** Dorn, Tropfmulde, mehrere Aufnahmen auf einem Kreis.

![Kelch mit senkrechten Riefen](images/03_kelch-riefen.jpg)

## Entwicklungsprozess

Der erste Stand stammt vom 21. Juli 2026. Das größte Lehrstück war die Vorschau:
Die Flächenreihenfolge meines Polyhedrons ergab Normalen nach innen. Das
vollständig berechnete Modell sah korrekt aus, die schnelle Vorschau dagegen war
durchsichtig, und man sah die Kerzenbohrung durch die Front. Umgedrehte
Flächenreihenfolge und ein Convexity-Wert, der mit der Riefenzahl wächst, haben
das am 3. August 2026 behoben. Am 4. August folgten acht Referenzvarianten mit
Profilen für den P1S.

## Technische Hintergründe

**Die Silhouette.** Zwei Cosinus-Übergänge von Fuß zu Taille und von Taille zu
Kopf, jeweils mit waagerechter Tangente – keine Knicke. Ein optionaler
Cosinus-Höcker ergibt den Bauch. Die Presets legen nur die Lage der Taille
und den Bauch fest; die drei Durchmesser bleiben immer unter deiner Kontrolle.
Bei `Konisch` und `Vase` ist die Taille der Mittelwert aus Fuß und Kopf, der
Taillenregler ist dort ohne Wirkung.

**Das Dekor.** Es wird als Radiusmodulation auf die Silhouette addiert: Riefen
als Sinus, Spiralriefen mit einer über die Höhe wandernden Phase, Kordel als
Sinus mit einer vollen Umdrehung über die Höhe, Perlen als achsensymmetrische
Ringe, Wellen als Kombination aus senkrechter und waagerechter Welle. An Boden
und Kopf läuft die Modulation über 6 % der Höhe auf null aus, damit Fase und
Kopfplatte glatt bleiben.

**Der Körper.** Ein Gitter aus Ringen über die Höhe und Punkten am Umfang,
zu einem geschlossenen Polyhedron verbunden. Bei `Facetten` sinkt die
Winkelauflösung auf die Kantenzahl, damit flache Seiten entstehen.

**Die Aufnahme.** Ein senkrechtes Sackloch mit Radius (Kerze + Spiel) / 2,
einer Einführfase am Mund, optional Dorn (Kegel) und Tropfmulde. Mit den
Standardwerten (Stabkerze 22 mm) ist die Bohrung Ø 22,6 mm und 22 mm tief; die
empfohlene Mindesttiefe beträgt 0,8 × Kerzendurchmesser, mindestens 15 mm.

**Die Warnungen.** Das Modell prüft Bohrungstiefe, Wand um die Bohrung
(mindestens 3 mm), zu tiefe Bohrung und Standfläche (Fuß mindestens ca.
0,35 × Höhe) und gibt Hinweise in der OpenSCAD-Konsole aus.

![Säule mit gedrehten Riefen](images/04_saeule-spirale.jpg)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für den **P1S** mit PLA gebaut (Gyroid 15 %). Der Ständer steht
aufrecht auf seiner flachen Standfläche; die Fase unten verhindert den
Elefantenfuß. Empfohlen sind 0,16–0,20 mm Layerhöhe, 3–4 Wände und 15–40 %
Infill – mehr Infill macht den Ständer schwerer und standfester.

Schlanke Formen drucken ohne Stützen. Breite Köpfe (Kelch, Vase) haben
Überhänge: Entweder Baumstützen im Slicer, oder du teilst den Ständer im Bambu
Studio mit dem Schneidwerkzeug senkrecht mittig, druckst beide Hälften mit der
Schnittfläche nach unten und klebst sie anschließend zusammen.

**Sicherheit:** Brennende Kerzen nie unbeaufsichtigt lassen. PLA erweicht ab
etwa 50–60 °C; halte genug Abstand zwischen Flamme und Kunststoff und lösche
die Kerze, bevor sie zum Halter herunterbrennt. Für mehr Hitzefestigkeit nimm
PETG, ASA oder PA.

## Einsatzideen

- Stabkerzen auf dem Esstisch, in Säule oder Kelch
- Dreiarmiger Leuchter mit `socket_count = 3`
- Teelicht- oder Stumpenhalter mit flacher Mulde
- Spitzkerzen mit Dorn
- Eine Serie aus derselben Form in verschiedenen Oberflächen

![Kelch mit drei Kerzenaufnahmen auf einem Kreis](images/05_kelch-dreifach.jpg)

## Fazit und Aufruf zum Mitmachen

Der Kerzenständer ist ein Baukasten für Dekorstücke. Wenn du ihn druckst,
freue ich mich über **Makes** mit Fotos, besonders mit eigenen Form- und
Dekor-Kombinationen. Rückmeldungen zur Passung der Kerzenaufnahme (Standard
0,6 mm) auf anderen Druckern helfen, den Standardwert zu verbessern. Schreib
einfach einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3077107-parametric-candlestick

---

## 10 SEO-Titel

1. Kerzenständer 3D-drucken: parametrisch, jede Form, jede Kerze
2. Kippsicherer Kerzenständer aus dem 3D-Drucker: tiefe Aufnahme mit Passung
3. Kerzenständer mit Riefen, Spirale oder Perlen: sieben Oberflächenstile
4. Mehrarmiger Kerzenständer 3D-Druck: mehrere Kerzen auf einem Kreis
5. Kerzenhalter für Teelicht, Stabkerze und Stumpen: Voreinstellungen im Customizer
6. Kelch, Baluster, Sanduhr, Vase: parametrische Kerzenständer-Formen
7. Kerzenständer ohne Stützen drucken oder teilen: Tipps für breite Köpfe
8. Parametric Candlestick: one model, endless designs for Bambu Lab
9. Polyhedron in OpenSCAD: warum die Vorschau durchsichtig war und wie man es behebt
10. Kerzenständer drucken: PLA, PETG oder ASA und die Hitzefrage

## 20 relevante Suchbegriffe

- Kerzenständer 3D-Druck
- Kerzenhalter 3D drucken
- Kerzenständer parametrisch
- Kerzenhalter OpenSCAD
- candle holder 3D print
- candlestick 3D print
- parametric candle holder
- Stabkerze Halter 3D-Druck
- Teelichthalter 3D-Druck
- Stumpenkerze Halter
- Spitzkerzen Halter
- Kerzenständer Riefen
- Kerzenständer Spirale
- Kerzenleuchter mehrarmig
- Bambu Lab P1S Kerzenständer
- MakerWorld Kerzenständer
- Customizer Kerzenständer
- Deko 3D-Druck
- Kerzenständer ohne Support
- Home Decor 3D-Druck

## 10 GitHub-Tags

- candle-holder
- candlestick
- decor
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- home-decor

## 5 LinkedIn-Post-Ideen

1. „Eine Silhouette aus drei Durchmessern“: Wie zwei Cosinus-Übergänge einen
   Kerzenständer ohne Knicke formen.
2. „Das durchsichtige Polyhedron“: Warum die schnelle Vorschau durchsichtig war,
   obwohl das Modell korrekt aussah.
3. „Kippsicherheit als Rechenregel“: Bohrungstiefe, Passung und Standfläche,
   die das Modell selbst prüft.
4. „Dekor als Radiusmodulation“: Riefen, Perlen und Kordel aus einer Formel.
5. „PLA und Kerzen?“: Materialwahl und Abstand zur Flamme.

## 5 Reddit-Post-Ideen

1. r/3Dprinting – „Parametric candle holder: seven shapes, seven surface
   styles, deep tip-proof socket“ mit dem Hero-Bild.
2. r/openscad – „Building a single closed polyhedron for a lathe-style body:
   winding order and preview transparency“, ohne Quelltext.
3. r/BambuLab – „Splitting a wide-headed candle holder with the cut tool
   instead of using supports“.
4. r/functionalprint – „Candle holder socket sizing: candle diameter plus
   0.6 mm clearance“ als Diskussionsfrage.
5. r/3Dprinting – „Which filament do you use for candle holders: PLA, PETG or
   ASA?“ als Diskussionsfrage.
