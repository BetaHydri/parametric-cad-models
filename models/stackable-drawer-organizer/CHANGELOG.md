# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- Dieses Repository enthält nur noch Dokumentation und Bilder. Modell- und
  Druckdateien werden ausschließlich über MakerWorld verteilt.

## [1.0.0] - 2026-08-21

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem); die ersten
Renderings stammen vom 2026-07-07, die P1S-Druckprofile vom 2026-08-04.

### Added

- Parametrisches, stapelbares Schubladensystem mit 1 bis 6 Ebenen
  (`drawer_count`), je ein rundum geschlossenes Gehäuse mit offener Front und
  eine Schublade.
- Freie Außenmaße (`unit_width`, `unit_depth`, `corner_r`) und einzeln
  einstellbare Schubladenhöhen (`h1` bis `h6`) oder eine einheitliche Höhe
  (`uniform_height`, `drawer_clear_h`).
- Umkehrbare Gleitschiene (`rail_mode`) mit Nut- und Rippentiefe als Anteil der
  Wandstärke (`rail_wall_frac`), einstellbarem Gleitspiel (`rail_clear`) und
  Einschubanschlag (`rail_backstop`).
- Weiche Rastnase gegen Herausfallen (`pull_stop`, `pull_stop_h`).
- 45°-Stapelfuß mit passender Tasche (`stack_lip`, `lip_h`, `lip_wall`,
  `lip_clear`, `stack_gap`).
- Dekorative Front mit Griffmulde und fünf Relief-Mustern (Diamonds, vertikale
  Rippen, horizontale Rippen, Dots, Crosshatch).
- Herausnehmbare Fächer-Einsätze mit zehn Layouts (`ins1` bis `ins6`),
  darunter vier asymmetrische Layouts mit einem großen und zwei geteilten
  Fächern (`insert_split_frac`).
- Ausgabemodi für Turm-Vorschau, Einzelteile, Druckplatte, alle Teile flach und
  einen mehrfarbigen Export mit eigener Farbgruppe je Schublade.
- Sicherheitsprüfungen (`assert`), die extreme Einstellungen melden, bei denen
  die Schublade nicht bündig schließen würde.
- Zwei Varianten mit Bambu-Studio-Profilen für den P1S mit PLA: `standard`
  (120 × 150 mm) und `schmal` (90 × 130 mm).
