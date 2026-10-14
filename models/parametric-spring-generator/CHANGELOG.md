# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-18

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht den Dateisystem-Zeitstempeln der Modelldatei, der Profile und der
Beschreibung (alle 18. August 2026).

### Added

- Vier Federtypen über `spring_type`: Serpentine (`serpentine`), Druckfeder
  (`compression`), Blattfeder (`leaf`) und Spiral-/Torsionsfeder (`spiral`).
- Serpentinenfeder mit runden oder eckigen Windungen (`ser_style`), einstellbarer
  Windungszahl, Drahtstärke, Tiefe und Breite, massiven Endkappen und
  Schwalbenschwanz-Zapfen (`ser_pegs`, `ser_peg_w`, `ser_peg_l`).
- Optionale Bohrung in den Zapfen (`ser_peg_hole`) als Tropfenloch, das
  waagerecht ohne Support rund druckt; bei Gewindewahl als Kernloch für
  selbstschneidende Schrauben.
- Montagehilfe (Jig) für die Serpentine (`ser_tool_grip`, Ausgaben
  `print_with_tool` und `tool_only`).
- Druckfeder als rechteckiges Bandprofil mit Fase (`coil_wire`, `coil_wire_h`,
  `coil_chamfer`), Vorgabe über Windungszahl oder Zielhöhe (`coil_turns`,
  `coil_len`) und Windungsabstand (`coil_gap`).
- Print-in-Place-Stützrippe für die stehend gedruckte Druckfeder (`coil_support`,
  `coil_clearance`) mit Abreißnadeln (`coil_support_tabs`).
- Endvarianten der Druckfeder: plan geschliffen (`flat`), offen (`open`) und
  Montageplatte unten (`plate`) mit offenem oder geschlossenem Deckel
  (`coil_top`), Plattenmaße über `coil_plate_t`, `coil_plate_d` und
  `coil_screw_len`.
- Blattfeder mit Bogenhöhe, Dicke und massiven Befestigungsaugen (`leaf_len`,
  `leaf_w`, `leaf_t`, `leaf_rise`, `leaf_hole`).
- Spiralfeder mit Nabe und Bohrung sowie drei äußeren Enden: Verankerungsring,
  Stiftlasche oder Haken (`spiral_outer`, `spiral_ring_wall`,
  `spiral_ring_holes`, `spiral_tab`).
- Gemeinsame Lochart für alle Befestigungen: glatt oder gedrucktes
  metrisches Gewinde M2–M6 (`hole_type`, `hole_screw`).
- Ausgabemodi `preview`, `print`, `print_multicolor`, `print_with_tool` und
  `tool_only`; Vorschaufarben für Feder, Stütze und Nadeln (`col_part`,
  `col_support`, `col_needle`).
- Zehn Referenzvarianten mit Bambu-Studio-Profilen für den P2S (PETG): zwei
  Serpentinen, eine Serpentine mit Gewindezapfen, drei Druckfedern, eine
  Blattfeder und drei Spiralfedern.
