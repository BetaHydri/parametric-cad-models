# Print-in-Place Scharnier parametrisch drucken: Der Hinge Designer für Bambu Lab

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3160240-parametric-print-in-place-hinge-generator – Profil:
<https://makerworld.com/en/@BetaHydri>

![Print-in-Place Hinge Designer – vier Scharnier-Varianten](images/01_hero.png)

## Motivation: Ein Scharnier, das sofort funktioniert

Wer Klappen, Deckel oder Blenden druckt, braucht früher oder später ein
Scharnier. Die Standardlösung ist Zukaufteile plus Schrauben und Bohrungen.
Ein **Print-in-Place-Scharnier** spart das: Beide Flügel und der Pin entstehen
in einem Job, ohne Stützen und ohne Montage. Der Haken ist das Spiel. Zu wenig
Luft, und das Gelenk verschweißt; zu viel, und es wackelt.

Der **Parametric Print-in-Place Hinge Designer** löst das über Parameter. Länge,
Flügelbreite, Festigkeit, Spiel und Befestigungsbild stellst du im
MakerWorld-Customizer ein, statt ein starres Modell zu skalieren.

## Funktionen im Überblick

- **Flach und offen gedruckt:** Beide Flügel liegen auf dem Bett, die Achse
  verläuft parallel dazu. Keine Stützen, keine Nacharbeit außer einem ersten
  Hin- und Herbewegen.
- **Drei Festigkeits-Presets:** `simple` (Pin 3 mm), `standard` (Pin 4 mm) und
  `heavy` (Pin 6 mm), dazu `custom` mit eigenen Werten für Pin, Wand,
  Plattenstärke und Knuckle-Anzahl.
- **Einstellbares Spiel:** `hinge_gap` (Standard 0,4 mm) und `axial_gap`
  (Standard 0,4 mm) passen das Gelenk an Drucker und Filament an.
- **Frei definierbares Montagebild:** Lochraster mit Spalten und Reihen,
  Senkung für Senkkopfschrauben, Langlöcher quer oder längs zur Achse.
- **Druckerabhängige Länge:** Über `printer` wird die Länge auf den Bauraum
  begrenzt.
- **Zweifarb-Optionen:** Zweifarbige Vorschau und ein Druckmodus, bei dem jeder
  Flügel ein eigenes Filament bekommt.
- **Fünf fertige Varianten** mit Bambu-Studio-Profilen für P2S und PETG.

![Flache Druckanordnung beider Flügel](images/03_vorschau-flach.png)

## Entwicklungsprozess

Das Scharnier ist Teil einer Reihe parametrischer OpenSCAD-Modelle. Die
Montageplatten übernehmen die Logik der DIN-Rail-Adapter-Platte: ein Raster aus
Löchern, wahlweise mit Senkung, oder Langlöcher in beliebiger Ausrichtung.

Zum Modell gehören die Presets für unterschiedliche Lasten, der
Drucker-Parameter für die Länge und die zweifarbigen Vorschauen. Die
Vorschau-Modi sind absichtlich nicht druckbar und zeigen deshalb ein rotes
„NOT FOR PRINTING“-Banner, damit niemand versehentlich die gefaltete Vorschau
slicet.

## Technische Hintergründe

Hinter dem Modell steckt eine überschaubare Geometrie mit einigen wichtigen
Regeln:

**Alternierende Knuckles.** Die Knuckles werden abwechselnd dem linken und dem
rechten Flügel zugeordnet. Bei einer ungeraden Anzahl liegen beide Enden am
linken Flügel. Der Pin gehört zum linken Flügel und läuft durchgehend; der
rechte Flügel erhält eine Bohrung mit Pin-Radius plus `hinge_gap`.

**Freistellung statt Verschmelzen.** Jeder Flügel wird dort ausgespart, wo die
Knuckles des anderen Flügels laufen. Die Freistellung deckt auch die axialen
Lücken ab. Ohne das würden die Stirnflächen der Knuckles in die Nachbarplatte
stoßen und verschweißen.

**Nahtspalt zwischen den Platten.** Die beiden Plattenkanten an der Achse
werden um `hinge_gap / 2` zurückgesetzt. Sonst berühren sie sich in jeder
Axiallücke und werden zu einem Teil.

