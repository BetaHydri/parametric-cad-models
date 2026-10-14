# Aufbewahrungsbox 3D-drucken: parametrisch mit Überstülp-Deckel, Griffen und Beschriftung

👉 **MakerWorld-Link:**
<https://makerworld.com/en/models/3191584-your-parametric-box-generator>
– Profil: <https://makerworld.com/en/@BetaHydri>

![Parametric Box – vier Boxen mit farbigen Deckeln](images/01_hero.jpg)

## Motivation: Die große Box, die ins Regal passt

Für Werkstatt, Keller und Homelab brauche ich Boxen in Maßen, die es fertig
selten gibt: 180 mm breit für das Regalfach, mit einem Deckel, der festsitzt,
und gern mit Griffen. Mein erstes Gefäß-Modell, der *Parametric Storage
Vessel*, nutzt einen Steckdeckel, der **innen** in die Öffnung greift. Das ist
für kleinere Behälter ideal. Für große Öffnungen wollte ich einen Deckel,
der **von außen** über die Wand greift und die Kante verdeckt. Daraus wurde
die **Parametric Box**: rund oder rechteckig, mit Griffen, Rillen und Text –
alles im MakerWorld-Customizer.

## Funktionen im Überblick

- **Überstülp-Deckel:** greift von außen über die Box. Standard sind 10 mm
  Überlappung (`lid_overlap`) und 0,15 mm Spiel je Seite (`fit_clearance`).
- **Rund oder eckig:** `shape` wählt zwischen Zylinder und Rechteck; `corner_r`
  steuert den Eckenradius.
- **Freie Maße bis 320 mm:** `diameter`, `width`, `depth`, `height`.
- **Tragegriffe:** Öffnungen mit spitzem Dach, die ohne Stützen druckbar sind.
- **Rillenstruktur:** rechteckig, V-förmig oder gerundet; die Rillen enden
  unterhalb des Deckelbereichs.
- **Beschriftung:** Text auf Deckel und Wand, als Vertiefung oder als
  Farbeinlage im Mehrfarbdruck.
- **Vier fertige Varianten** für den Bambu Lab P1S, Box und Deckel auf zwei
  Platten.

![Rechteckige Box mit Grifföffnung](images/03_variante-tragegriffe.jpg)

## Entwicklungsprozess

Die Box ist im August 2026 entstanden. Am 18. August gab es die ersten
Vorschau- und Prüfskripte, am 19. August die vier Referenzvarianten: eine
rechteckige Box mit Deckel (180 × 130 × 115 mm), eine rechteckige Kiste mit
Griffen (200 × 150 × 140 mm), ein runder Kanister mit Rillen (Ø 160 × 140 mm)
und eine beschriftete Box (175 × 125 × 110 mm) mit dem Schriftzug PARTS. Die
Bilder in diesem Beitrag sind Renderings der Modellgeometrie, keine
Druckfotos.

## Technische Hintergründe

**Der Deckel.** Der Deckel ist ein Rohr mit der Wandstärke `lid_wall`, dessen
Innenmaß die Box plus zweimal `fit_clearance` umfasst. Er wird mit der Platte
nach unten gedruckt; am offenen Ende (beim Drucken oben) sitzt eine
Einführfase. So braucht der Deckel keine Stützen.

**Griffe ohne Stützen.** Die Öffnung ist ein Langloch mit gerundeten unteren
Ecken und einem spitzen Dach. Die Dachflanken stehen steiler als 45°; jede
Schicht überhängt die darunter um weniger als eine Schichthöhe, und nichts
wird überbrückt. Die Spitze liegt bei `handle_side_h` + `handle_w` / 2. Mit
`handle_tip_r` rundest du sie für die Finger; dann entsteht oben nur eine
kurze Krone. Ohne `handle_z` sitzt die Öffnung automatisch unter der
Deckelüberlappung und über dem Boden.

**Rillen unter dem Deckel.** Die Rillen enden bei `height` − `lid_overlap`.
Der Bereich, in dem der Deckel greift, bleibt glatt – das ist die bessere
Reibfläche. Die Rillentiefe ist auf `wall` − 0,8 mm begrenzt, damit
mindestens 0,8 mm Wand stehen bleiben.

**Text auf runder Wand.** Jeder Buchstabe sitzt auf seiner eigenen
Tangentialebene an seiner Bogenposition und wird radial in die Wand
geschnitten. Um den Text bleibt ein glattes Feld frei von Rillen
(`text_panel_margin`); bei rechteckigen Boxen entsteht es aus der Hülle der
Textkontur.

**Die Farbeinlage.** Im Mehrfarbdruck ist der Text ein eigener Körper, der die
Vertiefung exakt füllt. Er ist tiefer als die Gravur im Einzelfarbdruck,
weil eine nur 0,6 mm dünne Haut an einer senkrechten Wand fadig druckt.

