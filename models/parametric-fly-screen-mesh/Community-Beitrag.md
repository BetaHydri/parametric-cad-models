# Fliegengitter 3D-drucken: Parametrisches Insektengitter mit Verbindungs-Clips für Bambu Lab

👉 **MakerWorld-Link:** https://makerworld.com/en/models/2915026-parametric-fly-screen-mesh-filter-net – Profil:
<https://makerworld.com/en/@BetaHydri>

![Zwei Fliegengitter-Stücke, mit Kamm-Clips an der Naht verbunden](images/01_hero.png)

## Motivation: Ein Gitter, das der Slicer versteht

Ein Fliegengitter aus dem 3D-Drucker klingt trivial: Stege kreuzen, fertig.
In der Praxis ist es einer der anspruchsvollsten Drucke für den Slicer. Die
Stege sind nur eine Düsenbreite dick, die Maschen klein, und der Slicer soll
daraus eine zusammenhängende Einzelwand machen statt Boden, Deckel und Infill.
Wer Stegbreite und Schichthöhe nicht auf die Düse abstimmt, bekommt lückige
Gitter oder einen Block aus Füllung.

Der **Parametric Fly Screen Mesh** löst das, indem er alles aus der **Düse**
ableitet. Du wählst 0,2, 0,4 oder 0,6 mm, und Strandbreite, Schichthöhe und
Teilung ergeben sich automatisch. Form, Größe, Maschenweite und Dicke stellst du
im MakerWorld-Customizer ein.

## Funktionen im Überblick

- **Düsengetrieben:** Strandbreite = Düse + 0,05 mm; Schichthöhe 0,10 mm
  (0,2-mm-Düse), 0,20 mm (0,4 mm) oder 0,28 mm (0,6 mm).
- **Rund oder quadratisch:** frei von 20 bis 300 mm oder per Preset (80 mm und
  100 mm rund, 100 mm und 200 mm quadratisch, volle Betten mit 256 mm und
  300 mm).
- **Maschenweite einstellbar:** `mesh_opening` von 0,8 bis 5,0 mm.
- **Dicke wählbar:** `num_layers` von 2 bis 6 Schichten.
- **Slicer-Vorgaben im Modell:** Die Konsole nennt Schichthöhe, 1 Wand, 0 %
  Infill und Dünnwand-Erkennung.
- **Kamm-Clips:** flache Verbinder, die zwei Gitterkanten in der Gitterebene
  greifen. Ohne Stützen druckbar.

![Gitter-Nahaufnahme in der Draufsicht](images/05_netz-nahaufnahme.png)

## Entwicklungsprozess

Das Gitter war zuerst da: ein Düsen-getriebenes Modell, bei dem die Geometrie
als 2D-Raster entsteht und mit **einem** `linear_extrude` in die dritte Dimension
gehoben wird. Das ist wichtig, weil ein Gitter mit Hunderten von Stegen als
Einzelquader-Konstruktion Vorschau und Export zäh macht. Als 2D-Vereinigung
bleibt auch ein Gitter für das volle Druckbett schnell exportierbar.

Dann kam die Frage, wie sich einzelne Stücke verbinden lassen. Die ersten
Clip-Formen (`tiny_snap` und `side_slide`) haben ihren Schlitz nach der **Dicke**
des Gitters bemessen und waren unten offen. Das funktioniert nur, wenn das Gitter
senkrecht steht – bei einem flach liegenden Gitter ist das die falsche Geometrie.
Heraus kam der **liegende Kamm**: ein flacher Clip, der in der Gitterebene
liegt. Zwei Gitterkanten stoßen an einen Mittelsteg und werden zwischen Boden und
einer Reihe von Fingern geklemmt.

## Technische Hintergründe

**Raster aus der Düse.** Aus der Ziel-Maschenweite und der Strandbreite ergibt
sich die Ziel-Teilung. Das Modell teilt die innere Spannweite durch diese
Teilung, rundet auf ganze Intervalle und rechnet die tatsächliche Teilung
zurück. So schließt das Gitter an beiden Rändern mit einem Steg ab, und die
Maschenweite weicht nur minimal vom Eingabewert ab. Beispiel bei 0,4-mm-Düse und
100 mm: 49 Intervalle, Teilung ca. 2,03 mm, Maschenweite ca. 1,58 mm, 50 Stege je
Achse.

