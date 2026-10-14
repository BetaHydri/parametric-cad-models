# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei dokumentiert.

Das Format basiert auf [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- Dieses Repository enthält nur Dokumentation und Bilder. Modell- und Druckdateien werden
  ausschließlich über MakerWorld verteilt.

## [1.0.0] - 2026-10-13

Hinweis: Die Versionsnummer ist eine Festlegung für die Erstveröffentlichung auf MakerWorld; das Datum
ist der Veröffentlichungstag.

### Added

- Rundes Schraubglas auf Gridfinity-Fuß (42-mm-Raster, Fußprofil 0,8 / 1,8 / 2,15 mm) mit Grundfläche
  1×1 bis 4×4 Zellen (`grid_size`) und Höhe in Gridfinity-Einheiten (`height_units`); geschlossene Höhe
  Einheiten × 7 mm, Spalt zwischen Bins über `base_gap`.
- Grobes Trapezgewinde mit 45°-Flanken ohne Überhang (`thread_style`, `thread_depth`, `thread_pitch`,
  `thread_turns`, `thread_slop`, `lid_tolerance`) sowie das ISO-60°-Gewinde als Option.
- Kappe mit Wand, Deckfläche, Randabstand, Schulterrand und Fase (`cap_wall`, `cap_top`, `cap_margin`,
  `lip_height`, `lip_round`, `cap_chamfer`).
- Griffrillen an der Kappe (`grip_style`, `grip_pitch`, `grip_depth`).
- Optionaler Kappentext (`lid_text_enabled`, `lid_text`, `lid_text_size`, `lid_text_depth`).
- Optionale Magnettaschen, vier pro Zelle, unten offen: Einkleben 6,5 × 2,4 mm oder Einpressen
  5,9 × 2,0 mm (`magnets`).
- Grundplatten-Passprobe mit 1–5 Zellen je Seite (`baseplate_cells`, `baseplate_floor`, `baseplate_rim`,
  `baseplate_clearance`).
- Teileauswahl mit Vorschau (Kappe auf, Kappe daneben), Glas und Kappe, Zweifarb-Export, nur Glas,
  nur Kappe und Passprobe.
- Fünf Referenzvarianten (`v1_1x1_screws_49mm` bis `v5_baseplate_2x2_test`) mit Druckprofilen auf
  MakerWorld.
