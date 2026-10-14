# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-12

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem); die erste
Fassung und die Prüfskripte stammen vom 2026-07-30, die sechs
Referenzvarianten mit Profilen vom 2026-08-04.

### Added

- Parametrische Hutschienen-Montageplatte mit zwei Klemmwänden, die auf
  genormte DIN-Schienen (DIN EN 60715) klipsen.
- Schienenauswahl über `rail_norm`: `TH35_7.5`, `TH35_15`, `TH15` und
  `CUSTOM` (mit `custom_rail_width` und `custom_rail_depth`).
- Zwei Klemm-Modi über `clip_mode`: `snap` (Federclip mit Federhals und
  optionalem Lösehebel) und `slide` (starr).
- Einstellbare Klemmgeometrie: `wall_thickness`, `spring_wall_thickness`,
  `wall_fillet`, `hook_catch`, `hook_height`, `fit_clearance`,
  `neck_thickness`, `release_lever` und `lever_height`.
- Grundplatte über `plate_width`, `plate_length`, `plate_thickness` und
  `corner_radius`; die Breite wächst automatisch mit der Schiene.
- Montagemuster über `mount_pattern` (`none`, `grid`, `slots`, `grid_slots`)
  mit exakter Anzahl (`hole_cols`, `hole_rows`, `slot_count`),
  Lochdurchmesser, Randabstand und Kabelbinder-Schlitzen.
- Senkung für Löcher und Langlöcher mit wählbarer Seite
  (`countersink`, `countersink_side`).
- Parameter `printer`, `fit_length_to_bed` und `bed_margin`, die die
  Plattenlänge auf den Bauraum begrenzen.
- Seitliche Befestigung mit `side_features`, `side_pattern`, `side_cols`,
  `side_rows` und `side_long_dir`; die Platte verbreitert sich automatisch.
- `assert`-Prüfungen mit Klartext-Meldungen und Konsolen-Ausgaben zu
  Schiene, Plattenmaß, Bauraum-Limit und Lochanzahl.
- Vorschau der Hutschiene (`show_din_rail`), die nicht exportiert wird.
- Zehn Referenzvarianten (`TH35x7.5_snap`, `TH35x15_snap`, `TH15_snap`,
  `TH35x7.5_slide`, `TH35x7.5_snap_slots`, `TH35x15_slide`, `side_grid`,
  `side_slots_y`, `side_slots_x`, `side_cabletie`) mit Bambu-Studio-Profilen
  für P2S mit PETG-CF (3 Wände, Gyroid 15 %).
- Automatische Prüfung der Varianten auf Wasserdichtheit und genau einen
  Körper.
