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
Dateien stammen vom 2026-08-05.

### Added

- Parametrischer Napfständer nach dem Vorbild eines vermessenen
  Fusion-360-Entwurfs: Deckplatte mit gespreizten Beinen
  (`leg_splay` Standard 30°, entspricht 120° Innenwinkel), Fußlänge
  `foot_length` und Rundung `edge_round`.
- Plattenmaße `board_length` (oder automatisch über `auto_board_length`),
  `board_width`, `board_thick` und Gesamthöhe `total_height`.
- Ein oder zwei Napfmulden (`bowl_count`) mit 45°-Wand, abgerundetem Rand
  (`bowl_rim_round`), abgerundeter Bodenkante (`bowl_fillet`) und flachem Boden
  ohne Mittelzapfen; Durchmesser `bowl_diameter`, Tiefe `bowl_depth`,
  Wandwinkel `bowl_wall_angle` und Abstand `bowl_spacing`.
- Zweiter Muldendurchmesser `bowl2_diameter` für einen großen Futternapf neben
  einem kleinen Wassernapf (0 = gleich wie die erste Mulde).
- Schwalbenschwanz-Teilung (`dovetail_depth`, `dovetail_neck`, `dovetail_tip`,
  `dovetail_play`) mit 45°-Einführfase an der hinteren Zungenseite und
  bündiger Vorderseite.
- Druckerwahl `printer` (P1S/P2S, H2C, H2D) und `split_mode` (`auto`, `always`,
  `never`); die Teilung erfolgt automatisch, wenn der Ständer nicht aufs
  Druckbett passt.
- Druckausrichtung auf der Stirnseite, stützfrei.
- Prüfung der Trennnaht gegen die Napfmulden mit Klartext-Meldung und
  Lösungsvorschlägen sowie weitere Eingabeprüfungen (Plattendicke, Muldentiefe,
  Beinüberlappung, Napfplatz).
- Ausgabemodi `assembled preview`, `split preview`, `assembled clean`,
  `both halves`, `right half` und `left half`; Vorschau-Modi mit
  „NOT FOR PRINTING“-Banner.
- Acht Varianten (Katze, kleiner, mittlerer und großer Hund, je mit einem oder
  zwei Näpfen) mit Bambu-Studio-Profilen in den Wandstärken 2, 3 und 4
  (P1S und H2C, Bambu PLA Basic, 0,20 mm, Gyroid 15 %).
