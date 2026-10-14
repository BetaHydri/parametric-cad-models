# Münzsortierer 3D-Druck parametrisch: Gefäß, Einsatz und Deckel nach Maß

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3248811-ultimate-parametric-coin-sorter-drop-in-vessel – Profil:
<https://makerworld.com/en/@BetaHydri>

![Münzsortierer: blaues Gefäß mit Münzstapeln im Einsatz, daneben der Deckel](images/01_hero.jpg)

## Motivation: Kleingeld, das nicht im Weg liegt

Kleingeld sammelt sich in Schalen, Taschen und Schubladen. Ein Münzsortierer
löst das, aber fertige Modelle haben ein Problem: Sie passen zu einer
bestimmten Auswahl an Münzen und zu einem bestimmten Gefäß. Willst du mehr
2-Euro-Stücke, weniger Cent-Münzen oder US-Münzen, fängst du von vorn an.

Der **Ultimate Parametric Coin Sorter and Drop-in** dreht das um. Du wählst
die Münzen, und das Modell erzeugt **Gefäß, Deckel und Einsatz** gemeinsam,
passend zueinander. Als Maker-Projekt für den 3D-Druck ist es vollständig in
OpenSCAD geschrieben und läuft im MakerWorld-Customizer.

## Funktionen im Überblick

- **Euro oder US:** Maße nach EZB bzw. US Mint sind hinterlegt.
- **Fächer je Münze frei wählbar:** `0` bis `24` je Nennwert, zum Beispiel
  `n_2eur = 6` für sechs 2-Euro-Fächer.
- **Gefäß automatisch dimensioniert:** Rund oder rechteckig, passend zur
  Münzauswahl; alternativ eigene Maße mit `sizing_mode = manual`.
- **Höhe = Stapelhöhe:** Entweder `tray_height` direkt vorgeben oder mit
  `height_mode = auto` aus der gewünschten Münzanzahl ableiten.
- **Einsatz zum Herausheben:** Ein abgesenkter Mittelgriff, dazu eine
  Daumenaussparung an jedem Fach.
- **Drei Deckelarten:** Reibdeckel, Schraubkappe oder Spardosen-Deckel mit
  Münzschlitz.
- **Muster und Text:** Rillen, Rippen, Ringe, Diagonale, Karo, Noppen oder
  Facetten, dazu Gravur auf Wand und Deckel (nur runde Gefäße).
- **Mehrfarbig:** Gefäß, Einsatz und Deckel in eigenen Farben.

![Explodierte Vorschau: Gefäß, Einsatz mit Münzen, Deckel](images/02_vorschau-explodiert.jpg)

## Entwicklungsprozess

Das Projekt begann als Einsatz für zwei bestehende Gefäß-Modelle. Dann kam der
Wunsch, das Gefäß mitzuliefern und mit der Münzauswahl wachsen zu lassen. Die
Datei erzeugt deshalb heute alle drei Teile; die Passmathematik der
Vorgängerprojekte ist nachgebildet.

Am 1. September 2026 wurden die wichtigsten Punkte gelöst: ein messbar
passender Einsatz, eine kompaktere Anordnung der Fächer, Zähler statt
Ein-/Aus-Schaltern je Münze und die Übernahme der Musterbibliothek aus dem
Schraubglas-Projekt. Die Vorschau zeigt alles explodiert mit rotem
„NOT FOR PRINTING“-Banner, damit sie nicht versehentlich gedruckt wird.

## Technische Hintergründe

**Fächer aus den Münzmaßen.** Der Fachdurchmesser ist Münzdurchmesser plus
`coin_clearance` (Standard 0,6 mm) plus zweimal `well_wall` (1,6 mm). Die
Tiefe folgt aus der Stapelhöhe.

**Revolver-Anordnung.** Bei runden Einsätzen stehen die Fächer auf einem Ring
um den Mittelgriff. Ein Solver nimmt für jedes Nachbarpaar nur den Platz, den
beide Fächer brauchen, und sucht per Bisektion den kleinsten Ringradius, bei dem
alle Winkel zusammen 360° ergeben. Beim Euro-Vollsatz sank der
Einsatzdurchmesser so von 114,5 auf 100,7 mm. Für rechteckige Einsätze gibt es
ein ungerades Raster mit reservierter Mittelzelle für den Griff.

**Passung.** Der Einsatz füllt das Gefäß bis auf `tray_fit`, Standard 0,15 mm
je Seite. Der Wert wurde am Mesh nachgemessen. Beim Reibdeckel sitzt der
Deckelrand im Freiraum über dem Einsatz, daher darf der Einsatz die volle Breite
nutzen und klappert nicht. Der Innenradius am Gefäßboden ist am Einsatz
ausgespart, damit er flach aufliegt.

**Schraubglas.** Das Gewinde stammt aus der Bibliothek BOSL2: grobe Steigung
(2,8 mm), drei Windungen, `thread_slop` 0,12 mm als Druckspiel. Das Schraubglas
gibt es nur rund; wählst du rechteckig, nimmt das Modell automatisch den
Reibdeckel.

