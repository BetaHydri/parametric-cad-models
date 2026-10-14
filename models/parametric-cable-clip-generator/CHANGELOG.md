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

- Generator für Einrast-Kabelclips mit 1 bis 10 Kanälen (`cable_count`), jeder Kanal mit eigenem
  Kabeldurchmesser von 2 bis 30 mm (`cable_d` bis `cable_d10`), Spiel `cable_clear` und Schlitzanteil
  `slot_ratio`.
- Kanäle in Tropfenform mit selbsttragendem 45°-Dach, ohne Stützen druckbar.
- Plattenclip mit drei Befestigungen (`fixing`): Klebeband, Senkschrauben (`screw_d`, `screw_margin`)
  und Magnettaschen 6 × 2 mm (`magnet_d`, `magnet_h`); Plattendicke und Flansch wachsen bei Schrauben
  und Magneten automatisch mit (`plate_t`, `flange`, `plate_extra`).
- Tischkanten-Klemme für Platten von 8 bis 60 mm Dicke (`desk_t`, `jaw_len`, `jaw_t`) mit Haltenoppen
  (`grip_bump`).
- Körperparameter `clip_length` und `wall` (Vielfache von 0,4 mm) und Render-Glätte `round_res`.
- Teileauswahl: Clip (Druck) und Vorschau mit Kabeln (nur Ansicht).
- Sechs Referenzkonfigurationen (`v1_adhesive_x2_6mm` bis `v6_screw_x10_4mm`).
- Die Durchmesser der Kanäle 5 bis 10 stehen in der Customizer-Gruppe „More Cables“.
- Die Magnetanzahl richtet sich nach der Breite des Kanalstapels (1 bis 4 Taschen).