![Runde Box mit gerundeten Rillen](images/04_variante-rund-rillen.jpg)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für den **P1S** mit **Bambu PLA Basic** gebaut und im Slicer
getestet: 0,20 mm Layerhöhe, 3 Wände, 15 % Gyroid. Die vier Referenzvarianten
sind große Boxen. Box und Deckel passen deshalb nicht auf eine Platte; die
Profile enthalten Platte 1 für die Box und Platte 2 für den Deckel. Kleinere
Boxen passen im Layout `both` nebeneinander auf eine Platte.

Das Deckelspiel hängt vom Drucker ab: Sitzt der Deckel zu locker, verringerst
du `fit_clearance`; klemmt er, erhöhst du es.

Für die **Zweifarb-Ausgabe** (`Multicolor Export`) exportierst du den STL
direkt aus der OpenSCAD-Vorschau, ohne F6/Render und ohne Kommandozeile.
Sonst werden alle Gruppen zu einem Körper vereinigt, und die Farben gehen
verloren.

## Einsatzideen

- Werkstattbox mit Griffen für Werkzeug und Kleinteile
- Eine Box, die genau in ein Regalfach passt
- Beschriftete Organizer-Box mit Text auf Wand und Deckel
- Runder Kanister mit Rillen
- Homelab-Boxen für Kabel, Netzteile und SSDs
- Farbset mit mehreren Deckelfarben

![Box mit PARTS-Schriftzug auf Wand und Deckel](images/05_variante-beschriftung.jpg)

## Fazit und Aufruf zum Mitmachen

Die Box ist ein Baukasten für große Aufbewahrungsboxen. Wenn du sie druckst,
freue ich mich über **Makes** mit Fotos, besonders mit Beschriftung, Griffen
und eigenen Maßen. Rückmeldungen zum Deckelspiel auf anderen Druckern helfen,
die Voreinstellung zu verbessern. Schreib einfach einen Kommentar auf
MakerWorld.

👉 **MakerWorld-Link:**
<https://makerworld.com/en/models/3191584-your-parametric-box-generator>

---

## 10 SEO-Titel

1. Aufbewahrungsbox 3D-drucken: parametrisch mit Überstülp-Deckel (OpenSCAD)
2. Parametric Box für Bambu Lab: rund oder eckig, jede Größe
3. Box mit Griffen 3D-Druck: Grifföffnung ohne Stützen
4. Deckel von außen über die Box: Überstülp-Deckel 3D-drucken
5. Box mit Beschriftung 3D-drucken: Text auf Deckel und Wand
6. Kiste mit Tragegriffen: selbsttragendes 45°-Dach
7. Regalbox nach Maß: parametrische Box im Customizer
8. Runde Box mit Rillen: Kanister 3D-drucken
9. Parametric Box: One Generator – Endless Storage Boxes
10. Große Box auf zwei Platten drucken: Box und Deckel getrennt

## 20 relevante Suchbegriffe

- Aufbewahrungsbox 3D-Druck
- Box mit Deckel 3D drucken
- parametrische Box OpenSCAD
- Storage box 3D print
- Over-cap lid 3D print
- Überstülp-Deckel 3D-Druck
- Box mit Griffen 3D-Druck
- Tragegriff ohne Stützen
- Kiste 3D-Druck
- Werkstattbox 3D-Druck
- Regalbox 3D-Druck
- Box mit Beschriftung 3D-Druck
- Dose mit Rillen 3D-Druck
- eckige Box 3D-Druck
- runde Box 3D-Druck
- Bambu Lab P1S Box
- MakerWorld Box
- Customizer Box
- Mehrfarbdruck Box
- funktionale 3D-Drucke

## 10 GitHub-Tags

- storage
- box
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- lid
- functional-print

## 5 LinkedIn-Post-Ideen

1. „Deckel von außen statt von innen“: Warum große Boxen einen
   Überstülp-Deckel brauchen.
2. „Griffe ohne Stützen“: Wie ein Dach steiler als 45° Grifföffnungen
   druckbar macht.
3. „Rillen, die vor dem Deckel enden“: Warum die Reibfläche glatt bleiben
   muss.
4. „Mehrfarbdruck ohne Slicer-Gefummel“: Farbeinlage im Text statt dünner
   Haut.
5. „Vom Gefäß zur Box“: Warum ich zwei Modelle mit zwei Deckelarten gebaut
   habe.

## 5 Reddit-Post-Ideen

1. r/functionalprint – „Parametric storage box with over-cap lid and
   support-free carry handles“ mit dem Hero-Bild.
2. r/openscad – „Self-supporting handle cut-outs: a peaked 45-degree roof in
   OpenSCAD“: Erklärung des Ansatzes ohne Quelltext.
3. r/BambuLab – „Two-colour lettering as flush inlay on a box wall: export
   from the preview, not from F6“.
4. r/3Dprinting – „Over-cap vs. inner friction-fit lid for large boxes: what
   works for you?“ als Diskussionsfrage.
5. r/3Dprinting – „Printing a large box and its lid on two plates: tips“.
