# Pillendose 3D-drucken: parametrischer Wochendosierer mit Scharnier- oder Reibdeckeln, stapelbar

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3120609-ultimate-parametric-pill-box – Profil:
<https://makerworld.com/en/@BetaHydri>

![Weekly Pill Organizer – die Designs im Überblick](images/01_hero.png)

## Motivation: Die Dose, die zu deinen Tabletten passt

Wochendosierer aus dem Laden haben ein festes Raster. Die große Kapsel passt
nicht, die Morgen-Mittag-Abend-Trennung fehlt, und der dünne Klappdeckel bricht
am Scharnier. Ein eigenes Modell lässt sich an die Tabletten anpassen – dafür
muss die Konstruktion aber im Druck funktionieren: Scharniere, die nicht
verschmelzen, Deckel, die halten, und Dosen, die sich stapeln lassen. Die
**Parametric Pill Box** sammelt das in einer Datei mit drei Deckelkonzepten.
Du stellst Tage, Fachgröße und Unterteilung im MakerWorld-Customizer ein.

## Funktionen im Überblick

- **Drei Designs:** `Hinged lids` (Klappdeckel mit Print-in-Place-Scharnier),
  `Friction + collar stack` (lose Reibdeckel, Stapel-Kragen) und
  `Friction + foot stack` (lose Reibdeckel, segmentierte 45°-Füße).
- **1–14 Tage je Streifen**, bis zu 6 Streifen auf einer Platte (`rows`).
- **Freie Fachgröße:** `day_w`, `day_len`, `well_depth`; bis zu 4 Unterfächer
  pro Tag (`subdiv`) für Morgen, Mittag, Abend.
- **Rampe zum Herausnehmen:** `front_fillet` rundet nur die Kante zwischen
  Fachboden und Vorderwand.
- **Beschriftung:** Wochentage (DE/EN, 1–3 Buchstaben) oder Zahlen, bei Design
  A auch erhaben innen; Freitext auf Front, Rückseite oder Stirnseite.
- **Snap-Verschluss** (Design A) mit einstellbarer Klickkraft `latch_grip`.
- **Mehrfarb-Export** für Körper, Deckel und Text.
- **Bauraum-Prüfung** für A1 mini, P1S/P2S, H2C und H2D.
- **Acht fertige Varianten** für den Bambu Lab P1S.

![Design A mit drei Unterfächern pro Tag](images/02_design-a-scharnier-3-faecher.png)

## Entwicklungsprozess

Am Anfang stand eine Referenz-Dose (STEP/STL), die ich mit OCP
(OpenCascade für Python) zerlegt habe: Zylinderflächen herausfiltern, Radien und
Achslagen auslesen, Segmentmuster aus den Lücken ableiten. Daraus ergaben sich
die Scharnierachse und das Print-in-Place-Prinzip. Die ersten Dateien stammen
vom 31. Juli 2026.

Der erste Testdruck am 1. August 2026 zeigte, was im CAD nicht sichtbar war.
Der Versteifungssteg hing geschlossen tiefer als die Deckelplatte und stieß an
Wände und die hinteren Fachecken. Der Snap-Verschluss saß zu weit hinten. Später
blieb der Deckel um wenige Grad offen, obwohl eine Kollisionsprüfung im CAD
leer war – mit Schleifpapier an der hinteren Wandkante schloss er sauber. Seitdem
hat die Klappkante eine Fase. Das Scharnierspiel verschiebt die tatsächliche
Drehachse genug, dass eine im CAD kollisionsfreie Kante im Druck trotzdem
berührt.

Am 9. August kam das zweite Design mit losen Reibdeckeln, am 10. und 11. August
wurde das Stapeln neu gedacht: Die erste Lösung (Fuß und Nut im Deckel)
erzwang einen gebrückten Nutboden am liegenden Deckel. Ein flacher Taschenboden
bleibt eine Brücke, egal wie das Bridging eingestellt ist. Also wanderte das Stapelmerkmal an die Box: ein
Kragen mit Auflage, in den die nächste Box mit ihrer 45°-Fase einrastet. Am
11. Oktober 2026 wurden die drei Designs in eine Datei zusammengeführt, und
auf Hinweis aus der Community kam `front_fillet` dazu.