**Konsolenausgabe.** Das Modell nennt bei jeder Änderung die Gefäßgröße und
wie viele Münzen jedes Fach aufnimmt. Mit den Standardwerten (Stapeltiefe
26 mm) ergibt der Euro-Vollsatz ein rundes Gefäß mit 105,81 mm Durchmesser und
37,4 mm Höhe; die rechteckige Variante misst 98,15 × 98,15 mm.

![Rechteckige Variante mit Raster-Einsatz](images/04_variante-rechteckig.jpg)

## Druck-Erfahrungen und Empfehlungen

Die mitgelieferten Profile sind für **Bambu Lab P1S** mit **Bambu PLA Basic**
gebaut und im Slicer getestet: 0,20 mm Layerhöhe, drei Wände, Gyroid mit 15 %.
Alle Teile drucken ohne Stützen. Gefäß und Einsatz stehen aufrecht, der Deckel
liegt auf der Oberseite, die Schraubkappe öffnet nach unten.

Passt etwas nicht, helfen drei Stellschrauben: Ist der Einsatz zu stramm,
erhöhe `tray_fit` auf 0,20 mm. Sitzt der Reibdeckel lose, verringere
`fit_clearance` um 0,02–0,03 mm; bei der Schraubkappe gilt das für
`thread_slop`. Bei PETG sind die Spiele um etwa 0,05 mm zu erhöhen, weil es
etwas breiter druckt.

Für den Mehrfarbdruck exportierst du `Multicolor Export` direkt aus der
OpenSCAD-Vorschau. Ein Export über F6 oder die Kommandozeile vereinigt alles zu
einem Objekt. Im Slicer weist du dann jedem Teil ein Filament zu; mit der
Druckreihenfolge „Nach Objekt“ fällt kaum Spülmaterial an.

## Einsatzideen

- Kleingeld-Sortierer für Schreibtisch oder Regal mit Euro-Vollsatz
- Münzvorrat mit sechs 2-Euro-Fächern und Wandtext
- US-Satz für Reisen oder Sammler
- Spardose aus Gefäß und `lid_slot` mit Wandtext
- Kompakter Satz für die vier größten Euro-Münzen mit Schraubglas

![Schraubglas mit Noppenmuster](images/05_variante-schraubglas.jpg)

## Fazit und Aufruf zum Mitmachen

Der Coin Sorter ist ein Werkzeug für deinen eigenen Münzbedarf, kein
festes Einzelstück. Das Modell mit den Bambu-Studio-Profilen findest du auf
**MakerWorld**. Ich freue mich über **Makes**, Fotos deiner Konfigurationen und
Rückmeldungen zu Passung und Spiel bei anderen Druckern und Materialien. Fehlt
dir eine Münze oder eine Anordnung, schreib einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3248811-ultimate-parametric-coin-sorter-drop-in-vessel

---

## 10 SEO-Titel

1. Münzsortierer 3D-Druck parametrisch: Gefäß, Einsatz und Deckel nach Maß
2. Coin Sorter für Euro und US-Münzen: OpenSCAD-Modell für Bambu Lab
3. Münzeinsatz mit Revolver-Anordnung: Kleingeld sortiert aufbewahren
4. Spardose 3D-Druck mit Münzschlitz: parametrisch und anpassbar
5. Münzhalter mit Schraubdeckel drucken: grobes Gewinde, robust und einstellbar
6. Kleingeld sortieren: 3D-gedruckter Einsatz zum Herausheben mit Mittelgriff
7. Münzbox rund oder rechteckig: Größe automatisch aus der Münzauswahl
8. Mehrfarbiger Münzsortierer für Bambu Lab P1S, P2S und H2C
9. Parametrischer Coin Organizer: Fächer je Münze frei wählbar
10. 2-Euro-Münzen sortieren: Münzrollen-Ersatz aus dem 3D-Drucker

## 20 relevante Suchbegriffe

- Münzsortierer 3D-Druck
- Coin Sorter 3D Print
- Münzhalter 3D-Druck
- Münzbox parametrisch
- Kleingeld Organizer 3D-Druck
- Euro Münzen Halter
- US Coin Holder 3D Print
- Spardose 3D-Druck
- Münzschlitz Deckel
- Münzeinsatz herausnehmbar
- Coin Tray Insert
- OpenSCAD Münzhalter
- OpenSCAD Customizer Münzen
- MakerWorld Münzsortierer
- Bambu Lab Münzbox
- Schraubdeckel Dose 3D-Druck
- BOSL2 Gewinde Dose
- 3D-Druck Aufbewahrung Münzen
- 2-Euro-Münzen aufbewahren
- mehrfarbiger 3D-Druck Dose

## 10 GitHub-Tags

- coin-sorter
- coin-holder
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- piggy-bank
- functional-print
