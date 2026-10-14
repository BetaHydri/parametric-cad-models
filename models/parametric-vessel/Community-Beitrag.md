# Gefäß 3D-drucken: parametrisch, rund oder eckig, mit Steckdeckel und Beschriftung

👉 **MakerWorld-Link:** https://makerworld.com/en/models/2917278-parametric-vessel-with-friction-fit-lid – Profil:
<https://makerworld.com/en/@BetaHydri>

![Parametric Storage Vessel – runde und eckige Gefäße mit Deckeln](images/01_hero.png)

## Motivation: Die Dose, die ins Regal passt

Kleinteile, Schrauben, Kaffee, Kabel: Irgendwo steht immer ein Gefäß im Weg
oder fehlt in genau dem Maß. Gekaufte Dosen passen selten in ein vorhandenes
Regalfach, und Deckel sitzen entweder zu locker oder zu stramm. Der
**Parametric Storage Vessel** löst das mit einem einzigen Modell: Form, Maße,
Deckelspiel, Rillenstruktur und Beschriftung stellst du im
MakerWorld-Customizer ein, statt ein starres Modell zu skalieren.

## Funktionen im Überblick

- **Rund oder eckig:** `shape` wählt zwischen Zylinder und Rechteck; bei
  eckigen Gefäßen steuert `corner_r` den Eckenradius.
- **Freie Maße bis 320 mm:** `diameter`, `width`, `depth`, `height`.
- **Steckdeckel mit Reibschluss:** Der Deckelrand schiebt sich mit
  `fit_clearance` (Standard 0,15 mm je Seite) in die Öffnung. `skirt_depth`
  und `skirt_chamfer` steuern Tiefe und Einführfase.
- **Rillenstruktur:** rechteckig, V-förmig oder gerundet, mit einstellbarer
  Anzahl, Tiefe und Breite.
- **Beschriftung:** Text auf dem Deckel und auf der Wand, als Vertiefung oder
  als Farbeinlage im Mehrfarbdruck.
- **Mehrfarbmodus:** Körper, Deckel und Text als getrennte Farbgruppen.
- **Fünf fertige Varianten** für den Bambu Lab P1S.

![Rundes Gefäß mit gerundeten Rillen](images/03_rund-rillen.png)

## Entwicklungsprozess

Am Anfang standen im Juni 2026 ein rundes und ein eckiges Gefäß mit Deckel. Im
August wurden daraus fünf Referenzvarianten mit Profilen für den P1S: rund und
hoch, rund mit Rillen, eckig mit V-Rillen, rund mit feinen Rillen und eckig mit
großem Eckenradius. Danach kam die Beschriftung auf Deckel und Wand dazu. Die
Beispielbilder zeigen Aufschriften wie COFFEE, HONEY und
TEA.

## Technische Hintergründe

**Der Deckel.** Der Deckel besteht aus einer Platte, die rundum 0,5 mm über das
Gefäß hinaussteht, und einem dünnwandigen Rand. Der Rand ist so groß wie der
Innenraum minus zweimal `fit_clearance`. Seine Wand ist mindestens 1,5 mm dick
(oder die halbe Gefäßwand, wenn das mehr ist). Eine Fase an der Spitze führt den
Rand beim Aufsetzen.

**Die Rillen.** Bei runden Gefäßen sitzen die Rillen gleichmäßig am Umfang. Bei
eckigen Gefäßen verteilt das Modell sie je Wand mit dem Abstand
Umfang / `relief_count` und hält um die Ecken `relief_corner` frei. Die
Rillentiefe wird auf `wall` − 0,8 mm begrenzt, damit mindestens 0,8 mm Wand
stehen bleiben.

**Der Text auf runder Wand.** Jeder Buchstabe sitzt auf seiner eigenen
Tangentialebene an seiner Bogenposition und wird radial in die Wand geschnitten.
Dadurch folgt die Schrift der Krümmung. Um den Text bleibt ein glatter Bereich
frei von Rillen (`text_panel_margin`); darüber und darunter laufen die Rillen
weiter.

**Die Farbeinlage.** Im Mehrfarbdruck ist der Text ein eigener Körper, der die
Vertiefung exakt füllt. Er ist tiefer als die Gravur im Einzelfarbdruck,
weil eine nur 0,6 mm dünne Haut an einer senkrechten Wand fadig druckt.

**Vorschau.** Die Vorschau-Modi zeigen das Gefäß zusammengebaut oder mit
daneben liegendem Deckel in zwei Farben und tragen ein rotes „NOT FOR
PRINTING“-Banner.

![Rechteckiges Gefäß mit V-Rillen](images/04_eckig-v-rillen.png)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für den **P1S** mit **Bambu PLA Basic** gebaut und im Slicer
getestet: 0,20 mm Layerhöhe, 2 Wände, 15 % Gyroid. Für belastete Gefäße
empfehle ich 3 oder mehr Wände und mehr Infill (30–40 %). Der Körper steht
aufrecht, der Deckel liegt auf seiner flachen Oberseite mit dem Rand nach oben;
Stützen sind nicht nötig. Für feinere Rillen kannst du auf 0,12–0,16 mm
Layerhöhe gehen.