**Der Kamm im Detail.** Ein durchgehender Boden liegt unter beiden Gitterkanten,
ein hoher Mittelsteg wirkt als Anschlag und trägt die Finger. Die Finger ragen
von diesem Steg als Kragarme über das Gitter. Die Schlitzhöhe beträgt
Gitterdicke plus `comb_slot_clear` (Standard 0,10 mm); mit einem mittig
liegenden Gitter bleiben oben und unten je 0,05 mm Luft. Weil der Schlitz aus der
Gitterdicke berechnet wird, passen Clip und Gitter nur zusammen, wenn beide mit
derselben Düse und Schichtzahl erzeugt werden.

**Prüfung statt Augenmaß.** Die Passung wurde mit einem kleinen
Prüfaufbau belegt: Clip und Gitterstücke werden im gemeinsamen Koordinatensystem
ausgegeben, die Interferenz wird über das **Überlappungsvolumen** bewertet (nicht
über die Dreieckszahl, denn zwei Körper, die sich nur an einer Fläche berühren,
liefern nahezu null Volumen) und das Spiel über den Mindestabstand der
Oberflächen. Dazu kommen Druckbarkeitsgrenzen gegenüber der Düse. Die
Standardkonfiguration bestand die Prüfung mit 0,05 mm Spiel und ohne
Überlappung. Ein Detail dabei: Die Eindringtiefe der Finger (`comb_chan_depth`)
soll höchstens etwa 2,0 mm betragen, sonst hängt der Kragarm beim Druck durch.

![Kamm-Clip an der Naht im Detail](images/03_kamm-clip-detail.png)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für **Bambu Lab P2S** mit **Bambu PETG Basic** gebaut und im
Slicer getestet: 0,4-mm-Düse, 0,20 mm Schichthöhe, 1 Wand, Gyroid mit 0 %
Infill. Entscheidend sind drei Dinge:

- **Schichthöhe = Anfangsschichthöhe.** Das Modell weist ausdrücklich darauf hin.
- **1 Wandlinie, keine Boden- und Deckschichten, 0 % Infill**, und die
  **Dünnwand-Erkennung** eingeschaltet, damit der Slicer jeden Steg als Linie
  druckt.
- **PETG** wird empfohlen, weil es flexibel und haltbar ist; PLA lässt sich
  ebenfalls drucken.

Das Gitter und die Clips liegen flach auf dem Bett. Stützen sind nicht nötig.

**Gitter verbinden:** Beide Kanten mit dem Abstand der Mittelstegbreite
(`comb_spine_w`, Standard 1,0 mm) nebeneinanderlegen und die Clips entlang der
Naht aufdrücken. Jede Kante gleitet unter eine Fingerreihe, der Steg hält die Naht
in Position.

## Einsatzideen

- Insektenschutz für kleine Öffnungen mit `80mm Round` oder `100mm Round`
- Staub- und Insektenschutz an Lüfteröffnungen von Gehäusen und Racks
- Größere Flächen aus mehreren Quadraten, verbunden mit Kamm-Clips
- Sieb- oder Filter-Einsätze mit gewählter Maschenweite
- Ein 20-mm-Teststück vorab, um Maschenweite und Haftung zu prüfen

![Rundes Gitter, 80 mm, Draufsicht](images/06_netz-rund-80mm.png)

## Fazit und Aufruf zum Mitmachen

Das Besondere an diesem Modell ist weniger die Optik als die Abstimmung: Düse,
Strandbreite, Schichthöhe und Slicer-Einstellungen passen von Anfang an
zusammen, und die Clips sind für flach liegende Gitter gebaut statt für eine
andere Geometrie. Auf **MakerWorld** findest du das Modell mit den
Bambu-Studio-Profilen. Ich freue mich über **Makes**, über Fotos von deinen
Einsatzorten und über Rückmeldungen zu Maschenweite, Material und Clip-Passung bei
anderen Druckern und Düsen.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/2915026-parametric-fly-screen-mesh-filter-net

