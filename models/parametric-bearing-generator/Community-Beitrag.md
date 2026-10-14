# Print-in-Place Lager parametrisch drucken: Kugel-, Rollen-, Zahnrad- und Axiallager für Bambu Lab

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3166631-parametric-print-in-place-bearing-generator – Profil:
<https://makerworld.com/en/@BetaHydri>

![Parametric Bearings – vier Print-in-Place-Lagertypen im Überblick](images/01_hero.png)

## Motivation: Ein Lager, das direkt vom Druckbett läuft

Standardlager wie das 608 sind billig, aber nicht immer die richtige Lösung.
Manchmal fehlt die passende Größe, manchmal soll ein Mechanismus ohne Metallteile
auskommen, und manchmal willst du einfach sehen, wie ein Planetengetriebe
von innen aussieht. Ein **Print-in-Place-Lager** entsteht in einem Druckjob,
komplett montiert, ohne Stützen und ohne Nacharbeit. Das Problem: Zu wenig
Spalt verschweißt die Teile, zu viel lässt sie klappern, und frei
schwebende Kugeln drucken schlecht.

Der **Parametric Print-in-Place Bearing Generator** bündelt vier Lagertypen in
einer OpenSCAD-Datei. Größe, Spalt, Düse und Typ stellst du im
MakerWorld-Customizer ein.

## Funktionen im Überblick

- **Rillenlager (`ball`):** zwei Ringe, die axial verrasten und auf einem
  konstanten Spalt laufen. Es gibt keine losen Kugeln, die verrutschen könnten.
- **Zylinderrollenlager (`roller`):** stehende Rollen in Spulenform, gehalten von
  Flanschen an beiden Ringen und einem Käfig zwischen den Rollen.
- **Zahnradlager (`gear`):** Sonne, Planeten und Hohlrad mit Pfeilverzahnung, die
  Planeten und Sonne axial festhält.
- **Axiallager-Kit (`thrust`):** zwei Laufscheiben und ein Kugelkäfig für echte
  Stahlkugeln; wahlweise mit Snap-Kragen oder Schraubmontage.
- **43 Normgrößen:** 35 Rillenlager von `685` bis `6304` und 8 Rollenlager von
  `NU202` bis `NU2205`, jeweils mit den Grenzmaßen nach DIN 625-1 bzw. DIN 5412-1.
- **Laufspalt als Regler:** `tolerance_class` (0,25 / 0,30 / 0,35 mm) bei
  Normgrößen, `fit` bei eigenen Maßen.

![Zahnradlager mit Sonne, Planeten und Hohlrad](images/03_zahnradlager.jpg)

## Entwicklungsprozess

Das Rillenlager ist keine Neuerfindung. Ich habe druckbare Referenz-Lager
(608, 609, 6000, 6001, 6002, 6004 und 6902) vermessen und die Bauform nachgebaut:
Zwei Ringe mit Rippe-in-Nut-Profil, die axial einrasten und auf einem konstanten
Spalt laufen. Der Spalt von 0,25 / 0,30 / 0,35 mm war über alle sieben Größen
identisch und steckt jetzt als Toleranzklasse im Modell.

Beim Rollenlager halfen echte Drucke. Die ersten dünnen Käfigpfosten brachen ab;
das aktuelle Design nutzt Rollen in Spulenform, größere Führungsflansche und
einen Käfig, der sich an die Rollenform schmiegt. Der gedruckte Axiallager-Typ mit
Kugeln in der Luft ist gestrichen, weil er sich nicht sauber drucken ließ. Dafür gibt es
das Kit mit Stahlkugeln, das später eine Schraubmontage als bündige Alternative
zum Snap-Kragen bekam.

## Technische Hintergründe

**Senkrechte Achse.** Alle Wälzelemente sind Kreise in der X/Y-Ebene. Der Spalt
bildet sich als vertikale Wand zwischen den Perimetern; es gibt keine waagerechte
Brücke über der Lauffläche.

