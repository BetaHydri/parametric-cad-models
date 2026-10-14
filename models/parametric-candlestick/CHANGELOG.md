# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-03

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem); die ersten
Dateien des Modells stammen vom 2026-07-21.

### Added

- Parametrischer Kerzenständer als massiver Rotationskörper (ein geschlossenes
  Polyhedron) mit den Maßen `total_height`, `foot_diameter`, `waist_diameter`
  und `top_diameter`.
- Sieben Grundformen über `shape_preset` (`Saeule`, `Kelch`, `Baluster`,
  `Sanduhr`, `Konisch`, `Vase`, `Frei`) mit `waist_position`, `belly_bulge`
  und `belly_position` für den freien Modus.
- Sieben Oberflächenstile über `deco_style` (`Glatt`, `Riefen`, `Spiralriefen`,
  `Wellen`, `Perlen`, `Kordel`, `Facetten`) mit `deco_amp`, `deco_count`,
  `deco_twist` und `bead_rows`; die Verzierung läuft an Boden und Kopf aus.
- Bodenfase `bottom_chamfer` gegen Elefantenfuß.
- Kerzenaufnahme als senkrechtes Sackloch mit Einführfase; Kerzentypen
  (Stabkerze 22 mm, Haushaltskerze 20 mm, Spitzkerze 13 mm, Teelicht 38 mm,
  Stumpen 50 mm und 68 mm) oder freier Durchmesser, Passung
  `socket_clearance` und Tiefe `socket_depth`.
- Optionen für Dorn (`use_spike`, `spike_*`), Tropfmulde (`drip_tray`,
  `drip_*`) und mehrarmigen Leuchter (`socket_count`, `socket_ring_radius`).
- Konsolenwarnungen bei zu flacher oder zu tiefer Bohrung, zu dünner Wand und zu
  schmaler Standfläche.
- Vorschau mit Kerze und Flamme (`part = Vorschau`) und druckfertiger Export
  (`part = DRUCK Kerzenstaender`).
- Acht Varianten (`d1_kelch_riefen` bis `d8_saeule_glatt`) mit
  Bambu-Studio-Profilen für P1S mit PLA.

### Fixed

- Flächenreihenfolge des Polyhedrons liefert Normalen nach außen; die schnelle
  Vorschau ist damit nicht mehr durchsichtig.
- Der Convexity-Wert wächst mit `deco_count` und Verdrehung, damit tiefe Riefen
  in der Vorschau korrekt dargestellt werden.
