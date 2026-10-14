# Parametrischen Lampenschirm 3D-drucken: Tischlampe und Hängelampe aus einer Datei

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3062645-parametric-table-lamp-ceiling-lamp – Profil:
<https://makerworld.com/en/@BetaHydri>

![Parametrischer Lampenschirm mit Hexagon-Muster als leuchtende Tischlampe](images/01_hero.jpg)

## Motivation: Ein Schirm, der wirklich leuchtet

Einen Lampenschirm zu drucken ist leicht. Einen zu drucken, der im
eingeschalteten Zustand gut aussieht, zum Leuchtmittel passt und sich ohne
Stützen und ohne Ausschuss drucken lässt, ist es nicht. Eine massive Wand von
1,6 mm lässt kaum Licht durch. Ein Loch fürs Kabel, das nur den Draht
berücksichtigt, lässt den Stecker nicht durch. Ein offenes Muster in einer
dünnen Wand zerfällt schnell in lose Einzelteile.

Der **Parametrische Lampenschirm** ist mein Versuch, diese Punkte in einem
Modell zusammenzubringen. Er ist für das **Bambu Lab LED Lamp Kit 001 (MH001)**
gebaut, lässt sich aber über Parameter an andere runde LED-Module anpassen.
Eine einzige OpenSCAD-Datei erzeugt eine **Tischlampe** und eine
**Hängelampe**.

## Funktionen im Überblick

- **Zwei Lampen in einem Modell:** Der Tischfuß hält den LED-Puck nach oben, die
  Hängekappe nach unten; das Kabel läuft mittig nach oben heraus.
- **Freie Grundform:** `shade_height`, `base_diameter`, `top_diameter`,
  `belly_bulge`, `belly_position` und `wall_thickness` formen konische,
  zylindrische oder bauchige Schirme.
- **Sechs Oberflächenstile:** `smooth`, `vertical_waves`, `twist_flutes`,
  `ripple`, `scallop` und `facets`; `surface_twist` dreht die Struktur über die
  Höhe.
- **Fünf Durchbruch-Muster:** `none`, `diamond`, `hex`, `mesh` und `slots`. Das
  Licht scheint durch echte Öffnungen und wirft Muster an Wand und Decke.
- **Leuchtmittel einstellbar:** Puck-Maße, Schraubenabstand, Kabel und
  Stecker (`plug_dia`).
- **Optionaler Diffusor** mit konzentrischen oder radialen Rillen.
- **Stützenfrei:** Der Schirm steht aufrecht, Fuß, Kappe und Diffusor liegen
  flach.

![Lampenschirm mit senkrechten Wellen als leuchtende Tischlampe](images/02_wellen.jpg)

## Entwicklungsprozess

Ausgangspunkt war der Wunsch, für das MH001-Kit (Puck Ø 59 × 8 mm, 5 V, 3 W)
einen eigenen Schirm zu drucken. Die Bauchungs-Idee habe ich aus einem früheren
parametrischen Schalenmodell übernommen; als Anregung dienten vier
Lampen auf MakerWorld mit Voronoi-, Wellen- und Ripple-Look.

Die interessanten Teile entstanden durch Fehler, die ich in der Vorschau oder
beim Testdruck gefunden habe:

- Der erste Tischfuß hatte den LED-Halter unter einer massiven Platte und einem
  vollen Zylinder vergraben. Der Puck passte nicht hinein, und das Licht war
  blockiert. Jetzt ist die Zentrierlippe ein Ring, und eine offene Bohrung
  lässt das Licht nach oben.
- Der Stecker des LED-Kabels ist dicker als das Kabel. Seitdem gibt es
  `plug_dia`, und Kappenloch, Knotenmulde und Kabelnut orientieren sich daran.
- `twist_flutes` sah zunächst genauso aus wie `vertical_waves`. Der Stil hat jetzt
  ein eigenes Profil mit eingebauter Halbdrehung.
- Hohe, freistehende Stege im Stil `slots` begannen beim Druck zu schwingen. Die
  Lösung waren waagerechte Versteifungsringe.

## Technische Hintergründe

