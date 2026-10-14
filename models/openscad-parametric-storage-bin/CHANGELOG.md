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

### Removed

- Modell-, Quellcode- und Druckdateien sowie die Anleitung zur lokalen Nutzung
  aus dem Repository entfernt.

## [1.0.0] - 2026-06-04

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem und
Commit-Historie); die ersten Commits stammen vom 2026-05-31. Die sechs
Referenzvarianten und ihre Druckprofile sind vom 2026-08-05.

### Added

- Parametrischer, vorne offener Behälter mit niedriger Frontwand und
  diagonaler Schrägfase an den Seitenwänden (`front_height`, `chamfer_len`).
- Freie Außenmaße über `width`, `depth` und `height`, Wand `wall` und Boden
  `floor_t`.
- Druckerpresets `P1S`, `P2S`, `H2C`, `H2D` und `Custom`; die Maße werden auf
  das Bauvolumen begrenzt.
- Optionaler Stapelrand: Lippe aus der inneren Wandhälfte und passende
  Aussparung in der Bodenunterseite ohne Verlust an Innenraum (`stackable`,
  `stack_lip_h`, `stack_clearance`).
- Optionale senkrechte Rillen an den Außenwänden mit drei Profilen
  (rechteckig, V-Rille, gerundet), symmetrischer Verteilung pro Wand und
  Eckenabstand (`relief_enabled`, `relief_style`, `relief_count`,
  `relief_depth`, `relief_width`, `relief_corner`, `relief_walls`).
- Fase an der Unterkante gegen Elefantenfuß (`bottom_chamfer`).
- Sechs Referenzvarianten (`b1_standard` bis `b6_klein_rillen`) mit
  Bambu-Studio-Profilen für den P2S mit PETG.

### Changed

- Stapelrand mehrfach überarbeitet: Die Lippe ist rein rechteckig, die
  Aussparung nur so lang wie die Lippe; in der Fasenzone wird die innere
  Wandhälfte abgeflacht.
- Bei aktivem Stapelrand wird die Wandstärke auf mindestens 3,0 mm angehoben;
  das Modell schreibt dazu einen Hinweis in die Konsole.
- Vorschaubilder neu gerendert (Rillen sichtbar, Stapelansicht).