**Ein globaler Spalt mit Untergrenze.** Das Modell hebt den Laufspalt auf
`max(0,30 mm; 0,75 × Düse)` an. Nach Quellcode wirkt `tight` (0,25 mm) beim
Rillenlager deshalb wie `default`. Beim Rollenlager steuert die Klasse dagegen den
Rollenspalt (Klassenwert minus 0,12 mm, mindestens 0,13 mm).

**Zahnräder mit Taktung.** Die Planeten haben eine feste, ungerade Zähnezahl von
7. Ein ungerader Wert lässt einen unverdrehten Planeten der Sonne eine Zahnlücke
und dem Hohlrad einen Zahn zuwenden. Die Sonnenzähnezahl wird so gewählt, dass
die Montagebedingung der Planetenzahl erfüllt ist (3 bis 12 Planeten); das Hohlrad
hat Sonne plus zweimal Planet Zähne. Ein zu kleiner `outer_d` wird automatisch
vergrößert.

**Pfeilverzahnung.** Zwei gegenläufige Schrägungshälften treffen sich in der Mitte.
Der Winkel (`gear_helix`, Standard 30°) wird gegen Selbstdurchdringung
begrenzt. Mit `gear_helix = 0` entstehen Geradzähne, die axial herausfallen.

**Kugelkäfig.** Die Taschen verengen sich an beiden Seiten mit einem 45°-Hals:
Die Kugel wird eingepresst und ist danach gefangen. Ein Entlastungsschlitz macht
die Lippen federnd, damit PETG nicht bricht.

Alle Typen wurden mit einer OpenCascade-Prüfung kontrolliert: Der Mindestabstand
zwischen beweglichen Teilen ist größer als null, das Schnittvolumen ungefähr null.

![Rillenlager aus verrasteten Ringen](images/02_kugellager.jpg)

## Druck-Erfahrungen und Empfehlungen

Die mitgelieferten Profile sind für **Bambu Lab P2S** mit **PETG** erstellt:
3 Wände, Gyroid-Infill 20 %, Layerhöhe 0,20 mm. Das Rollenlager braucht
ein langsameres Profil (30 mm/s in der ersten Schicht, 50 mm/s bei Wänden, Infill
und Top-Fläche), das auf Bambu Studio mit `0.16 mm Standard @BBL H2C` geprüft wurde.
Ein Raft ist nicht nötig. Andere Typen drucken mit normalem Tempo.

Wichtig: Das Lager genau so drucken, wie es exportiert wird, mit senkrechter
Achse. Das Neu-Ausrichten im Slicer macht aus Spalten Brücken. Nach dem Abkühlen
einmal vorsichtig von Hand freibrechen. Klemmt es, `fit` in 0,05-mm-Schritten
erhöhen.

Für Dauerlast ist PLA ungeeignet; besser sind PA12 oder PA6 (trocken drucken) und, wenn
du es bekommst, ein Tribo-Filament. Gedruckte Lager sind für Prototypen und passend
dimensionierte Mechanismen gedacht, nicht für sicherheitskritische Anwendungen.

Für das Axiallager-Kit brauchst du Stahlkugeln der Güteklasse G100 oder besser.
Bei der Schraubmontage kommt eine Schraube dazu, deren Länge die Konsole ausgibt
(beim Rahmen 8 × 30 × 8 mm mit 6-mm-Kugeln: M3×4 oder M2.5×4).

![Axiallager-Kit: Platte mit Kragen, Gegenplatte und Käfig](images/04_axial-kit-flach.jpg)

## Anwendungsideen

- Drehteller und Plattentellern für Werkstatt und Homelab
- Rollen und Führungen in Prototypen
- Lehrmodell für Planetengetriebe
- Passproben für Gehäuse, bevor ein Industrielager bestellt wird
- Eigene Maße über `custom` mit `bore`, `outer_d` und `width`

## Fazit und Aufruf zum Mitmachen

