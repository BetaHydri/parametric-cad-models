# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-11

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht den frühesten Dokumenten und Bildern des Modells (Dateisystem).

### Added

- Parametrisches Print-in-place-Knuckle-Scharnier aus zwei Flügeln und einem
  durchgehenden Pin, flach und stützenfrei druckbar.
- Festigkeits-Presets `simple`, `standard`, `heavy` und `custom` mit eigenen
  Werten für Pin, Barrel-Wand, Plattenstärke und Knuckle-Anzahl.
- Parameter `hinge_gap` und `axial_gap` zur Abstimmung des Spiels auf den
  Drucker.
- Drucker-Parameter `printer`, der die maximale Scharnierlänge auf den Bauraum
  begrenzt.
- Frei definierbares Montagebild: Lochraster, optionale Senkung (oben/unten)
  und Langlöcher (quer/längs zur Achse).
- Zweifarbige Vorschau-Modi (gefaltet und flach) mit „NOT FOR PRINTING“-Banner
  sowie Druckmodi `print`, `print_2color`, `leaf_left` und `leaf_right`.
- Eingebaute Prüfungen für Barrel-Wand, Plattenstärke, Knuckle-Länge und
  Plattenbreite.
- Fünf Varianten (`simple_40mm`, `standard_60mm`, `heavy_80mm`,
  `standard_slots_60mm`, `test_coupon_30mm`) mit Bambu-Studio-Profilen für
  P2S und PETG in je 2, 3 und 4 Wänden.
- Fit-Prüfung über Mindestabstand und Schnittvolumen der beiden Flügel.
- Materialempfehlungen für Scharniere (PETG, PA, PP, ABS/ASA, TPU, PC, PLA).
