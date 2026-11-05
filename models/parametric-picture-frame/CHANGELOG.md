# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

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
