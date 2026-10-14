# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.2.0] - 2026-08-04

Hinweis: Versionsnummern sind in den Quellen nicht belegt und wurden nachträglich
vergeben. Die Daten stammen aus dem Dateisystem.

### Added

- Bambu-Studio-Profile für P2S mit Bambu PETG Basic (0,4-mm-Düse, 0,20 mm
  Schichthöhe, 1 Wand, Gyroid 0 %, Dünnwand-Erkennung an) für die Varianten
  Rund 80 mm und Rund 100 mm, jeweils mit Test-Slice.

## [1.1.0] - 2026-08-02

### Added

- Optionale Verbindungs-Clips für zwei Gitterstücke (`output_mode`: `clip`,
  `both`) mit dem Clip-Stil `comb` („liegender Kamm“): flach in der Gitterebene,
  Mittelsteg als Anschlag, Finger über beiden Gitterkanten, stützenfrei
  druckbar.
- Parameter für den Kamm (`comb_floor_t`, `comb_lip_t`, `comb_slot_clear`,
  `comb_chan_depth`, `comb_spine_w`, `comb_finger_w`, `comb_finger_gap`,
  Längenrasterung, Fingerfase, optionale Bodennoppen).
- Demo-Modus (`output_mode = demo`) mit zwei Gitterstücken, Clip-Reihe und
  Explosionsdarstellung (`demo_explode`).
- Prüfmodus (`output_mode = verify`) mit Clip und Gitterstücken im gemeinsamen
  Koordinatensystem für eine OpenCascade-Prüfung von Interferenz, Spiel und
  Druckbarkeit.

### Changed

- Standard-Clip-Stil ist `comb`. Die älteren Stile `tiny_snap` und
  `side_slide` bleiben in der Datei erhalten, sind aber für flache, koplanare
  Gitter geometrisch ungeeignet (Schlitz nach Gitterdicke, unten offen).

## [1.0.0] - 2026-06-10

Hinweis: Das Datum entspricht den frühesten Dateien des Modells (Dateisystem).

### Added

- Parametrisches Fliegengitter als Einzelstrang-Gitter, düsengetrieben
  (0,2 / 0,4 / 0,6 mm): Strandbreite = Düse + 0,05 mm, Schichthöhe 0,10 / 0,20 /
  0,28 mm.
- Form rund oder quadratisch, freie Größe von 20 bis 300 mm und Presets
  (80 mm und 100 mm rund, 100 mm und 200 mm quadratisch, Full Bed 256 mm und
  300 mm).
- Einstellbare Maschenweite (0,8–5,0 mm) und Dicke (2–6 Schichten).
- Schneller Aufbau über ein 2D-Raster und einen einzigen `linear_extrude`.
- Slicer-Hinweise in der Konsole (Schichthöhe, Anfangsschichthöhe, 1 Wand,
  0 % Infill, Dünnwand-Erkennung).