Der Schirm ist kein Boolean-Körper, sondern ein einzelner **Polyeder** aus
Außenfläche, Innenfläche und zwei Randringen. Der Außenradius ergibt sich aus
einer Geraden zwischen Unter- und Oberradius plus einer Bauchung, die über einen
Kosinus-Faktor an den Enden auf null ausläuft. Die Oberflächenstruktur wird auf
den Radius addiert und blendet an den obersten und untersten 6 % der Höhe aus,
damit die Ränder rund bleiben und die Zentrierlippe sauber passt. Der Innenradius
folgt dem Außenradius, die Wandstärke bleibt konstant.

Fuß und Kappe zentrieren sich über eine Lippe. Ihr Radius ist der kleinste
Innenradius des Schirms in der Eingriffstiefe `lip_engage` minus `fit_play`;
dadurch passt die Lippe auch bei Wellen oder Bauchung.

Die Durchbrüche sind Schneidkörper. Damit sie den Schirm nicht zerlegen, gelten
mehrere Regeln: Beim Muster `mesh` verschiebt eine deterministische
Hash-Funktion Winkel, Höhe, Größe und Drehung jedes Lochs, die Größe bleibt aber
unter dem Zellmaß abzüglich Stegbreite. Bei `slots` wird die Oberflächenstruktur
auf 40 % gedämpft, damit tiefe Wellen keinen Steg verdünnen, und
`slot_rings` lässt waagerechte Wandbänder stehen, die alle Streben verbinden.

Zur Absicherung habe ich alle 30 Kombinationen aus Oberflächenstil und
Durchbruch-Muster exportiert und geprüft. Jede ergab genau einen wasserdichten
Körper. Ob ein Parameter wirkt, habe ich über den Hash der exportierten Datei
belegt statt über das Volumen, weil etwa `surface_twist` das Volumen nicht
ändert.

![Hängelampen-Vorschau mit Kappe auf einem Schirm im Ripple-Stil](images/04_vorschau-haengelampe.jpg)

## Druck-Erfahrungen und Empfehlungen

Die mitgelieferten Profile sind für den **Bambu Lab P1S** mit **Bambu PLA Basic**
erstellt: 0,20 mm Layerhöhe, 2 Wände, Gyroid mit 15 % Infill, jeweils mit Schirm
und Tischfuß als zwei Objekten auf einer Platte. Drei Varianten liegen bei:
`wellen`, `hex` und `twist`.

Die wichtigsten Hinweise:

- **Leuchten:** 0,8–1,2 mm Wandstärke, 2–3 Wände und 0 % Infill beim Schirm
  machen die Wand lichtdurchlässig. Weißes oder transluzentes PLA wirkt am
  besten. Für kräftigeres Licht 1,6–2,0 mm.
- **Platz auf dem Bett:** Der Schirm ist breiter als `base_diameter`; mit den
  Standardwerten passen Schirm und Fuß nicht nebeneinander auf ein 256-mm-Bett.
  Deshalb sind sie in den Profilen getrennte Objekte.
- **Hohe Stege:** Bei `slots` mindestens zwei Ringe behalten und die Außenwand
  langsam drucken.
- **Netzspannung:** PLA erweicht ab etwa 50–60 °C. Wer ein 110- oder
  230-V-Modul nutzt, sollte PETG oder PA drucken, nur zertifizierte Module mit
  isoliertem Anschluss einsetzen und den Treiber außerhalb des Schirms
  montieren.

![Lampenschirm mit gedrehten Rillen als leuchtende Tischlampe](images/03_twist.jpg)

## Anwendungsbeispiele

- Nachttisch- oder Kommodenlicht als weiches Ambientelicht
- Schattenspiel mit `hex` oder `mesh` an Wand und Decke
- Pendelleuchte über dem Esstisch mit der Hängekappe
- Eigenes Leuchtmittel durch Anpassung von `led_diameter`, `led_thickness` und
  `plug_dia`
- Formstudien mit `belly_bulge`, `belly_position` und `top_diameter` im
  Customizer

## Fazit und Aufruf zum Mitmachen

