# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-29

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem); die ersten
Modelldateien stammen vom 2026-06-10.

### Added

- Parametrisches Gefäß, rund (`round`) oder rechteckig (`rect`) mit
  einstellbarem Eckenradius `corner_r`.
- Maße über `diameter`, `width`, `depth` und `height` (bis 320 mm), Wand
  `wall` und Boden `floor_t` mit Mindestwert 2 mm.
- Steckdeckel mit Reibschluss: `fit_clearance`, `skirt_depth` und
  Einführfase `skirt_chamfer`.
- Fase an der Unterkante (`bottom_chamfer`) gegen Elefantenfuß.
- Rillenstruktur mit drei Profilen (rechteckig, V-Rille, gerundet) über
  `relief_enabled`, `relief_style`, `relief_count`, `relief_depth`,
  `relief_width` und `relief_corner`.
- Ausgabemodi `Preview 2-color`, `Preview open`, `both`, `Multicolor Export`,
  `body` und `lid`; Vorschau-Modi mit „NOT FOR PRINTING“-Banner.
- Beschriftung auf der Deckeloberseite und der Gefäßwand (Größe, Tiefe,
  Seite bzw. Winkel, vertikale Position, glatter Freiraum um den Text),
  wahlweise als Vertiefung oder als bündige Farbeinlage im Mehrfarbdruck.
- Fünf Varianten (`v1_rund_hoch`, `v2_rund_rillen`, `v3_eckig_vrille`,
  `v4_rund_feinerillen`, `v5_eckig_rund`) mit Bambu-Studio-Profilen für P1S
  mit PLA.
