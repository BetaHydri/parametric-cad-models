# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.1.0] - 2026-08-15

Hinweis: Versionsnummern sind in den Quellen nicht belegt. Die Aufteilung in
1.0.0 und 1.1.0 folgt den Dateidaten des Modells (14.08.2026 und 15.08.2026).

### Added

- Schraubmontage für das Axiallager-Kit (`kit_mount = screw`): zwei gedruckte
  Stopfen mit Zunge-und-Nut-Kopplung und eine zentrale Schraube, Oberseite
  bündig.
- Parameter `kit_screw` für die Schraubengröße (`M2.5` oder `M3`) und
  Konsolenausgabe der Stückliste samt Schraubenlänge.
- Einzelteile `kit_plug_bottom` und `kit_plug_top` für die Stopfen.

### Changed

- Rollenlager mit größeren, massiven Führungsflanschen, dünnen Ringwänden,
  Spulenrollen und einem Käfig, der die Rollen umschließt.

### Removed

- Der gedruckte Print-in-Place-Axiallager-Typ mit schwebender Deckscheibe und
  gedruckten Kugeln; das Axiallager gibt es nur noch als Kit mit Stahlkugeln.

## [1.0.0] - 2026-08-14

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht den frühesten Dokumenten und Bildern des Modells (Dateisystem).

### Added

- Parametrischer Print-in-Place-Lagergenerator mit vier Typen: Rillenlager
  (`ball`), Zylinderrollenlager (`roller`), Axiallager-Kit (`thrust`) und
  Zahnradlager (`gear`).
- Rillenlager als verrastete Ringe ohne lose Kugeln, nachgebaut und vermessen
  an druckbaren Referenz-Lagern.
- 35 Rillenlager-Normgrößen (`685` bis `6304`) und 8
  Zylinderrollenlager-Größen (`NU202` bis `NU2205`) mit Grenzmaßen nach
  DIN 625-1, DIN 5412-1 und DIN 616 / ISO 15.
- Toleranzklassen `tight`, `default` und `loose` (0,25 / 0,30 / 0,35 mm).
- Zahnradlager mit Pfeilverzahnung, automatischer Zähnezahlwahl und fünf
  Größen-Presets (Außen-Ø 40 bis 80 mm).
- Axiallager-Kit mit Snap-Kragen, Kugelkäfig mit Entlastungsschlitzen und
  Testkugeln (`kit_balls`).
- Düsenabhängige Mindestmaße (`nozzle`) und `assert`-Prüfungen für nicht
  druckbare Kombinationen.
- Zweifarb-Ausgabe `print_2color` und Vorschau des montierten Kits.
- Fit-Prüfung über Mindestabstand und Schnittvolumen aller beweglichen Paare.
- Release-Varianten (Rillenlager 608, 609, 6000, 6001, 6002, 6004, 6902,
  Rollenlager 22 mm, Axiallager-Kit mit 6-mm-Kugeln, Zahnradlager) mit
  Bambu-Studio-Profilen für P2S und PETG.
