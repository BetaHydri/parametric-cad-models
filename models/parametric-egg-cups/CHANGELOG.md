# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-06

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldateien und Bilder (Dateisystem);
die Entwicklung begann am 2026-08-05.

### Added

- Parametrischer Eierbecher in drei Körperformen: `tumbler` (Fass),
  `pedestal` (klassisch) und `wineglass` (Pokal).
- Eigröße-Presets `S`, `M`, `L`, `XL` sowie `custom` mit
  `egg_diameter_custom` und `egg_length_custom`.
- Gerundetes Cradle als Viertelellipse, einstellbar über `cradle_inset`,
  `cradle_depth_frac` und `rim_extra`.
- Reliefbibliothek mit 13 Strukturen: Flutes erhaben/genutet, Rippen, Ringe
  erhaben/genutet, Diagonale 45° erhaben/genutet, Kreuzschraffur, Spirale,
  Chevron, Noppenraster und Facetten, dazu glatt.
- Oberflächen-Schale für Reliefs mit konstanter Tiefe auf der gewölbten Wand.
- Auslaufende Textur über `fade_top` und `fade_bottom` (Standard je 9 mm).
- Texturband über `margin_bottom` und `margin_top`.
- Ausgabemodi `preview`, `preview_2color`, `print`, `print_2color`, `set_2`
  und `set_4`; zweifarbige Textur als eigene Farbgruppe.
- Prüfungen per `assert` für Eigröße, Cradle, Bodenstärke, Randwand,
  Reliefzone, Reliefdurchbruch sowie Pedestal- und Weinglas-Maße.
- Bambu-Studio-Profile für P1S mit PLA: acht Showcase-Varianten
  (`tumbler_flutes`, `tumbler_diagonal`, `tumbler_dimples`, `tumbler_facets`,
  `pedestal_rings`, `pedestal_flutes`, `wineglass_ribs`, `wineglass_smooth`)
  sowie drei Band-Varianten (`tumbler_flutes_band`, `tumbler_diagonal_band`,
  `tumbler_rings_band`).

### Changed

- Cradle-Profil von linear (spitzer Boden) auf Viertelellipse umgestellt.
- Zweifarb-Akzent bei vertieften Reliefs sitzt vertieft in der Nut, damit die
  Vorschau nicht mehr flimmert (Z-Fighting).
- Auslaufende Textur ist standardmäßig aktiv.
