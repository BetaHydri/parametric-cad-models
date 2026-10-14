# Küchenrollenhalter 3D-drucken: Wand, Unterschrank oder Tisch – mit Federbremse und teilbar

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3143928-parametric-kitchen-paper-towel-roll-holder – Profil:
<https://makerworld.com/en/@BetaHydri>

![Parametric Kitchen Paper Towel Roll Holder – drei Montagearten in einer Wohnmobil-Küche](images/01_hero.jpg)

## Motivation: Eine Rolle, die nach der ersten Kurve noch hängt

Küchenrollenhalter gehören zu den Dingen, die man erst vermisst, wenn sie
fehlen – und die man dann falsch kauft. Im Wohnmobil rüttelt die Fahrt die
Rolle ab. Unter dem Hängeschrank schleift der Winkel an der frischen, dicken
Rolle. Und die ganze Rolle ist 260 mm breit, das Druckbett aber nur 256 mm.
Ich wollte einen Halter, der diese drei Probleme als **Parameter** behandelt:
Montageart, Rollenmaße und Teilung für das eigene Druckbett.

## Funktionen im Überblick

- **Drei Montagearten:** Wand, Unterschrank und Tischständer (`mount_style`,
  `part`).
- **Federbremse:** leichter Dauerwiderstand im Pappkern; Stärke über
  `brake_preload`.
- **Zwei Bremsbauarten:** Clip-Federblatt zum Einclipsen (`insert`, Standard,
  flach druckbar, ideal in PETG) oder druckintegriertes Blatt (`integrated`).
- **Rollenvoreinstellungen:** Standard 230, Deutsch 260,5, Groß 250, Kompakt
  180 und Eigen; Kern-, Außen- und Freischnitt-Durchmesser einstellbar.
- **Schrauben oder Klebeband:** `screw_hole_dia = 0` für eine glatte Platte.
- **Ganz oder geteilt:** gedrucktes Grobgewinde ohne Kleber, für 256-mm-Betten.
- **Unterschrank frei für dicke Rollen:** `clearance_roll_dia`.

![Wandvariante mit aufgesteckter Rolle](images/02_wandmontage.jpg)

## Entwicklungsprozess

Am Anfang stand im August 2026 eine Federbremse, die als Blatt direkt aus der
Spindelwand geschnitten ist. Beim stehenden Druck schwingt die lange freie Zunge
ab ca. 100 mm Höhe, deshalb gibt es abknipsbare Haltestege. Weil das Blatt
nicht in geteilten Teilen funktioniert, kam am 7. August das Clip-Federblatt
dazu. Der erste Clip lag im Test flach und wirkte nur als Höcker – er war zu dick,
zu breit und zu kurz. Die Neukonstruktion hat eine dünne, verjüngte Zunge mit
dem Dom an der freien Spitze und einem Luftspalt von 2,6 mm darunter. Außerdem
entfernte ich die Stützstrebe unter der Wandspindel, weil sie mit jeder Rolle
kollidierte.

## Technische Hintergründe

**Spindel und Bremse.** Der Schaft ist um `spin_play` (0,8 mm) dünner als der
Kern, die Rolle dreht sich also frei. Nur der Bremsdom steht um
`spin_play` + `brake_preload` über der Spindel und drückt leicht in den Kern.
Mit den Voreinstellungen (Kern 41 mm) ergeben sich ein Spindelradius von
19,7 mm und ein Bremsradius von 21,0 mm.

**Der Clip.** Der kräftige Fuß gleitet unter eine Lippe im Schlitz und kann
radial nicht herausfallen; eine kleine Rastnase schnappt in eine Nut. Der
Schlitz ist `brake_blade_len` + 2 mm lang. Der Fuß misst 30 % der Clip-Länge
(mindestens 8, höchstens 14 mm). Die freie Zunge ist mit 1,0 mm dünner als der
Fuß (1,6 mm) und verjüngt sich von 15 mm auf 9 mm Breite.

**Das Gewinde.** Ein grobes Trapezprofil mit flachem Kamm, 3,5 mm Steigung,
Tiefe 0,42 × Steigung und 14 mm Eingriff (ca. 4 Windungen). Es ist robust und
von Hand schraubbar. `split_at` legt fest, wo ein Teil geteilt wird.

**Der Unterschrank.** Winkel und Streben werden für den Durchmesser von
`clearance_roll_dia` (Standard 140 mm) plus Luftspalt freigeschnitten – nicht
für die Rolle, die gerade hängt. So schleift auch eine frische, dicke Rolle
nicht.

**Ausgabe.** Teile mit Clip-Schlitz legen den Clip neben sich auf die Platte.
Die geteilten Ausgaben ordnen alle Segmente und den Clip auf einer Platte an.

![Unterschrank-Variante mit hängender Rolle](images/03_unterschrank.jpg)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für **Bambu PETG Basic** gebaut: 0,20 mm Layerhöhe, 2 Wände,
Gyroid 10 %. Geteilte und kleine Teile sind für den P2S ausgelegt, einteilige
hohe Teile für den H2C.