## Technische Hintergründe

**Die Scharnierachse.** Ein flacher Deckel deckt die Box nur ab, wenn die
Achse auf halber Höhe von Box plus Deckel liegt. Eine tiefe Achse klappt den
Deckel nach unten – das wäre eine Klappschale. Die Faltung um 180° ist ihre
eigene Umkehrung, daher wird der Verschluss in geschlossener Lage modelliert
und in die Drucklage gedreht.

**Der Steg.** Die Deckelsegmente bestehen aus Barrel und einem Block bis zur
Achsenmitte; die Stiftbohrung wird erst danach gebohrt. Wäre der Block unter der
Bohrung abgeschnitten, bliebe eine dünne Berührlinie. Ein Steg bindet alle
Segmente zu einem steifen Träger und liegt geschlossen hinter der Rückwand.

**Der Snap.** Eine scharfe Dreiecksspitze druckt auf der 0,4-mm-Düse nicht auf
die volle Höhe. Die Rippe hat deshalb eine flache Spitze. Weil der Deckel auf
einem Bogen schließt, hebt die Öffnungsbewegung die Rippe nach oben aus der Nut;
eine höhere Rippe vergrößert das Fenster, in dem sie hält.

**Der Reibdeckel.** Der Deckelrand taucht mit `lid_fit` Spiel in das Fach.
Bei mehreren Unterfächern gibt es eine Schürze je Unterfach. Kleine Zellen
bestehen fast nur aus Eckenradius und halten schwächer; das Spiel wird dort
automatisch etwas enger.

**Der Stapel-Kragen.** Die Fächer sitzen nach innen versetzt zum äußeren Kragen,
sodass die Wandoberkanten eine umlaufende Auflage für die Deckel bilden. Die
Deckel sitzen versenkt. Der 45°-Trichter des Kragens nimmt die 45°-Fase der
nächsten Box auf. Zwei Bedingungen entscheiden, ob es funktioniert: Die Fase
muss größer sein als die Kragenwand, und die Deckel müssen tiefer liegen als die
Fase hoch ist – sonst rammt der Fuß die Deckel oder die Box sitzt nur Rand auf
Rand.

![Design B: gestapelte Dosen mit Kragen](images/03_design-b-kragen-stapel.png)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für den **P1S** mit **Bambu PLA Basic** gebaut und im Slicer
getestet: 0,20 mm Layerhöhe, 3 Wände, 15 % Gyroid. Das Scharnier läuft nach dem
Druck leichtgängiger, wenn du jeden Deckel einmal bewegst; feinere Layer
(0,16 mm) helfen. Bei Klemmen erhöhst du `hinge_gap`, bei Wackeln verringerst
du ihn.

Das Reibdeckel-Spiel hängt vom Drucker ab: Der Standard von 0,07 mm je Seite
greift auf Bambu-Druckern fest. Fällt der Deckel kopfüber heraus, geh Richtung
0,00; sitzt er zu fest, auf 0,10–0,15. Bei Design C hat der Nutboden im Deckel
eine kurze Brücke – für PLA nutze ich Brückenfluss 1,5 bei 25 mm/s, für PETG
1,4 bei 15 mm/s, jeweils 45° und volle Kühlung.

Für den **Mehrfarb-Export** exportierst du den STL direkt aus der
OpenSCAD-Vorschau, ohne F6/Render und ohne Kommandozeile. Sonst werden die
Farbgruppen zu einem Körper vereinigt.

## Einsatzideen