Das Deckelspiel hängt vom Drucker ab: Sitzt der Deckel zu locker, verringerst du
`fit_clearance`; klemmt er, erhöhst du es.

Für die **Zweifarb-Ausgabe** (`Multicolor Export`) exportierst du den STL
direkt aus der OpenSCAD-Vorschau, ohne F6/Render und ohne Kommandozeile. Sonst
werden alle Gruppen zu einem Körper vereinigt, und die Farben gehen verloren.

## Einsatzideen

- Werkstattdosen mit Aufschrift an der Wand
- Ein Gefäß, das genau in ein Regalfach passt
- Vorratsdosen für Kaffee, Honig oder Tee mit Aufschrift auf Deckel und Wand
- Kleinteilegefäße für das Homelab: Patchkabel, SSDs, Schrauben
- Stifttöpfe mit feinen Rillen (ohne Deckel, `part = body`)

![Rundes Gefäß mit mehrfarbiger Aufschrift](images/05_text-kaffee-mehrfarbig.png)

## Fazit und Aufruf zum Mitmachen

Das Gefäß ist ein Baukasten für Dosen aller Art. Wenn du es druckst, freue ich
mich über **Makes** mit Fotos, besonders mit Beschriftung und eigenen Maßen.
Rückmeldungen zum Deckelspiel auf anderen Druckern helfen, die Voreinstellung zu
verbessern. Schreib einfach einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/2917278-parametric-vessel-with-friction-fit-lid

---

## 10 SEO-Titel

1. Vorratsdose 3D-drucken: parametrisches Gefäß mit Steckdeckel (OpenSCAD)
2. Parametrisches Gefäß für Bambu Lab: rund oder eckig, jede Größe
3. Gefäß mit Deckel 3D-Druck: Spiel einstellen mit `fit_clearance`
4. Dose mit Beschriftung 3D-drucken: Text auf Deckel und Wand
5. 3D-gedruckte Vorratsdose in Zweifarb-Optik: Text als Farbeinlage
6. Dose mit Rillenstruktur: rechteckig, V-förmig oder gerundet
7. Regalfach-Dose nach Maß: parametrisches Gefäß im Customizer
8. Aufbewahrungsdose ohne Stützen drucken: Körper und Deckel flach
9. Parametric Storage Vessel: One Model – Endless Designs
10. Gefäß mit Text auf gewölbter Wand: Buchstaben folgen der Krümmung

## 20 relevante Suchbegriffe

- Vorratsdose 3D-Druck
- Gefäß 3D drucken
- Dose mit Deckel 3D-Druck
- parametrische Dose
- parametrisches Gefäß OpenSCAD
- Storage Vessel 3D Print
- Container with lid 3D print
- Friction fit lid 3D print
- Dose mit Beschriftung 3D-Druck
- Gefäß Text Deckel Wand
- Dose mit Rillen 3D-Druck
- eckige Dose 3D-Druck
- runde Dose 3D-Druck
- Bambu Lab P1S Dose
- MakerWorld Gefäß
- Customizer Dose
- Mehrfarbdruck Dose
- Werkstattdose 3D-Druck
- Kleinteile Aufbewahrung 3D-Druck
- funktionale 3D-Drucke

## 10 GitHub-Tags

- storage
- container
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- lid
- functional-print

## 5 LinkedIn-Post-Ideen

1. „Ein Modell, jede Dose“: Wie ein parametrisches Gefäß Maßanfertigungen für
   Regalfächer ersetzt.
2. „Das richtige Spiel für einen Steckdeckel“: Warum `fit_clearance` als eigener
   Regler sinnvoll ist.
3. „Text auf gewölbten Wänden“: Buchstabe für Buchstabe auf die Tangentialebene
   gesetzt.
4. „Mehrfarbdruck ohne Slicer-Gefummel“: Farbeinlage im Text statt dünner Haut.
5. „Von zwei Dateien zu einem Customizer“: Entwicklung vom Einzelstück zum
   parametrischen Modell.

## 5 Reddit-Post-Ideen

1. r/functionalprint – „Parametric storage vessel with friction-fit lid, any
   size, round or rectangular“ mit dem Hero-Bild.
2. r/openscad – „Wrapping text around a cylinder, glyph by glyph“: Erklärung
   des Ansatzes ohne Quelltext.
3. r/BambuLab – „Two-colour lettering as flush inlay on a vase wall: export
   from the preview, not from F6“.
4. r/3Dprinting – „One customizer model for round and rectangular containers
   with grooved walls“.
5. r/3Dprinting – „Tuning the lid clearance on a printed container: what
   fit_clearance works for you?“ als Diskussionsfrage.