Der Generator ist ein Werkzeug: Du legst Typ und Größe fest, der Rest wird aus
Düse, Spalt und Norm abgeleitet. Auf **MakerWorld** findest du das Modell mit
Bambu-Studio-Profilen. Ich freue mich über **Makes**, Fotos von deinen Lagern und
Feedback zu Spalten und Materialien. Besonders interessiert mich, wie das Zahnradlager
und das Rollenlager auf anderen Druckern und mit anderen Filamenten laufen.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3166631-parametric-print-in-place-bearing-generator

---

## 10 SEO-Titel

1. Print-in-Place Lager 3D-Druck: parametrischer Lagergenerator für Bambu Lab
2. Kugellager aus dem 3D-Drucker: Rillenlager ohne lose Kugeln (608, 6000, 6204)
3. Planetengetriebe-Lager drucken: Zahnradlager mit Pfeilverzahnung
4. Zylinderrollenlager 3D-Druck: NU202 bis NU2205 parametrisch
5. Axiallager-Kit mit Stahlkugeln: Drehteller aus PETG selbst bauen
6. 3D-gedrucktes Lager richtig auslegen: Laufspalt, Düse und Material
7. OpenSCAD Lagergenerator: 43 Normgrößen nach DIN 625 und DIN 5412
8. Lager drucken ohne Stützen: Achse senkrecht, Spalt als Parameter
9. Print-in-Place Bearing für P2S und H2C: Profile und Einstellungen
10. Funktionale 3D-Drucke: Lager für Prototypen, Drehteller und Lehrmodelle

## 20 relevante Suchbegriffe

- print in place bearing
- 3D-Druck Lager
- Kugellager 3D drucken
- Rillenkugellager 3D-Druck
- Zylinderrollenlager 3D-Druck
- Axiallager 3D-Druck
- Zahnradlager 3D-Druck
- Planetengetriebe 3D-Druck
- Planetary gear bearing
- parametrisches Lager OpenSCAD
- Lagergenerator
- 608 Lager drucken
- Drehteller 3D-Druck
- Stahlkugeln Axiallager
- Lager Laufspalt PETG
- Bambu Lab Lager drucken
- Bambu P2S PETG
- MakerWorld Lager
- Pfeilverzahnung 3D-Druck
- funktionale 3D-Drucke

## 10 GitHub-Tags

- print-in-place
- parametric
- openscad
- bearing
- planetary-gear
- 3d-printing
- bambu-lab
- makerworld
- fdm
- customizer

## 5 LinkedIn-Post-Ideen

1. **Vom Spalt zum Werkzeug:** Warum der Laufspalt in einem
   Print-in-Place-Lager der entscheidende Parameter ist und wie eine
   Untergrenze aus der Düse verhindert, dass es verschmilzt.
2. **Reverse Engineering im Maker-Alltag:** Wie aus vermessenen
   Referenz-Lagern ein parametrisches Rillenlager wurde.
3. **Normgrößen als Dropdown:** 35 Rillenlager- und 8 Rollenlager-Größen
   aus DIN 625-1 und DIN 5412-1 – und warum das Ergebnis trotzdem kein
   zertifiziertes Lager ist.
4. **Ein Typ gestrichen:** Was ich aus dem gescheiterten gedruckten
   Axiallager gelernt habe und warum Stahlkugeln besser sind.
5. **Open Documentation, exklusive Dateien:** Wie ich Dokumentation
   öffentlich teile und die Druckdateien bei MakerWorld halte.

## 5 Reddit-Post-Ideen

1. **r/3Dprinting:** „Print-in-place ball bearing with interlocking races – no
   loose balls, 35 DIN sizes" mit Hero-Bild und Spaltwerten.
2. **r/BambuLab:** „P2S + PETG print-in-place bearing profiles – roller
   bearing needs a slower profile, here are my speeds" mit Frage nach Erfahrungen.
3. **r/openscad:** „How I derive ring wall, gap and rolling-element size from the
   nozzle in a parametric bearing generator" mit Diagramm der Parameterkette.
4. **r/functionalprint:** „Printable steel-ball thrust bearing kit (snap or
   screw mount) for turntables" mit Stückliste.
5. **r/homelab:** „Printable bearings for rotating mounts and fan or sensor
   gimbals – fully parametric" mit Hinweis auf Normgrößen.