- 7-Tage-Wochendosierer mit Wochentagen auf den Deckeln
- Morgens, mittags, abends mit `subdiv = 3`
- Zwei oder vier Wochen als mehrere Streifen
- Dosen mit Namen für Familienmitglieder
- Stapelbare Dosen für Schublade oder Reisetasche
- Kleinteile-Organizer statt Pillen: Schrauben, Schmuck, Nähzeug

![Design B: einzelne Box](images/04_design-b-einzelbox.png)

## Fazit und Aufruf zum Mitmachen

Die Pillendose ist ein Baukasten für Tablettendosen aller Art. Wenn du sie
druckst, freue ich mich über **Makes** mit Fotos, besonders mit ungewöhnlichen
Fachmaßen und Beschriftungen. Rückmeldungen zu Scharnierspiel und Reibdeckel-Sitz
auf anderen Druckern helfen, die Voreinstellungen zu verbessern. Schreib einfach
einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3120609-ultimate-parametric-pill-box

---

## 10 SEO-Titel

1. Pillendose 3D-drucken: parametrischer Wochendosierer (OpenSCAD)
2. Wochendosierer mit Print-in-Place-Scharnier: ohne Zusammenbau drucken
3. Tablettenbox nach Maß: Fachgröße und Unterteilung im Customizer
4. Stapelbare Pillendose für Bambu Lab: Kragen oder Füße
5. Morgens-Mittags-Abends-Dose 3D-drucken: bis zu vier Unterfächer
6. Pillenbox mit Namen und Wochentagen: Text graviert oder erhaben
7. Print-in-Place-Scharnier konstruieren: Achse auf halber Höhe
8. Reibdeckel richtig einstellen: `lid_fit` für jeden Drucker
9. Parametric Pill Box: One File – Three Lid Designs
10. Pillendose mit Rampe: Tabletten gleiten nach vorne heraus

## 20 relevante Suchbegriffe

- Pillendose 3D-Druck
- Wochendosierer 3D drucken
- Tablettenbox 3D-Druck
- Pillenbox parametrisch
- Medikamentenbox 3D-Druck
- Pill organizer 3D print
- Weekly pill box 3D print
- Print-in-place hinge
- Print-in-Place Scharnier
- Stapelbare Dose 3D-Druck
- Friction fit lid
- Reibdeckel 3D-Druck
- OpenSCAD Customizer Pillendose
- Wochentage Dose beschriften
- Morgens Mittags Abends Pillendose
- Bambu Lab P1S Pillendose
- MakerWorld Pillendose
- Dose mit Unterfächern
- Dose mit Namen 3D-Druck
- funktionale 3D-Drucke

## 10 GitHub-Tags

- pill-box
- organizer
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- print-in-place
- functional-print

## 5 LinkedIn-Post-Ideen

1. „Warum ein Scharnier auf halber Höhe liegen muss“: Die Geometrie hinter dem
   Print-in-Place-Deckel.
2. „CAD-kollisionsfrei ist nicht druckkollisionsfrei“: Warum die Klappkante eine
   Fase bekam.
3. „Die Brücke wegkonstruieren statt tunen“: Stapelmerkmal vom Deckel an die Box
   verlegt.
4. „Ein Referenzteil reverse-engineeren“: Eine Dose mit OCP in Barrel, Stift und
   Segmentmuster zerlegen.
5. „Feedback aus der Community, ein Parameter mehr“: Wie `front_fillet` entstand.

## 5 Reddit-Post-Ideen

1. r/functionalprint – „Parametric weekly pill organizer: hinged print-in-place
   lids, 1–14 days, any compartment size“ mit dem Hero-Bild.
2. r/3Dprinting – „Print-in-place hinge: why the axis must sit at half height
   for the lid to fold over the box“.
3. r/BambuLab – „Stackable pill box with 45° collar, lids recessed, no
   supports“.
4. r/openscad – „Detecting self-colliding hinge parts: intersection test and
   bounding box of the overlap“ ohne Quelltext.
5. r/3Dprinting – „Friction-fit lid clearance on a printed box: what lid_fit
   works for your printer?“ als Diskussionsfrage.