---

## 10 SEO-Titel

1. Fliegengitter 3D-drucken: parametrisches Insektengitter für Bambu Lab
2. Fliegengitter aus dem 3D-Drucker: Düse wählen, Maschenweite einstellen
3. 3D-gedrucktes Insektengitter mit Kamm-Clips verbinden
4. Fliegengitter für Lüftungsöffnungen drucken: Einstellungen für PETG
5. Parametrisches Gitter in OpenSCAD: rund, quadratisch, 20 bis 300 mm
6. Gitter mit Einzelwand drucken: 1 Wand, 0 % Infill, Dünnwand-Erkennung
7. Fliegengitter-Clip aus dem 3D-Drucker: der liegende Kamm
8. Fliegengitter für P2S, P1S und H2C: Profile und Parameter
9. Große Gitterflächen aus Kacheln drucken und verbinden
10. Mesh-Gitter 3D-Druck: Strandbreite und Schichthöhe passend zur Düse

## 20 relevante Suchbegriffe

- Fliegengitter 3D-Druck
- Insektengitter 3D drucken
- 3D-gedrucktes Gitter
- parametrisches Gitter OpenSCAD
- fly screen mesh 3D print
- 3D print mesh grid
- Gitter mit Einzelwand drucken
- Dünnwand-Erkennung Bambu Studio
- Bambu Lab Fliegengitter
- Bambu P2S PETG Gitter
- MakerWorld Fliegengitter
- Lüftungsgitter 3D-Druck
- Insektenschutz Lüftungsöffnung
- Gitter verbinden Clip 3D-Druck
- Kamm-Clip Gitter
- Gitter 0,4 mm Düse Einzelstrang
- Maschenweite einstellen 3D-Druck
- Gitter rund 100 mm drucken
- OpenSCAD Customizer Gitter
- funktionale 3D-Drucke

## 10 GitHub-Tags

- fly-screen
- mesh
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- fdm
- customizer
- functional-print

## 5 LinkedIn-Post-Ideen

1. **Düsen-getriebene Konstruktion:** Wie ein Parameter (die Düse) Strandbreite,
   Schichthöhe und Teilung eines ganzen Modells bestimmt – und warum das Fehler
   im Slicer vermeidet.
2. **Prüfen statt schätzen:** Wie ich die Passung eines Clips mit
   Überlappungsvolumen und Mindestabstand statt Augenmaß belegt habe.
3. **Wenn der erste Entwurf falsch ist:** Warum die ersten Clip-Formen nur bei
   senkrecht stehenden Platten funktionierten und der liegende Kamm die Lösung
   war.
4. **Schnell exportieren:** 2D-Raster plus ein `linear_extrude` statt tausender
   Quader – eine kleine Modellierungsentscheidung mit großer Wirkung.
5. **Parametrik für Maker:** Ein Customizer-Modell, das von 20 bis 300 mm
   skaliert, ohne dass der Slicer überfordert wird.

## 5 Reddit-Post-Ideen

1. **r/3Dprinting:** „Fliegengitter aus einer Wand gedruckt – Düse bestimmt
   Strandbreite und Schichthöhe“ mit Nahaufnahme des Rasters.
2. **r/BambuLab:** „Einzelstrang-Gitter auf der P2S: 1 Wand, 0 % Infill,
   Dünnwand-Erkennung – meine Einstellungen“.
3. **r/openscad:** „Gitter mit 2D-Union und einem linear_extrude statt vieler
   Quader – Vorschau bleibt schnell“.
4. **r/functionalprint:** „Kamm-Clip verbindet zwei flache Gitterstücke ohne
   Kleber, Druck ohne Stützen“.
5. **r/homelab:** „Staub- und Insektenschutz für Lüfteröffnungen eines Racks:
   parametrisches Gitter, rund oder quadratisch“.
