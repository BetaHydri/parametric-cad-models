# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-31

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem); die ersten
Dateien des Modells stammen vom 2026-07-07.

### Added

- Parametrische Schale mit Schräge: Gesamtmaße `outer_width`, `outer_depth`,
  Höhen `front_height` und `back_height`, Eckenrundung `corner_r`, Wand- und
  Bodenstärke `wall_t` und `floor_t`.
- Fachaufteilung über Verhältniswerte (`col1_ratio` bis `col3_ratio`,
  `row_bottom_ratio`, `row_top_ratio`); fünf Fächer oder sechs mit
  `split_top_right`.
- Herausnehmbare Einsätze mit einstellbarer Passung (`insert_clearance`),
  Wand- und Bodenstärke, Höhenanteil und Abstand unter dem Schalenrand.
- Sieben Einsatztypen pro Fach: offene Box, Stift-Löcher, zwei Fächer, drei
  Fächer, 2×2-Raster, drei Schlitze und Kombi.
- Stifthalter-Einsatz mit automatischer, hexagonal versetzter Lochverteilung
  und wahlweise drei Lochdurchmessern nach Tiefenzone.
- Rippenstruktur an der Außenwand mit drei Profilen (rechteckig, V-förmig,
  gerundet) über `relief_enabled`, `relief_style`, `relief_count`,
  `relief_depth`, `relief_width` und `relief_corner`.
- Ausgabemodi über `part_mode`: Zusammenbau-Vorschau, Schale und Einsatz 1 bis 6;
  Vorschau mit eingesetzten oder auseinandergezogenen Einsätzen.
- Vorschau-Farben für Schale und Einsätze (`shell_color`, `insert_color`).
- Vier Referenzvarianten (Standard, geteiltes hinteres Fach, kompakt, breit)
  mit Bambu-Studio-Profilen für P1S mit PLA.