**Material:** In Wohnmobil, Auto oder Boot verzieht sich PLA in der heißen
Kabine, dort mindestens PETG. Zu Hause genügt PLA für den Halter; nur der Clip
profitiert von PETG (federt besser, hält länger).

**Stützen:** Spindelteile mit Clip-Schlitz drucken stehend, der Schlitz hängt
leicht über – dafür leichte Baumstützen. Tischfuß und Clip drucken ohne Stützen.

**Länge:** Eine einteilige Wandspindel ist bei 230 mm Rolle etwa 248 mm hoch,
bei 260,5 mm Rolle etwa 278 mm. Auf einem 256-mm-Bett nimmst du die geteilten
Ausgaben (`Wall holder split`, `Table split`).

Bei `brake_type = integrated` knipst du nach dem Druck die Haltestege bündig
ab, sonst federt die Zunge nicht.

## Einsatzideen

- Unterschrank im Camper mit Federbremse und PETG-Halter
- Wandplatte neben der Arbeitsfläche, aufgeschraubt oder geklebt
- Klebe-Variante ohne Bohren (Mietwohnung): `screw_hole_dia = 0`
- Freistehender Tischständer
- Halter an der Werkbank für Reinigungspapier

![Küche mit allen drei Montagearten nebeneinander](images/05_kueche-drei-varianten.jpg)

## Fazit und Aufruf zum Mitmachen

Der Halter ist ein Baukasten für Rollenhalter aller Art. Wenn du ihn druckst,
freue ich mich über **Makes** mit Fotos, besonders in Fahrzeugen und mit
ungewöhnlichen Rollen. Rückmeldungen zur Bremskraft und zum Clip auf anderen
Druckern und Materialien helfen, die Voreinstellungen zu verbessern. Schreib
einfach einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3143928-parametric-kitchen-paper-towel-roll-holder

---

## 10 SEO-Titel

1. Küchenrollenhalter 3D-drucken: Wand, Unterschrank oder Tisch (parametrisch)
2. Küchenrollenhalter fürs Wohnmobil: PETG, Federbremse, Unterschrank-Montage
3. Rolle reißt einhändig ab: Federbremse für den Küchenrollenhalter
4. Clip-Federblatt 3D-Druck: Bremse zum Einclipsen, flach in PETG gedruckt
5. Küchenrollenhalter für 256-mm-Druckbett: geteilt mit gedrucktem Gewinde
6. Halter für dicke Küchenrollen: Unterschrank-Winkel mit Freischnitt
7. Küchenrollenhalter ohne Bohren: Klebe-Variante mit doppelseitigem Band
8. Parametric Kitchen Paper Towel Roll Holder: one file, three mounts
9. Tischständer für Küchenrolle: beschwerter Fuß mit Kugel
10. Grobgewinde aus dem 3D-Drucker: robuste Schraubverbindung ohne Kleber

## 20 relevante Suchbegriffe

- Küchenrollenhalter 3D-Druck
- Küchenrollenhalter Wohnmobil
- Küchenrollenhalter Unterschrank
- Küchenrollenhalter Wand
- Küchenrollenhalter Tisch
- paper towel holder 3D print
- paper towel holder camper
- under cabinet paper towel holder
- Küchenrolle Halter Bremse
- anti unroll paper towel holder
- parametrischer Küchenrollenhalter
- OpenSCAD Halter
- Bambu Lab P2S Halter
- MakerWorld Küchenrollenhalter
- Customizer Küchenrollenhalter
- Halter PETG Wohnmobil
- Küchenrollenhalter ohne Bohren
- Küchenrollenhalter Klebeband
- geteilter 3D-Druck Gewinde
- funktionale 3D-Drucke

## 10 GitHub-Tags

- kitchen
- paper-towel-holder
- roll-holder
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- functional-print

## 5 LinkedIn-Post-Ideen

1. „Ein Federblatt aus dem Drucker“: Warum die erste Clip-Version nur ein Höcker
   war und wie die verjüngte Zunge das löste.
2. „Wenn das Druckbett kürzer ist als die Rolle“: Teilen mit einem gedruckten
   Grobgewinde statt Kleber.
3. „Freischnitt für die größte Rolle“: Warum der Unterschrank-Winkel nicht für die
   aktuelle, sondern für die dickste Rolle gebaut wird.
4. „PLA im Wohnmobil?“: Materialwahl für heiße Kabinen.
5. „Eine Datei, drei Montagearten“: Parametrische Varianten statt drei Modellen.

## 5 Reddit-Post-Ideen

1. r/functionalprint – „Paper towel holder with a printed spring brake,
   three mounting styles from one parametric file“ mit dem Hero-Bild.
2. r/3Dprinting – „Printed clip-in leaf spring: my first version was a rigid
   bump, thin tapered tongue fixed it“.
3. r/openscad – „Split a long print with a chunky printed thread: how I sized
   pitch, depth and clearance“, ohne Quelltext.
4. r/vandwellers – „Under-cabinet paper towel holder with anti-unroll brake,
   printed in PETG for hot cabins“.
5. r/BambuLab – „Which brake preload feels right on your paper roll? Default
   is 0.5 mm“ als Diskussionsfrage.