Der Lampenschirm ist ein Baukasten: Du wählst Form, Oberfläche und Muster, und
das Modell hält Passung, Lichtweg und Kabelführung konsistent. Das Modell mit den
Bambu-Studio-Profilen gibt es ausschließlich auf **MakerWorld**. Ich freue mich
über **Makes**, Fotos deiner Lampen im Betrieb und Rückmeldung, mit welchen
Leuchtmitteln und Filamenten es bei dir funktioniert hat. Wenn dir ein
Oberflächenstil oder ein Muster fehlt, schreib es in die Kommentare.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3062645-parametric-table-lamp-ceiling-lamp

---

## 10 SEO-Titel

1. Lampenschirm 3D-drucken: parametrisch für Tisch- und Hängelampe
2. Parametrischer Lampenschirm für das Bambu LED Lamp Kit (MH001)
3. 3D-gedruckte Lampe selbst gestalten: Schirm mit Wellen, Hex und Twist
4. Lampenschirm OpenSCAD: Customizer-Modell mit LED-Halter
5. Pendelleuchte 3D-Druck mit Hängekappe und Knoten-Zugentlastung
6. Lampenschirm mit Lichtmuster drucken: hex, mesh und slots
7. LED-Puck Lampenschirm: Maße, Stecker und Kabel richtig einstellen
8. Stützenfreier Lampenschirm für Bambu Lab P1S und PLA
9. Transluzenten Lampenschirm drucken: Wandstärke, Infill und Material
10. Lampenschirm 3D-Druck: 6 Oberflächenstile und 5 Durchbruch-Muster

## 20 relevante Suchbegriffe

- Lampenschirm 3D-Druck
- Lampenschirm drucken
- parametrischer Lampenschirm
- 3D gedruckte Lampe
- Tischlampe 3D-Druck
- Hängelampe 3D-Druck
- Pendelleuchte 3D drucken
- Bambu LED Lamp Kit
- Bambu LED Lamp Kit 001 MH001
- LED-Puck Halter 3D-Druck
- Lampenschirm OpenSCAD
- Lampenschirm Customizer
- MakerWorld Lampenschirm
- Lampenschirm Vase Mode
- transluzentes PLA Lampe
- Lampenschirm mit Muster
- Voronoi Lampe 3D-Druck
- Lampenschirm Bambu P1S
- Lampenschirm ohne Stützen
- Diffusor 3D-Druck Lampe

## 10 GitHub-Tags

- lampshade
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- led-lamp
- customizer
- pendant-lamp
- home-decor

## 5 LinkedIn-Post-Ideen

1. Vom Fehler zum Feature: Wie ein verdeckter LED-Halter und ein zu großer
   Stecker die Konstruktion eines parametrischen Lampenschirms geprägt haben.
2. Constraint-Design in OpenSCAD: 30 Kombinationen aus Oberflächenstil und
   Muster automatisch auf wasserdichte Geometrie prüfen.
3. Ein Modell, zwei Anwendungen: Warum Tischfuß und Hängekappe denselben
   Schirm teilen und welche Parameter dafür nötig sind.
4. Parametrik statt Variantenflut: Ein Customizer-Modell ersetzt Dutzende
   Einzeldateien – und was das für Wartung und Pflege bedeutet.
5. Sicherheit beim Selbstbau: PLA, Netzspannung und Treiberplatzierung in
   gedruckten Leuchten.

## 5 Reddit-Post-Ideen

1. r/3Dprinting – „Parametric lampshade with 6 surface styles and 5 light
   patterns, printed support-free on a P1S" (Bilder der leuchtenden Tischlampe).
2. r/BambuLab – „Using the Bambu LED Lamp Kit 001: table and pendant lamp from
   one OpenSCAD file" (Hinweise zu Puck, Stecker und Profilen).
3. r/openscad – „Hand-built polyhedron shade with constant wall thickness and
   rim fade; how I keep patterned openings from splitting the shell".
4. r/functionalprint – „Pendant lamp cap with plug-sized cable hole and knot
   strain relief" (Anwendungsfoto der Hängekappe).
5. r/lamps oder r/DIY – „3D-printed translucent lampshade: wall thickness,
   infill and filament tips for a good glow".
