# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-21

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht den frühesten Dokumenten, Renderbildern und der Modelldatei
(Dateisystem).

### Added

- Parametrische Taschen-Box für Hundeleckerli (Standard 90 × 60 × 20 mm) mit
  Print-in-Place-Knuckle-Scharnier hinter der Rückwand, flach und ohne Stützen
  druckbar.
- Übergreifender Klappdeckel (`lid_rim`, `rim_height`), der Front und Seiten der
  Box außen umgreift.
- Schnapper aus Nut und Feder an der Außenseite der Front (`latch_style`,
  `latch_count`, `latch_grip`); innenliegender Schnapper als Rückfall bei
  `lid_rim` = `Off`.
- Hinterer Füllkeil und 45°-Fase an der Rückwand für den Deckelschluss.
- Namen auf dem Deckel (`top_text`, Größe automatisch oder manuell,
  Versatz) und Freitext an der Front (`front_text`).
- Deckel-Motive `Paw`, `Bone`, `Dots`, `Ribs`, `Diagonal` (`lid_decor`,
  `decor_size`, `mark_depth`); Text und Motiv werden auf die Fläche begrenzt und
  überlappen sich nicht.
- Optionale Fächer mit Print-in-Place-Trennwänden (`cells_x`, `cells_y`,
  `div_wall`, `fillet`).
- Vorschau-Modi (zu, offen, zweifarbig) mit „NOT FOR PRINTING“-Banner sowie die
  Druckmodi `Print flat (1 color)` und `Print flat (2 color)`.
- Parameter `printer` mit Konsolenwarnung, wenn das flache Layout nicht auf den
  Bauraum passt, und `hinge_gap` für das Scharnier-Spiel.
- Vier Varianten (`treats_paw_en`, `leckerli_bone_de`, `snacks_dots_en`,
  `gassi_diag_de`) mit Bambu-Studio-Profilen für P1S und PLA mit 3 Wänden.

### Changed

- Der Schnapper wurde von der Innenseite an die Außenseite der Front verlegt, damit
  Fächer unberührt bleiben.

### Fixed

- Nichts.

### Removed

- Nichts.
