# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-05

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem); die ersten
Dateien und die Modellbeschreibung stammen vom 2026-07-03, die Profile und
Varianten vom 2026-08-04.

### Added

- Parametrische Deckelschale aus drei getrennten Körpern: Schale, Deckel und
  Knauf, jeweils in Druckrichtung ausgegeben (`part`: `bowl`, `lid`, `knob`).
- Schalenform über `bowl_height`, `base_diameter`, `top_diameter`,
  `belly_bulge` und `belly_position`, dazu `wall_thickness`,
  `floor_thickness` und die Bodenfase `bottom_chamfer`.
- Sechs Wandstrukturen über `wall_pattern`: `none`, `diamond_grid`,
  `hex_grid` (offen) sowie `diamond_relief`, `vertical_ribs`,
  `horizontal_ribs` (Vertiefungen); Steuerung über `grid_cell`, `grid_bar`,
  `relief_depth`, `rib_count` und `pattern_margin_bottom`.
- Reibsitz-Deckel mit `fit_play`, `skirt_depth`, `skirt_thickness` und
  Einführfase `skirt_tip_chamfer`; der Rand wird an der engsten Innenweite der
  Schale bemessen.
- Deckelform über `lid_thickness`, `lid_overhang` und `lid_dome_height`.
- Deckelmuster über `lid_pattern` (`none`, `concentric`, `radial`,
  `diamond_relief`), `lid_pattern_count` und `lid_relief_depth`.
- Knauf in vier Formen (`dome`, `sphere`, `teardrop`, `cylinder`) mit
  Größen `knob_diameter` und `knob_height`; wahlweise als Einklebe-Teil mit
  Zapfen (`knob_separate`, `peg_diameter`, `peg_clearance`,
  `peg_tip_chamfer`).
- Ausgabemodi `both` (auseinandergezogene Vorschau), `assembled` und
  `Multicolor Export` (alle Teile flach, drei Farbgruppen); die
  Vorschau-Modi tragen ein „NOT FOR PRINTING“-Banner und eine Start-Kamera,
  die alle Teile zeigt.
- Zehn Referenzvarianten in drei Größen (klein, Standard, groß) mit
  Bambu-Studio-Profilen für P1S mit PLA (3 Wände, Gyroid 15 %).
- Renderings der Wandstrukturen und Varianten.