**Pin zuletzt.** Der Pin wird erst nach dem Ausklinken hinzugefügt und bleibt
dadurch durchgehend und intakt.

**Achshöhe gleich Barrel-Radius.** Der Barrel liegt tangential auf dem Bett,
die Platten stehen bei Z = 0. Der Spalt entsteht horizontal zwischen den
Schichten, und der obere Knuckle überbrückt ihn.

Die Knuckle-Anzahl folgt aus der Länge und der Ziel-Teilung des Presets
(`simple` 14 mm, `standard` 10 mm, `heavy` 8 mm), gerundet und auf eine ungerade
Zahl aufgerundet. So bleiben die Pin-Brücken auch bei langen Scharnieren kurz.
Beispiele: `standard` bei 60 mm ergibt 7 Knuckles, `heavy` bei 80 mm ergibt 11.

Eingebaute Prüfungen verhindern unsinnige Kombinationen: Barrel-Wand unter
0,8 mm, Plattenstärke unter 1,2 mm, Knuckles kürzer als 1,5 mm oder zu schmale
Platten für das gewählte Lochbild.

Die Geometrie wurde geprüft: Jeder Flügel ist ein wasserdichter Einzelkörper
(`Volumes: 2` in OpenSCAD). Eine Fit-Prüfung bestimmt den Mindestabstand der
Flügel (muss größer als 0,05 mm sein) und das Schnittvolumen (muss kleiner als
0,05 mm³ sein).

![Gefaltete Vorschau der Flügel](images/02_vorschau-gefaltet.png)

## Druck-Erfahrungen und Empfehlungen

Die mitgelieferten Profile sind für **Bambu Lab P2S** mit **Bambu PETG Basic**
gebaut und im Slicer getestet: 0,20 mm Layerhöhe, Gyroid-Infill mit 15 %,
wahlweise 2, 3 oder 4 Wände. Die Empfehlung ist 3 Wände; 4 Wände eignen sich für
belastete Scharniere.

Aus den Auslegungsreferenzen des Modells gelten diese Spielwerte als
Ausgangspunkt:

- **PLA:** 0,30–0,40 mm
- **PETG:** 0,40–0,50 mm

Zu klein, und das Scharnier verschweißt; zu groß, und es wackelt. Deshalb gilt:
Zuerst den 30-mm-Testcoupon drucken, `hinge_gap` einstellen, dann das große Teil
drucken. Nach dem Druck das Gelenk einmal vorsichtig hin- und herbewegen.

Zur Materialwahl: **PETG** ist der Allrounder und der Standard der Profile.
**PA/Nylon** (gern mit Carbon- oder Glasfaser) ist die beste Wahl für Ermüdung
und Verschleiß, muss aber trocken verarbeitet werden. **ASA** ist die Wahl für
draußen. **TPU** eignet sich für weiche, dämpfende Verbinder. **PLA** ist
brauchbar für leichte Innenanwendungen und Testcoupons, aber bei Biegung
spröde.

## Montagebild richtig konfigurieren

Das Lochraster wird über `hole_cols` und `hole_rows` festgelegt, der
Lochdurchmesser über `hole_diameter` (3,4 mm für M3, 4,5 mm für M4 mit etwas
Luft). Der Randabstand `mount_margin` hält die Löcher von Kante und Barrel
fern. Für Senkkopfschrauben aktivierst du `countersink`; die Senkung liegt
standardmäßig oben, also auf der der Klappseite abgewandten Seite, und druckt
dadurch ohne Stützen. Mit `slots_enabled` ersetzt du die Löcher durch Langlöcher:
`across` lässt den Abstand zur Montagefläche nachjustieren, `along` die seitliche
Position. Sind beide Muster aktiv, teilt das Modell die Fläche auf, damit sie
sich nicht überschneiden.

## Einsatzideen

- Klappe oder Blende an einem Homelab-Rack oder Mini-PC-Gehäuse
- Deckel für Elektronikgehäuse
- Justierbare Klappen mit Langlöchern
- Schwerere Deckel und Türen mit dem Preset `heavy`
- Eigene Konstruktionen mit einzelnen Flügeln (`leaf_left`, `leaf_right`)

![Variante mit Langlöchern](images/04_variante-langloecher.png)

## Fazit und Aufruf zum Mitmachen

