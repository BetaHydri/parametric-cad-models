# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-10-30

### Added

- Parametrischer selbstbewässernder Pflanztopf aus Reservoir, Einsatz und
  Peilstab; Voreinstellungen Kräutertopf 110 mm, Zimmerpflanze 140 mm und 180 mm,
  Pflanzgefäß XL 260 mm sowie freie Größe (`preset`, `custom_d`, `custom_h`,
  `taper`).
- Wasserreservoir mit Einfüllschacht und Peilstab (Rillenring = Maximalmarke),
  Überlaufloch auf der maximalen Füllhöhe und 8 mm Luftspalt zwischen
  Wasserstand und Einsatzboden (`water_h`, `fill_d`, `overflow`).
- Dochtlöcher im Einsatzboden für Baumwollschnüre (`wick_n`, `wick_d`).
- Drei Oberflächen: glatt, gerillt und facettiert (`style`, `flutes`,
  `flute_depth`, `sides`) sowie Wand- und Bodenstärke (`wall`, `floor_t`).
- Zweifarbiger Druck: Reservoir in Farbe 1, Einsatz und Peilstab in Farbe 2,
  jede Farbe auf eigenen Platten, kein Prime-Tower (`two_colors`, `color_pot`,
  `color_insert`).
- Druckerauswahl für 256-mm-Betten, H2C und A1 mini (`printer`); unmögliche
  Einstellungen werden mit einer roten Meldung statt eines Modells abgelehnt.
- Assemble-Ansicht mit Schnitt durch den Topf (`cutaway`).
- Vier Varianten (`herb-110-smooth`, `plant-140-fluted`, `plant-180-faceted`,
  `planter-260-xl`) mit test-geslicten Bambu-Studio-Profilen für 3, 4 und 5
  Wände.
- Automatische Prüfung an der echten Geometrie in 10 Konfigurationen:
  372 Prüfungen, 0 fehlgeschlagen (Überlappungen, Überlauf, Einfüllschacht,
  Wasservolumen, Wandstärke, Überhänge, Platten).

### Changed

- Die Profile behalten die zufälligen Nähte, wenn sie in Bambu Studio geöffnet
  werden.
