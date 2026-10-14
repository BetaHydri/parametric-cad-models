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
Vorschau- und Prüfskripte stammen vom 2026-08-18, die Profile, Renderings und
die Beschreibung vom 2026-08-19.

### Added

- Parametrische Box, rund (`round`) oder rechteckig (`rect`) mit
  einstellbarem Eckenradius `corner_r`.
- Maße über `diameter`, `width`, `depth` und `height` (bis 320 mm), Wand
  `wall` und Boden `floor_t` mit Mindestwert 1,6 mm.
- Überstülp-Deckel, der von außen über die Box greift: `lid_overlap`,
  `lid_wall`, `lid_top`, Spiel `fit_clearance` und Einführfase
  `lid_chamfer`.
- Fase an der Unterkante gegen Elefantenfuß.
- Selbsttragende Grifföffnungen mit 45°-Dach: `handle_enabled`, `handle_w`,
  `handle_side_h`, `handle_corner`, `handle_tip_r`, `handle_z`; bei runden
  Boxen `handle_count` und `handle_angle`, bei rechteckigen `handle_faces`
  (`LR`, `FB`, `ALL`).
- Rillenstruktur mit drei Profilen (rechteckig, V-Rille, gerundet) über
  `relief_enabled`, `relief_style`, `relief_count`, `relief_depth`,
  `relief_width` und `relief_corner`; die Rillen enden unterhalb des
  Deckelbereichs.
- Beschriftung auf der Deckeloberseite und der Boxwand (Größe, Tiefe, Seite
  bzw. Winkel, vertikale Position, glattes Feld um den Text), wahlweise als
  Vertiefung oder als bündige Farbeinlage im Mehrfarbdruck.
- Ausgabemodi `Preview assembled`, `Preview open`, `both`,
  `Multicolor Export`, `body` und `lid`; Vorschau-Modi mit „NOT FOR
  PRINTING“-Banner und Start-Kamera, die beide Teile zeigt.
- Vier Referenzvarianten (`rect_lidded`, `rect_handles`, `round_relief`,
  `rect_text`) mit Bambu-Studio-Profilen für P1S mit PLA (3 Wände, Gyroid
  15 %), Box auf Platte 1 und Deckel auf Platte 2.
