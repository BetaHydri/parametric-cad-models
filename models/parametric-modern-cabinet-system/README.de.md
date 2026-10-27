# Parametric Modern Cabinet System – Offene Regale und Türschränke als Mehrplatten-Bausatz

[← Alle Modelle im Überblick](../../README.de.md)

🌐 [English](README.md) | **Deutsch**

Parametrische, moderne, **druckbare Schränke und Regale** für Bambu-Lab-Drucker:
ein offenes Standregal, ein Schrank mit einer Tür oder ein Sideboard mit zwei
Türen. Jede große Platte wird in bauplattengroße Kacheln geschnitten und als
**Bausatz auf getrennten Druckplatten** für den **P2S (256 mm)** und den **H2C
(330 × 320 mm)** geliefert. Böden gleiten in Schwalbenschwanz-Nuten, die Türen
hängen an **verdeckten, gedruckten Scharnieren**.

[![MakerWorld](https://img.shields.io/badge/MakerWorld-Modell-00AE42)](https://makerworld.com/en/models/3501978-parametric-modern-cabinet-system)
![OpenSCAD](https://img.shields.io/badge/OpenSCAD-parametrisch-yellow)
![Bambu Lab](https://img.shields.io/badge/Bambu%20Lab-P2S%20%7C%20H2C-green)
![Druckdateien](https://img.shields.io/badge/Druckdateien-nur%20MakerWorld-blue)

> **Das Modell mit allen Druckprofilen gibt es ausschließlich auf MakerWorld:**
> 👉 [MakerWorld-Link: https://makerworld.com/en/models/3501978-parametric-modern-cabinet-system](https://makerworld.com/en/models/3501978-parametric-modern-cabinet-system)
>
> ![Parametric Modern Cabinet System – Flurschrank, offenes Regal und Sideboard](images/01_hero.jpg)

Im MakerWorld-Customizer stellst du Größe, Anzahl der Böden, Türtyp und Griff
ein. Das Modell berechnet Kacheln, Fugen, Verbindungen, Türen und Scharniere
passend dazu, **verteilt alle Teile selbst auf Druckplatten** und exportiert
**eine 3MF mit einer Platte je Druckauftrag**. Drei geprüfte Bausätze gibt es
zusätzlich als fertige 3MF-Projekte.

## Inhaltsverzeichnis

- [Highlights](#highlights)
- [Enthaltene Bausätze](#enthaltene-bausätze)
- [Montage in Kürze](#montage-in-kürze)
- [Montageanleitungen (PDF und Markdown)](#montageanleitungen-pdf-und-markdown)
- [Parametrische Optionen](#parametrische-optionen)
- [Welche Option wähle ich?](#welche-option-wähle-ich)
- [Scharniere und verstärkte Schraublöcher](#scharniere-und-verstärkte-schraublöcher)
- [Was muss ich kaufen?](#was-muss-ich-kaufen)
- [Verifikation](#verifikation)
- [Druckempfehlungen](#druckempfehlungen)
- [Grenzen](#grenzen)
- [Downloads](#downloads)
- [Lizenz](#lizenz)

## Highlights

- **Offen oder geschlossen:** Regal, eine Tür, zwei Türen (mehrere Türreihen),
  Sockel mit Fußraum (schwebend), optionale Rückwand.
- **Bausatz-Logik:** Große Platten werden in **Kacheln** geschnitten (P2S ≤ 244 mm,
  H2C ≤ 292 mm), verbunden durch eine stützenfreie **V-Nut-Feder-Fuge und
  Schmetterlingsschlüssel** (Zugbänder). Kacheln, Schlüssel, Scharniere und Griffe
  liegen auf getrennten Druckplatten.
- **Stabil und werkzeugfrei:** Böden, Deckel und Boden **gleiten in
  Halb-Schwalbenschwanz-Nuten** der Seitenwände (selbstspannend, vorn blind, durch
  die Rückwand gesichert). Optional versteckte **M4-Schrauben mit Mutter** oder
  **Flügelschrauben** (ohne Werkzeug).
- **Türen mit verdeckten, gedruckten Scharnieren:** Aufschlagtür auf
  **Print-in-Place-Bandscharnieren** (aus meinem *Hinge Designer*, flach in einem
  Rutsch gedruckt, kein Stift zum Einstecken). Sie sitzen in Taschen hinter der Tür
  und werden mit **M3-Senkkopfschrauben** befestigt. Außen sieht man nur Tür, Fuge
  und Griff. Alternativen: `pivot` (bündige Tür auf zwei verdeckten M4-Zapfen-
  schrauben mit Heat-Set-Einsätzen) und `knuckle` (Laschen und langer Stift).
- **Dort stabiler, wo geschraubt wird:** Jedes Schrauben- und Einsatzloch bekommt
  eine Verstärkungszone. Die 3MF enthält sie als *Modifier-Volumen*: nur um die
  Löcher **6 Wandlinien und 100 % Füllung**.
- **Deine Griffe:** M3–M6-Bohrbild (`handle_cc` 32 … 320 mm, gleiche Werte wie im
  Projekt [Parametric Furniture Handles](../parametric-furniture-handles/README.de.md)),
  Griffmulden oder ein **eingebauter gedruckter Bügelgriff**; Magnete als
  Türverschluss.
- **Verifiziert statt gedacht:** Druckprüfung, Kollision, Spiel, **simulierte
  Montage** (Schiebeweg-Kollisionstests) und Statik.
- **Matte-PETG-Optik:** Layerlinien, keine Stützen, keine sichtbaren Beschläge
  außer den optionalen Schrauben.

![Moderner Schrank im Flur](images/02_flurschrank.jpg)

## Enthaltene Bausätze

| Bausatz | Maße B × H × T (mm) | Drucker | Platten | Druckzeit | Filament | Verbindung | Türen |
|---|---|---|---|---|---|---|---|
| `mini-open-shelf-360x500-p2s` | 360 × 500 × 230 | P2S | 15 | 68 h | 2,7 kg | Stecken (werkzeugfrei) | – |
| `cabinet-1door-300x500-p2s` | 300 × 500 × 220 | P2S | 19 | 81 h | 3,2 kg | Schwalbenschwanz + M4-Schrauben | 1, verdeckte Scharniere, Griff, Magnete |
| `sideboard-2door-580x500-h2c` | 580 × 500 × 270 | H2C | 18 | 145 h | 5,8 kg | Schwalbenschwanz + Flügelschrauben | 2, verdeckte Scharniere, Griffmulden, Magnete |

PETG, 3 Wände, 15 % Gyroid, 0,2 mm, mit Bambu-Studio-Presets gesliced. Andere
Größen: Parameter im Customizer einstellen (siehe unten).

### Eigene Größe im Customizer bestellen

1. Größe, Böden, Türen, Scharnierart, Griff und Verbindungen einstellen.
2. **Drucker** wählen (Parameter `printer`) **und denselben Drucker im Betten-Menü
   der MakerWorld-Vorschau auswählen, BEVOR du herunterlädst** (noch einmal im
   Download-Dialog). Die 3MF trägt dieses Druckerprofil. P2S = jedes 256-mm-Bett
   (P2S, P1S, X1C …), H2C = großes Bett. MakerWorld prüft nur das Bett: auf einem
   kleineren Bett (A1 mini …) erscheint „Model cannot fit in plates".
3. Optional **zwei Farben** (`two_colors`): Türen und eingebauter Griff bekommen
   eine zweite Farbe, jede Farbe ist ein Filament in Bambu Studio. Türteile und
   Korpusteile liegen auf **getrennten Platten**, damit jede Platte einfarbig ist
   und keinen Reinigungsturm braucht.
4. **Generate, dann Download.** Du bekommst **eine 3MF mit einer Platte je
   Druckauftrag** (bis zu 36 Platten, Grenze von Bambu Studio), alle Teile mittig
   auf den Platten. Die *Assemble View* zeigt den fertigen Schrank mit offener
   Tür. Ein Schrank 500 × 800 mm mit einer Tür braucht etwa 27 Platten; sehr
   große Maße überschreiten 36 Platten und müssen verkleinert werden.
5. In Bambu Studio das Filament auf **PETG** stellen (die Presets starten mit PLA).

![Offenes Regal im Wohnzimmer](images/03_regal-wohnzimmer.jpg)

## Montage in Kürze

| Schritt | Was passiert |
|---|---|
| **1. Kacheln** | Feder in Nut, Schmetterlingsschlüssel in die Taschen der verdeckten Seite drücken. |
| **2. Böden** | Jede waagerechte Platte von hinten in die linke Seitenwand schieben. |
| **3. Rechte Seite** | Von vorn über alle Zapfen gleichzeitig aufschieben. |
| **4. Rückwand** | Sichert die Böden; Reibung oder M3-Schrauben. |
| **5. Türen** | Gedruckte Scharniere in ihre Taschen schrauben (Türrückseite und Vorderkante der Seitenwand, M3 × 10 Senkkopf), Tür schließen, Magnete einsetzen, Griff montieren. |
| **6. Wand** | Zwei Löcher im Deckel für Wandwinkel oder Kippschutz-Gurt — **Pflicht**. |

![Verdecktes Print-in-Place-Scharnier in seinen Taschen](images/05_verdecktes-scharnier.jpg)

## Montageanleitungen (PDF und Markdown)

Zu jedem Bausatz gibt es eine bebilderte Anleitung auf Deutsch und Englisch:
Bilder mit Pfeilen für die Schieberichtung, Nahaufnahmen von Schmetterlings-
schlüssel, Mutter und Scharnier, Zubehörliste, Druckplan je Bauplatte und eine
kurze Zusammenfassung der Prüfungen.

| Bausatz | PDF Deutsch | PDF Englisch | Markdown |
|---|---|---|---|
| Offenes Regal 360 × 500 | [Assembly-Guide-DE.pdf](guides/mini-open-shelf-360x500-p2s/Assembly-Guide-DE.pdf) | [Assembly-Guide-EN.pdf](guides/mini-open-shelf-360x500-p2s/Assembly-Guide-EN.pdf) | [DE](guides/mini-open-shelf-360x500-p2s/ASSEMBLY.de.md) · [EN](guides/mini-open-shelf-360x500-p2s/ASSEMBLY.md) |
| Schrank 300 × 500 | [Assembly-Guide-DE.pdf](guides/cabinet-1door-300x500-p2s/Assembly-Guide-DE.pdf) | [Assembly-Guide-EN.pdf](guides/cabinet-1door-300x500-p2s/Assembly-Guide-EN.pdf) | [DE](guides/cabinet-1door-300x500-p2s/ASSEMBLY.de.md) · [EN](guides/cabinet-1door-300x500-p2s/ASSEMBLY.md) |
| Sideboard 580 × 500 | [Assembly-Guide-DE.pdf](guides/sideboard-2door-580x500-h2c/Assembly-Guide-DE.pdf) | [Assembly-Guide-EN.pdf](guides/sideboard-2door-580x500-h2c/Assembly-Guide-EN.pdf) | [DE](guides/sideboard-2door-580x500-h2c/ASSEMBLY.de.md) · [EN](guides/sideboard-2door-580x500-h2c/ASSEMBLY.md) |

Zuerst den **Passungstest** drucken. Er enthält einen Schwalbenschwanz-Block,
einen Schmetterlingsschlüssel, zwei Scharniere und einen M3-Dom, damit du dein
Filament prüfen kannst, bevor du den Bausatz druckst.

## Parametrische Optionen

| Bereich | Parameter |
|---|---|
| Platten und Farben | `two_colors`, `body_color`, `door_color` (zweite Farbe für Türen und eingebauten Griff), `door_open` (Vorschauwinkel 0–110°, Standard 60°) |
| Schrankgröße | `cab_w`, `cab_h`, `cab_d`, `panel_t` (Seiten, Türen), `shelf_t` (Böden, Deckel, Boden), `shelf_count`, `plinth_h`, `kick_d`, `back_panel`, `back_t`, `wall_anchor` |
| Türen | `doors` (none / single_left / single_right / double), `door_comp` (Fächer mit Tür), `door_rows`, `reveal`, `handle` (none / bar = Löcher für eigene Griffe / knob / scoop / integrated), `handle_cc`, `handle_screw`, `handle_orient`, `handle_v`, `handle_edge`, `hp_*` (eingebauter Griff), `magnets`, `magnet_d`, `magnet_h` |
| Verbindungen | `joint` (plug / screw / thumbscrew), `dt_depth`, `dt_angle`, `fit`, `tenon_len`, `tenon_gap`, `seam_keys`, `back_fix` |
| Scharniere | `hinge_style` (**leaf** = verdecktes Print-in-Place-Scharnier, Standard / pivot / knuckle), `hinge_len`, `hl_gap` (Scharnierspiel), `hinge_inserts` (M3-Heat-Set-Einsätze statt selbstschneidender Schrauben), `insert_d`, `insert_len`, `pin_d`, `hinge_fit`, `hinge_pitch` (knuckle) |
| Drucker | `printer` (P2S = Kacheln bis 248 mm, passt auf jedes 256-mm-Bett wie P1S / X1C; H2C = Kacheln bis 296 mm für das große Bett), legt Kachel- und Plattengröße fest |

**Automatische Platten:** Bei jeder Einstellung wird neu gepackt: Kacheln,
Schmetterlingsschlüssel (+12 % Reserve), Stiftsegmente, Scharniere, Griffe und
Kappen liegen zeilenweise auf dem nutzbaren Bett (248 mm P2S, 296 mm H2C, 8 mm
Abstand), jede Platte ist mittig zum Bett. Die **Schlüssel in Schrankfarbe
drucken**, dann fallen sie im offenen Regal kaum auf.

## Welche Option wähle ich?

| Option | Was sie macht | Wann wählen |
|---|---|---|
| `back_fix = friction` | Rückwand sitzt per Reibung im Falz. **Keine Schrauben, kein Werkzeug.** Sichert die Böden trotzdem gegen Herausrutschen nach hinten. | Kleine oder leicht belastete Schränke und offene Regale. Ein paar Tropfen Kleber oder Klebeband machen sie dauerhaft. |
| `back_fix = screw_M3` | Dieselbe Rückwand plus **M3 × 16 Schrauben (selbstschneidend)** in die Hinterkante von Deckel, Boden und jedem Boden. Nichts klappert, die Rückwand kann nicht herausrutschen. **Braucht einen Schraubendreher.** | Hohe oder stark beladene Schränke, oder wenn er oft bewegt wird. |
| `joint = plug` | Nur Schwalbenschwänze, **ohne Werkzeug und ohne Hardware**. | Leichte Regale, von Hand auf- und abbauen. |
| `joint = screw` | Schwalbenschwanz plus versteckte **M4-Schraube mit Mutter** je Zapfenblock. | Festeste, dauerhafte Verbindung. |
| `joint = thumbscrew` | Schwalbenschwanz plus **M4-Flügelschrauben**, von Hand. | Fest, aber **werkzeugfrei** und wieder lösbar. |
| `handle = bar / knob` | Nur Löcher: du montierst **deine eigenen** Griffe. | Du nutzt *Parametric Furniture Handles* oder gekaufte Griffe. |
| `handle = scoop` | Griffmulde in der Türkante, nichts zu montieren. | Schlichter Look, keine Hardware. |
| `handle = integrated` | Gedruckter Bügelgriff als Teil des Bausatzes (eine M4-Schraube und Mutter je Steg). | Kompletter Bausatz aus einem Druckauftrag. |
| `hinge_style = leaf` *(Standard)* | Aufschlagtür, **Print-in-Place-Scharnier** hinter der Tür verborgen, **M3 × 10 Senkkopfschrauben** (2 je Flügel). Das Scharnier wird mitgedruckt. | Fast immer: sieht aus wie ein verdecktes Scharnier, Tür öffnet über 110°. |
| `leaf` + `hinge_inserts = true` | Wie oben, aber vorher **M3-Heat-Set-Einsätze** (Ø 4,0–4,2 mm, 5–6 mm lang) in die Scharniertaschen einschmelzen. | Türen werden sehr oft bewegt oder die Scharniere regelmäßig abgenommen. |
| `hinge_style = pivot` | Bündige Tür auf zwei verdeckten **M4-Zapfenschrauben** in **M4-Heat-Set-Einsätzen** in den Türenden, gedruckte Abdeckkappen. | Völlig bündige Tür in einer Reihe (Lötkolben nötig). |
| `hinge_style = knuckle` | Laschen an der Seitenwand, lange gedruckte Stifte (segmentiert). | Gar keine Schrauben im Scharnier gewünscht. |

Die Rückwandfugen sind einfache Nut-Feder-Fugen (6 mm sind für Schlüssel zu dünn):
ein paar Tropfen Kleber oder Klebeband auf der Rückseite machen sie dauerhaft.

## Scharniere und verstärkte Schraublöcher

Das Leaf-Scharnier ist eine Geometrie aus meinem
[Hinge Designer](../parametric-hinge-designer/README.de.md) (Preset „standard“,
4 mm Stift, 0,4 mm Spiel), in den Schrank eingebettet. Es druckt flach als zwei
getrennte Körper und schwenkt direkt nach dem Druck frei; geprüft ist 0–180°
ohne Berührung. Jede Seitenwand bekommt hinter jeder Scharniertasche einen kleinen
Dom nach innen, damit die Tasche eine dicke Wand für die M3-Schrauben behält, und
die Türen haben eine Freistellung, damit sie bis 110° ohne Berührung des Korpus
öffnen.

Um jedes Schrauben- und Einsatzloch enthält die **3MF** ein Modifier-Volumen
(Ring 3,5 mm breit): dort **6 Wandlinien, 100 % Füllung**, sonst 3 Wände und
15 % Gyroid. Das kostet nur etwa 1 g und 7 Minuten je Kachel, statt alles massiv
zu drucken. Reine STL-Dateien können keinen Modifier speichern: dort um die
Scharnierschrauben selbst 4–5 Wände einstellen.

M3 ist die kleinste Schraubengröße im ganzen Bausatz.

![Sideboard im Esszimmer](images/04_sideboard-esszimmer.jpg)

## Was muss ich kaufen?

- Steck-Regal (offenes Regal): **nichts**.
- Schwalbenschwanz-Schrauben: M4-Linsenkopfschrauben mit M4-Sechskantmuttern oder M4-Flügelschrauben mit Muttern.
- Rückwand (optional): M3 × 16 selbstschneidende Schrauben.
- **Scharniere: M3 × 10 Senkkopfschrauben (ISO 10642), 2 je Flügel.** Die Scharniere selbst werden gedruckt.
- Türverschluss: 8 × 3 mm Neodym-Scheibenmagnete (4 je Tür).
- Griffe: M4-Schrauben für eigene oder eingebaute Griffe.
- Wand: Schrauben und Dübel oder ein Kippschutz-Gurt.

Die genaue Liste mit Stückzahlen steht in der Montageanleitung jedes Bausatzes.

## Verifikation

Alle Prüfungen liefen an den echten exportierten Netzen und sind wiederholbar.

- **Montage simuliert**, Schritt für Schritt mit Schiebeweg-Kollisionstests: Böden
  von hinten, rechte Seite über alle Zapfen, Rückwand, Türen von vorn, Schwenk
  0–110°, Scharniere sitzen in ihren Taschen. Die Verriegelung ist nachgewiesen:
  Böden können nicht nach hinten oder vorn heraus, die Seiten lassen sich nicht
  spreizen.
- **Statik:** Schwerpunkt, **Kippen** (ein leerer freistehender Schrank dieser Art
  kippt schon bei wenigen kg auf der Vorderkante nach vorn, **Wandbefestigung ist
  Pflicht**), Bodenlast (Spannung und Durchbiegung ≤ L/200: Mini 15 kg, 1-Tür 20 kg,
  Sideboard 10 kg je Boden, gleichmäßig verteilt), Schlüsselfugen,
  Schwalbenschwanz-Pressung und -Schub, Scharnierlast.
- **Druckbarkeit:** Bettgröße, flach auf dem Bett, ein Körper je Teil, Überhänge,
  Fugen, Spiele; die exportierten Bauplatten werden auf Überlappung und
  Vollständigkeit geprüft.

Die Berechnungen verwenden vorsichtige Werte für gedrucktes PETG (E 600 MPa,
Biegung 8 MPa, Schlüsselzug 15 MPa). Das sind **Ingenieurs-Abschätzungen, kein
Prüfbericht**. Die Festigkeitswerte der Scharniere (M3-Ausziehkraft 120 N,
Einsatz 100 N) sind Annahmen. Passungstest drucken und den eigenen Aufbau
belasten, bevor du dich darauf verlässt.

## Druckempfehlungen

- **Material:** PETG, 3 Wandlinien, 15 % Gyroid, 0,2 mm Schichthöhe. Keine Stützen nötig.
- **Die fertigen 3MF der Bausätze verwenden** für verstärkte Schraubzonen: ein
  Customizer-Download kann keine Modifier-Volumen speichern, stelle um die
  Scharnierschrauben selbst **4–5 Wände** (und ≥ 40 % Füllung) ein oder drucke die
  Scharnierseiten mit 5 Wänden.
- **Zuerst den Passungstest** drucken: Schwalbenschwanz-Block (leichte Reibung),
  Schmetterlingsschlüssel (mit dem Daumen einzudrücken), Scharnier (schwenkt frei),
  M3-Dom (Schraube schneidet ein). Bei Bedarf `fit` und `hl_gap` im Customizer anpassen.
- Schmetterlingsschlüssel in Schrankfarbe; Türen in einer Kontrastfarbe wirken am besten.

## Grenzen

- Böden breiter als etwa 600 mm brauchen dickere Böden (`shelf_t`) oder eine
  Mittelwand (noch nicht modelliert).
- Türreihen werden an den Böden geteilt; sehr niedrige Türen bekommen nur ein Griffloch.
- Geplant: Mittelwände, Schubladen, Füße, ein 90°-Eckschrank.

Die Bilder in diesem Ordner sind Renderings der Modellgeometrie; die Raumszenen
sind fotorealistische Bilder, bei denen nur der Raum erzeugt wird, während das
Möbel aus dem Render des tatsächlichen Modells stammt.

## Downloads

Druckdateien gibt es bewusst ausschließlich auf MakerWorld.

👉 MakerWorld-Link: https://makerworld.com/en/models/3501978-parametric-modern-cabinet-system

Profil: <https://makerworld.com/en/@BetaHydri>

## Lizenz

Dokumentation und Bilder in diesem Repository: © BetaHydri. Das Modell
(einschließlich Quellcode) und alle Druckdateien werden ausschließlich über
MakerWorld unter der dort genannten Lizenz verbreitet. Dieses Repository enthält
bewusst kein Modell, keinen Quellcode und keine Druckdateien.
