# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.2.0] - 2026-11-06

### Changed

- Zungen neu gebaut: flache Blattfeder mit rechteckiger Wurzel, die gerade in
  einen geraden Schlitz in der Falzwand geschoben wird (die runden Köpfe passten
  nicht durch den engen Hals und drehten sich nur, ohne zu federn). 1,5 mm
  Federweg, etwa 1,6 N pro Zunge. Die Zahl der Zungen richtet sich nach dem
  Gewicht des Stapels.
- Lange Leisten liegen diagonal auf dem Bett (bis etwa das 1,4-Fache der
  Bettlänge), sodass der Rahmen weniger Teile braucht: 135 x 240 mm hat 4 statt 6
  Leisten, A4 hat 6 statt 8.
- Die 45°-Fase unter der Lippe läuft bis zur Falzwand (kein flacher Absatz mehr).
- Prüfskript: 25 Konfigurationen plus 6 ungültige Einstellungen, 1508
  Prüfungen; Zunge, Leistenzahl und Leistenplatten werden an den echten Netzen
  gemessen.

### Added

- Test-Ecke mit drei Schlüsselpassungen (`key fit` -0,05 / ±0 / +0,05), standardmäßig
  aus; Schalter `diag strips` für die diagonalen Leisten.

## [1.1.0] - 2026-11-06

### Changed

- Neue Verbindung: Die runden Zapfen sind weg. Ein flacher Snap-Schlüssel (zwei
  geschlitzte Ringköpfe mit einer 45°-Raste an einem Steg) wird von hinten in
  eine Tasche in jeder Leiste gedrückt; die Raste klickt in eine Nut am
  Taschengrund. Der Schlüssel wird liegend gedruckt, die Schichten laufen in
  Zugrichtung. Klammer, Federklammer und Schmetterlingsverbinder entfallen.
- Die Lippe, die das Bild hält, hat unten eine 45°-Fase (nur ein 0,5 mm breites
  Band berührt das Glas); der Rahmen wird dafür um etwa Lippe + 1 mm tiefer. Das
  Spiel um das Bild ist auf 0,5 mm begrenzt.
- Zungenfenster, die in ein Schlüsselloch der oberen Leiste laufen würden,
  entfallen.
- Prüfskript: strenge Prüfung auf flache Absätze, auf freistehende Inseln und
  auf die Lippenfase; 951 Prüfungen in 22 Konfigurationen.

### Added

- Test-Ecke (zwei kurze Leistenstücke und ein Schlüssel) als erste Platte jedes
  Downloads, dazu die Einstellung `key fit` für den Sitz des Schlüssels.

### Fixed

- Beim ersten echten Druck sind fast alle runden Zapfen abgebrochen (freistehende
  Säulen, nur über das überbrückte Dach der Tasche mit der Leiste verbunden), und
  die flache vordere Lippe brauchte Stützen. Beides ist behoben.

## [1.0.0] - 2026-11-05

### Added

- Parametrischer Bilderrahmen aus Gehrungsleisten für Rechtecke (Standardgrößen
  9 x 13 cm bis A3 oder frei bis 600 mm), regelmäßige Vielecke mit 3 bis 12
  Seiten und Rauten (Winkel 30 bis 85°); jede Ecke bekommt ihren eigenen
  Gehrungswinkel.
- Fünf Profile: flach, Fase, halbrund, Stufen (Kassette) und Hohlkehle; Breite
  20 bis 70 mm, Tiefe 14 bis 50 mm, Lippe 2 bis 10 mm.
- Verbindungen ohne Kleber auf der Rückseite: Klammer mit Reibschluss auf zwei
  Zapfen (zieht die Gehrung durch 0,3 mm Zapfenabstand zu), konischer
  Schmetterlingsverbinder und Federklammer.
- Automatische Teilung langer Seiten (Länge über Bettbreite minus 14 mm) mit
  Klammern an den Stoßstellen, damit A4- und Posterrahmen auf ein 256-mm-Bett
  passen.
- Flexible Zungen, die Glas, Foto und Rückwand in Fenstern der Falzwand halten;
  optionale gedruckte Rückplatte und zwei Schlüssellöcher.
- Narrensichere Eingaben: eine rote Meldung ersetzt das Modell, wenn der Rahmen
  zu schmal oder zu flach ist, eine Leiste breiter als das Bett wird oder die
  Öffnung zu klein ist.
- Mehrplatten-Export für den MakerWorld-Customizer mit Wahl der Bettgröße;
  Ansichten für den fertigen Rahmen, die Rückseite und die Explosionsansicht.
- Sechs Beispielrahmen (13 x 18 Fase, 10 x 15 flach mit Schmetterlingsverbinder,
  A4-Kassette, Sechseck, Raute, Achteck) als 3MF für den Bambu Lab P2S in PETG.
- Prüfskript mit 386 Prüfungen in 12 Konfigurationen und 5 bewusst falschen
  Einstellungen an der echten exportierten Geometrie.
