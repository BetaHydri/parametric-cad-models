# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei dokumentiert.

Das Format basiert auf [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- Dieses Repository enthält nur Dokumentation und Bilder. Modell- und Druckdateien werden
  ausschließlich über MakerWorld verteilt.

## [1.0.0] - 2026-10-14

Hinweis: Die Versionsnummer ist eine Festlegung für die Erstveröffentlichung auf MakerWorld. Das Datum ist der
Tag, an dem das Modell in der MakerWorld-Profilübersicht erstmals gelistet war.

### Added

- Steckbares Teilersystem für Schubladen: lange Teiler mit Schlitzen unten, Quer-Teiler mit Schlitzen oben,
  Schlitzbreite Teilerstärke plus Spiel (`div_t`, `slot_clear`).
- Freie Schubladenmaße von 40 bis 700 mm Breite und Tiefe und 15 bis 200 mm Höhe (`inner_w`, `inner_d`,
  `inner_h`).
- 1 bis 12 Spalten und Reihen (`cols`, `rows`), gleich groß oder mit einem doppelt breiten Fach
  (`col_layout`, `row_layout`).
- Puzzleverbindungen für lange Teiler (`max_piece`, `joint_clear`), Trennstellen mit Abstand zu den Schlitzen.
- Quetschrippen an den Teilerenden (`grip`), Spalt zur Schubladenwand (`fit_gap`), Teilerhöhe (`div_h`).
- Fingermulden an der Oberkante der Fächer (`finger_notch`, `notch_r`).
- Randschienen für Schubladen mit nur einer Teilerrichtung: zwei Randschienen oder eine Mittelschiene
  (`base_rail`, `rail_h`).
- Übernahme des Innenmaßes aus dem Stackable Parametric Drawer System (`drawer_source`, `sd_unit_width`,
  `sd_unit_depth`, `sd_shell_wall`, `sd_side_gap`, `sd_drawer_wall`, `sd_rail_backstop`, `sd_front_t`,
  `sd_inner_h`).
- Verteilung der Teile auf Druckplatten mit Plattennummer (`plate_no`, `plate_w`, `plate_d`, `plate_gap`)
  und Übersicht, die die Plattenzahl zeigt.
- Teileauswahl: PRINT, OVERVIEW, nur lange Teiler, nur Quer-Teiler und Vorschau in der Schublade.
- Fünf Referenzkonfigurationen (`v1_stackable_2x2` bis `v5_kitchen_300x400`, Letztere auf drei Platten).
