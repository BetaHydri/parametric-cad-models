# Parametric Picture Frames – Bilderrahmen in jeder Größe und Form, fünf Profile, Snap-Schlüssel ohne Kleber

[← Alle Modelle im Überblick](../../README.de.md)

🌐 [English](README.md) | **Deutsch**

Drucke einen Bilderrahmen **genau so groß und so geformt wie dein Bild**: ein
Foto, ein Poster, ein Sechseck, eine Raute. Der Rahmen besteht aus **Gehrungsleisten**,
die auf der Rückseite von kleinen gedruckten **Snap-Schlüsseln** zusammengehalten
werden: kein Kleber, von vorn nichts zu sehen, und du kannst den Rahmen wieder
auseinandernehmen. Glas, Foto und Rückwand halten **Federzungen**, die du
zum Bildwechsel herausziehst.

[![MakerWorld](https://img.shields.io/badge/MakerWorld-Modell-00AE42)](https://makerworld.com/en/models/3551154-parametric-picture-frame#profileId-4062778)
![OpenSCAD](https://img.shields.io/badge/OpenSCAD-parametric-yellow)
![Bambu Lab](https://img.shields.io/badge/Bambu%20Lab-P2S-green)
![Druckdateien](https://img.shields.io/badge/Druckdateien-nur%20MakerWorld-blue)

> **Das Modell mit allen Druckprofilen gibt es ausschließlich auf MakerWorld:**
> 👉 [MakerWorld-Link: https://makerworld.com/en/models/3551154-parametric-picture-frame](https://makerworld.com/en/models/3551154-parametric-picture-frame#profileId-4062778)
>
> ![Parametric Picture Frames: sechs Rahmen in verschiedenen Formen und Profilen](images/01_hero.jpg)

## Inhaltsverzeichnis

- [Highlights](#highlights)
- [Die Profile](#die-profile)
- [Die Verbindung](#die-verbindung)
- [Parametrische Optionen](#parametrische-optionen)
- [Beispiele](#beispiele)
- [Druckempfehlungen](#druckempfehlungen)
- [Montage](#montage)
- [Was geprüft wurde](#was-geprüft-wurde)
- [Downloads](#downloads)
- [Lizenz](#lizenz)

## Highlights

- **Such das Bild aus, bekomm den Rahmen.** Standardgrößen von 9 x 13 cm bis A3
  in der Auswahlliste oder jede beliebige Größe. Oder ein **regelmäßiges Vieleck
  mit 3 bis 12 Seiten** oder eine **Raute** mit beliebigem Winkel: jede Ecke
  bekommt automatisch ihren eigenen Gehrungswinkel.
- **Fünf Profile.** Flach, Fase, halbrund, Stufen (Kassette) und Hohlkehle.
  Breite 20 bis 70 mm, Tiefe 14 bis 50 mm, Lippe 2 bis 10 mm.
- **Verbindungen ohne Kleber.** Auf der Rückseite jeder Gehrung hat jede Leiste
  eine Tasche. Ein flacher **Snap-Schlüssel** (zwei geschlitzte Ringköpfe an
  einem Steg) wird von hinten in beide Taschen gedrückt: Eine kleine Raste an
  jedem Kopf **klickt in eine Nut** am Taschengrund. Der Schlüssel wird liegend
  gedruckt, die Schichten laufen also in Zugrichtung der Verbindung, und beim
  Druck steht nichts frei in der Luft. Von vorn ist nichts zu sehen, und ein
  dünner Schraubendreher in der runden Aussparung an der Verbindung hebelt den
  Schlüssel wieder heraus. Mit der Einstellung **Schlüsselsitz** passt du den
  Halt an deinen Drucker an.
- **So wenige Teile wie möglich.** Das Bild bestimmt das Innenmaß; die
  Außenlänge einer Leiste (Öffnung + 2 x Rahmenbreite) muss aufs Bett passen.
  Eine Leiste, die länger ist als das Bett, wird **diagonal** gedruckt (bis zum
  etwa 1,4-Fachen der Bettlänge, auf einem 256-mm-Bett etwa 320 mm), sodass ein
  **135 x 240 mm** großer Rahmen nur **4 Leisten** braucht statt 6. Die Leisten
  liegen nebeneinander quer zur Diagonale des Betts, die längsten in der Mitte,
  und kürzere Leisten füllen die freien Plätze daneben: Auf einem 256-mm-Bett
  passt der ganze Rahmen 135 x 240 mm auf **eine Platte** (plus eine für
  Schlüssel und Zungen). Nur noch
  längere Seiten werden geteilt, in gleich große Stücke mit Schlüsseln an den
  Stoßstellen: Ein **A4-Rahmen** passt auf ein 256-mm-Bett. Mit `diag strips`
  aus liegt jede Leiste gerade.
- **Glas, Foto, Rückwand.** Der Falz ist so tief wie dein Stapel (Glas 0 bis
  6 mm, Foto, Rückwand 1,5 bis 8 mm) plus Platz für die Zungen. Keine Rückwand?
  Drucke eine **Rückplatte** (wenn sie aufs Bett passt).
- **Bild jederzeit wechseln.** Die **flachen Federzungen** werden gerade (mit
  der Wurzel voran) in Schlitze in der Falzwand geschoben, ihr Arm drückt den
  Stapel nach vorn. Gerade herausziehen, Bild tauschen, wieder einschieben. Die
  Zahl der Zungen richtet sich nach dem Gewicht des Stapels.
- **Aufhängen.** Zwei **Schlüssellöcher** in der oberen Leiste (Rechtecke und
  Vielecke mit flacher Oberseite).
- **Druck ohne Stützen.** Jede Leiste liegt mit der Rückseite auf dem Bett. Die
  Lippe, die das Bild hält, hat unten eine **45°-Fase**, die bis zur Falzwand
  durchläuft: Sie berührt das Glas nur entlang der Bildkante, und nirgends gibt
  es einen flachen Absatz. Der Rahmen wird dafür tiefer: an der dünnsten Stelle
  etwa um die Lippenbreite minus 1 mm.
- **Narrensicher.** Wenn eine Einstellung nicht funktionieren kann (Rahmen zu
  schmal für die Schlüssel, zu flach für den Stapel, eine Leiste breiter als das
  Bett, eine zu kleine Öffnung), **ersetzt eine rote Meldung das Modell**: du
  kannst nie versehentlich ein kaputtes Teil herunterladen.

![Hero hochkant: Rahmen in vielen Formen auf einem Holztisch](images/02_hero-hochformat.jpg)

## Die Profile

| Profil | Aussehen | Gut für |
|---|---|---|
| Flat (flach) | rechteckige Leiste | moderne, schlanke Rahmen, Fotos 10 x 15 |
| Bevel (Fase) | fällt zum Bild hin ab | der klassische Fotorahmen |
| Half-round (halbrund) | gerundete Oberseite | weiche, freundliche Rahmen, Vielecke |
| Steps (Stufen) | Kassette mit zwei Stufen | Poster, Kunstdrucke, A4 |
| Cove (Hohlkehle) | hohle Rille | Rauten und breite Rahmen |

## Die Verbindung

| | Snap-Schlüssel |
|---|---|
| **So hält er** | zwei geschlitzte Ringköpfe mit einer kleinen Raste rasten in Nuten am Taschengrund ein; ein steifer Steg verbindet sie |
| **Druckposition** | der Schlüssel liegt flach: Schichten in Zugrichtung, keine Stützen, keine freistehenden Teile |
| **Sitz** | `key fit` 0 bis 0,15 mm: kleiner = fester. Die optionale Test-Ecke (im Customizer einschalten) druckt drei Passungen auf einmal und zeigt, wie der Schlüssel auf deinem Drucker sitzt |
| **Wieder lösen** | mit einem dünnen Schraubendreher in der runden Aussparung an der Verbindung herauswippen |
| **Reserve** | 2 zusätzliche Schlüssel werden mitgedruckt (mehr im Customizer) |

Wähle **Keine**, wenn du die Gehrungen lieber kleben möchtest.

![Die Snap-Schlüssel auf der Rückseite des Rahmens](images/09_rueckseite-schluessel.jpg)

![Schnitt durch den Rahmen: Die Lippe hat unten eine 45°-Fase](images/11_schnitt-lippe-fase.jpg)

## Parametrische Optionen

| Gruppe | Optionen |
|---|---|
| Bild und Umriss | Rechteck (Standardgrößen oder frei bis 600 mm), regelmäßiges Vieleck (3 bis 12 Seiten, Seite 20 bis 300 mm) oder Raute (Seite und Winkel 30 bis 85°) |
| Rahmenprofil | Profil, Rahmenbreite, Tiefe und Lippe (der Rahmen wird an der dünnsten Stelle etwa um die Lippenbreite minus 1 mm tiefer) |
| Bildstapel und Rückseite | Dicke von Glas, Foto und Rückwand, Spiel (0,2 bis 1 mm), eigene Rückwand oder gedruckte Rückplatte, Zungen an oder aus, Schlüssellöcher an oder aus |
| Verbindungen | Snap-Schlüssel oder keine; Schlüsseldicke, Schlüsselsitz, Anzahl Ersatzschlüssel, Test-Ecke (standardmäßig aus: fügt eine erste Platte mit drei Schlüsselpassungen hinzu) |
| Drucker und Farben | Lange Leisten diagonal (standardmäßig an), Bettgröße (wähle **denselben Drucker im MakerWorld-Bettmenü**), Rahmenfarbe und Schlüsselfarbe; das Ansichtsmenü zeigt den fertigen Rahmen, die Rückseite oder die Explosionsansicht |

Ein Customizer-Download besteht aus mehreren Platten: zuerst die Leisten, auf
der letzten Platte die Schlüssel und Zungen. Mit eingeschalteter `test corner`
ist die Test-Ecke die erste Platte.

![Explosionsansicht eines Achteck-Rahmens](images/10_explosionsansicht.jpg)

## Beispiele

Druckfertige Bambu-Profile (**PETG, P2S**, 0,20 mm, 3 Wände, 15 % Gyroid,
testgeslict) gibt es auf MakerWorld, alle Platten in einer 3MF: zuerst die
Leistenplatten, dann eine Platte mit Snap-Schlüsseln und Zungen.

| Beispiel | Bild | Profil | Verbindung | Teile | Zeit / Gewicht |
|---|---|---|---|---|---|
| ![Fotorahmen 13 x 18 cm](images/03_foto-13x18-fase.jpg) **Fotorahmen 13 x 18 cm** | 130 x 180 mm | Fase | Snap-Schlüssel | 4 Leisten, 6 Snap-Schlüssel, 8 Zungen | 4,5 h / 132 g (2 Platten) |
| ![Fotorahmen 10 x 15 cm](images/04_foto-10x15-flach.jpg) **Fotorahmen 10 x 15 cm, flaches Profil** | 100 x 150 mm | flach | Snap-Schlüssel | 4 Leisten, 6 Snap-Schlüssel, 5 Zungen | 3,2 h / 101 g (2 Platten) |
| ![A4-Posterrahmen](images/05_a4-kassette.jpg) **A4-Posterrahmen, geteilte Seiten** | 210 x 297 mm | Stufen (Kassette) | Snap-Schlüssel | 6 Leisten, 8 Snap-Schlüssel, 10 Zungen | 8,0 h / 255 g (3 Platten) |
| ![Sechseck-Rahmen](images/06_sechseck-halbrund.jpg) **Sechseck-Rahmen** | regelmäßiges 6-Eck, Seite 70 mm | halbrund | Snap-Schlüssel | 6 Leisten, 8 Snap-Schlüssel, 5 Zungen | 3,8 h / 104 g (2 Platten) |
| ![Rautenrahmen](images/07_raute-hohlkehle.jpg) **Rautenrahmen** | Raute, Seite 90 mm, Winkel 60° | Hohlkehle | Snap-Schlüssel | 4 Leisten, 6 Snap-Schlüssel, 8 Zungen | 4,6 h / 134 g (2 Platten) |
| ![Achteck-Rahmen](images/08_achteck-fase.jpg) **Achteck-Rahmen** | regelmäßiges 8-Eck, Seite 60 mm | Fase | Snap-Schlüssel | 8 Leisten, 10 Snap-Schlüssel, 7 Zungen | 4,0 h / 108 g (3 Platten) |

Jede andere Größe oder Form druckst du mit dem Customizer.

## Druckempfehlungen

| Einstellung | Empfehlung |
|---|---|
| Drucker | Bambu Lab P2S (die Beispiele), P1S und jeder Drucker mit 256-mm-Bett; wähle den Drucker im MakerWorld-Bettmenü |
| Filament | **PETG** für alles (ASA oder PLA gehen auch). Die **Schlüssel** sollten PETG sein (steif, sie müssen einrasten); die **Zungen** kannst du auch in **TPU 95A** drucken, das ist weicher |
| Schichthöhe / Wände | 0,20 mm, 3 Wände |
| Füllung | 15 % Gyroid |
| Stützen / Brim | keine (Stützen im Slicer aus lassen: die Lippe hat eine 45°-Fase) |
| Lage | Leisten liegen mit der Rückseite auf dem Bett, Schlüssel und Zungen liegen flach |
| Genauigkeit | Der Schlüssel rastet um wenige Zehntelmillimeter ein, der Sitz hängt also von deinem Drucker ab. Schalte `test corner` ein und drucke sie zuerst (drei Passungen auf einmal). Ist der Schlüssel schwer hineinzudrücken, erhöhe `key fit` um 0,05; fällt er heraus, senke es um 0,05 |

> **Status:** Die Geometrie ist an den echten exportierten Netzen geprüft, und
> jedes Beispiel ist in Bambu Studio testgeslict. **In dieser Version noch
> nicht gedruckt.** Die erste Version hatte runde Zapfen und Zungen mit rundem
> Kopf; beim ersten echten Druck sind die Zapfen abgebrochen, und die Zungen
> passten nicht in ihre Löcher und federten nicht, deshalb wurden Verbindung
> und Zungen **neu gebaut**. Eine **Test-Ecke** (drei Schlüsselpassungen) ist
> optional: Schalte `test corner` im Customizer (Verbindungen) ein, dann ist
> sie die erste Platte.

## Montage

1. Lege die Leisten als Ring mit der **Rückseite nach oben** auf den Tisch; die
   Gehrungen berühren sich.
2. Drücke von hinten in die zwei Taschen jeder Verbindung einen Snap-Schlüssel,
   bis die Rasten klicken und er bündig sitzt.
3. Drehe den Rahmen **mit der Vorderseite nach unten** auf eine weiche
   Unterlage und lege Glas, Foto und Rückwand ein.
4. Schiebe jede Zunge mit der Wurzel voran bis zum Anschlag in ihren Schlitz in
   der Falzwand: Der Arm liegt dann auf der Rückwand und drückt den Stapel nach
   vorn.
5. Häng ihn an eine Schraube: der Kopf geht durch den runden Teil des
   Schlüssellochs, dann schiebst du den Rahmen nach unten.

## Was geprüft wurde

Alle Prüfungen laufen an den **echten exportierten Netzen** (OpenSCAD,
Manifold) in 25 Konfigurationen (u. a. 135 x 240 mm auf drei Bettgrößen, mit und
ohne diagonale Leisten, ein schwerer Glasstapel 20 x 30 cm, schmale und breite
Lippe), dazu 6 bewusst falsche Einstellungen, die die rote Meldung zeigen
müssen: **1598 Prüfungen, 0 fehlgeschlagen**. Auch die Schnappschlüssel-Verbindung
wird am Mesh gemessen (Kopf, Wulst, Schlitz, Spiel jedes eingesetzten Schlüssels
in seiner Tasche an Mündung und Rille, Taschentiefe); wie fest sie unter Zug
hält, zeigt nur ein Druck, drucke deshalb zuerst die optionale Testecke.

- **Die Gehrungen schließen:** die Fläche aller Leisten über der Lippenfase
  entspricht dem äußeren Umriss minus Öffnung, und benachbarte Leisten
  überlappen nicht.
- **Falz:** entspricht dem Bild plus Spiel auf jeder Seite.
- **Jede Leiste** ist ein Körper, liegt flach auf dem Bett, passt aufs Bett und
  **druckt ohne Stützen**. Die Prüfung ist streng: Ein flacher Absatz, der mehr
  als etwa 0,7 mm freisteht, fällt durch (Brücken bis 10 mm sind in Ordnung).
- **Die Lippenfase** wird an den Schnitten gemessen: In jeder Höhe von der
  Wandkante bis zur Öffnung beginnt das Material genau dort, wo die 45°-Linie es
  sagt.
- **Keine freistehenden Inseln:** Jede Schicht jeder Leiste ist ein
  zusammenhängendes Gebiet.
- **Leisten:** Eine Leiste, die länger als das Bett ist, liegt diagonal (eine
  284-mm-Leiste braucht ein Feld von 201 x 201 mm), ein Rahmen 135 x 240 mm hat
  also 4 Leisten, die auf einem 256-mm-Bett alle auf einer Platte liegen (zwei
  284-mm-Leisten in der Mitte, zwei 179-mm-Leisten außen). Jede Leistenplatte wird gemessen: Alle Leisten darauf sind
  getrennt, liegen im Bett und berühren sich nicht.
- **Wände:** mindestens 2 mm um jede Tasche und jeden Schlitz.
- **Schlüssel und Zungen** sitzen in ihren Taschen und Schlitzen, ohne den
  Rahmen zu berühren (außer den Quetschzähnen der Zungen).
- **Snap-Schlüssel:** Der Kopf schließt sich um 0,25 mm, während die Raste durch
  die Taschenöffnung gedrückt wird; das dehnt das PETG um etwa **1,5 %** (2,2 %
  bei 0,1 mm zu strammem Drucker; Grenze 3 %). Die Raste greift auch, wenn der
  Drucker 0,1 mm zu locker druckt, und der Schlüssel druckt flach ohne Stützen.
- **Zunge:** am echten Netz gemessen: Die Wurzel gleitet gerade in ihren
  Schlitz (Arm und Pad berühren auf dem Weg nichts), die Zähne werden um
  0,02 mm² eingepresst (Presssitz), der gebogene Arm bleibt frei von der Wand,
  und die Padoberseite liegt entspannt 1,5 mm in der Rückwand, der Stapel biegt
  den Arm also um 1,5 mm. Das ergibt etwa **1,6 N pro Zunge** (Balkenmodell mit
  der gemessenen Auslenkung), Biegedehnung **1,1 %** (1,8 % beim Einlegen des
  Bildes). Alle Zungen zusammen drücken auf einen 13 x 18-cm-Stapel von etwa
  1,8 N Gewicht mit etwa 13 N. Ein schwerer Stapel bekommt mehr Zungen (zusammen
  mindestens das Doppelte seines Gewichts).
- **Alle Platten** liegen im Bett; jedes Beispiel ist testgeslict, und die 3MF
  lädt in Bambu Studio nur mit Bambu-Filament.

**Noch nicht geprüft:** wie fest der gedruckte Snap-Schlüssel wirklich hält, wie
sich Presssitz und Steifigkeit der gedruckten Zunge anfühlen (das hängt von
der Toleranz deines Druckers ab). Von dieser Version ist noch nichts gedruckt.

## Downloads

Druckdateien gibt es bewusst ausschließlich auf MakerWorld.

👉 MakerWorld-Link: https://makerworld.com/en/models/3551154-parametric-picture-frame#profileId-4062778

Profil: <https://makerworld.com/en/@BetaHydri>

## Lizenz

Dokumentation und Bilder in diesem Repository; Modell- und Druckdateien werden
ausschließlich über MakerWorld verteilt. Dokumentation und Bilder: © BetaHydri.
Das Modell (inkl. Quellcode) und alle Druckdateien stehen unter der auf
MakerWorld angegebenen Lizenz. Dieses Repository enthält bewusst keine Modell-,
Quellcode- oder Druckdateien.