Der Hinge Designer ist ein Werkzeug, kein Einzelstück: Du definierst Länge,
Festigkeit, Spiel und Montagebild, und das Modell passt die Geometrie an. Auf
**MakerWorld** findest du das Modell mit den Bambu-Studio-Profilen. Ich freue
mich über **Makes**, Fotos von deinen Einsatzfällen und Feedback zum Spiel bei
anderen Druckern und Materialien. Wenn du eine Konfiguration brauchst, die das
Modell noch nicht abdeckt, schreib in die Kommentare auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3160240-parametric-print-in-place-hinge-generator

---

## 10 SEO-Titel

1. Print-in-Place Scharnier parametrisch drucken – Hinge Designer für Bambu Lab
2. 3D-gedrucktes Scharnier ohne Stützen: flach drucken, sofort beweglich
3. Parametrisches Knuckle-Scharnier mit Lochbild und Langlöchern (OpenSCAD)
4. Scharnier 3D-Druck: Spiel einstellen mit `hinge_gap` und Testcoupon
5. Print-in-Place Hinge für P2S, P1S und H2C: Presets simple, standard, heavy
6. Barrel-Hinge aus PETG: Einstellungen, Spiel und Wände im Überblick
7. Scharnier selbst konstruieren? Parametrisches Modell mit Customizer
8. 3D-Druck-Scharnier mit Senkung und Langlöchern für Homelab und Gehäuse
9. Flaches Print-in-Place-Scharnier: Aufbau, Parameter und Druckprofile
10. OpenSCAD-Scharnier für MakerWorld: Länge, Pin und Montage frei wählbar

## 20 relevante Suchbegriffe

- print in place hinge
- 3D-Druck Scharnier
- Scharnier 3D drucken ohne Stützen
- parametrisches Scharnier
- Knuckle Hinge 3D Print
- Barrel Hinge OpenSCAD
- Bambu Lab Scharnier
- Bambu P2S Scharnier PETG
- MakerWorld Scharnier
- Scharnier Langlöcher 3D-Druck
- Scharnier mit Senkung 3D-Druck
- Hinge Spiel einstellen
- Print-in-Place Spiel PETG
- Testcoupon Scharnier
- Scharnier für Deckel 3D-Druck
- Gehäuse Klappe 3D-Druck
- Homelab Rack Klappe drucken
- OpenSCAD Customizer Scharnier
- funktionale 3D-Drucke
- Scharnier Nylon PA-CF 3D-Druck

## 10 GitHub-Tags

- print-in-place
- parametric
- openscad
- hinge
- 3d-printing
- bambu-lab
- makerworld
- fdm
- customizer
- functional-print

## 5 LinkedIn-Post-Ideen

1. **Von der Kalibrierung zum Werkzeug:** Warum das Spiel in einem
   Print-in-Place-Scharnier der entscheidende Parameter ist und wie ein
   Testcoupon Zeit und Filament spart.
2. **Parametrisch statt starr:** Wie Presets (`simple`, `standard`, `heavy`)
   die Geometrie ableiten, statt ein Modell zu skalieren.
3. **Qualitätssicherung im Maker-Alltag:** Mindestabstand und Schnittvolumen als
   automatische Prüfung für bewegliche Teile.
4. **Design-Entscheidungen erklärt:** Warum die Achshöhe gleich dem Barrel-Radius
   ist und wie dadurch stützenfrei gedruckt wird.
5. **Open Documentation, exklusive Dateien:** Wie ich Dokumentation öffentlich
   teile und die Druckdateien bei MakerWorld halte.

## 5 Reddit-Post-Ideen

1. **r/3Dprinting:** „Print-in-place hinge that prints flat with no supports –
   adjustable clearance, holes or slots" mit Hero-Bild und Spielwerten für PLA
   und PETG.
2. **r/BambuLab:** „P2S + PETG print-in-place hinge profiles in 2/3/4 walls –
   which one do you use?" mit Frage nach Erfahrungen.
3. **r/openscad:** „How I derive knuckle count, bore and barrel from presets in a
   parametric hinge" mit Diagramm der Parameterkette.
4. **r/functionalprint:** „Adjustable hinge with slotted mounting for covers and
   hatches" mit Anwendungsbeispiel.
5. **r/homelab:** „Printable hinge for rack covers and mini-PC enclosures –
   screw pattern adjustable" mit Hinweis auf Befestigungsbild.
