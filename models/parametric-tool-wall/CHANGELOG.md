# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.1.0] - 2026-11-13

### Added

- 16 Halter-Typen statt fünf. Neu: V-Kerben für Zangen und Scheren beliebiger
  Dicke (`vee`), Stiftebecher (`cup`), gerade Stifte für Spulen und Rollen
  (`peg`) und Hammerhalter mit zwei Haken und einer Lücke für den Stiel
  (`hammer`); dazu Bohrmaschinen-Aufnahme, Bohrerständer, Rohrzangen-Halter,
  Schleifpapier-Tasche, Messschieber-Halter, Box mit offener Front und
  Arbeitstisch.
- Boden (Sacklöcher) für runde, Schlitz- und V-Kerben-Halter sowie 0,6 mm tief
  eingravierte Beschriftungen pro Loch; Pinzetten-Voreinstellung für die
  Schlitze (bis 8 Schlitze).
- Wechselbare 1×1-Behälter (21–70 mm hoch) mit Beschriftungsfläche oder
  eingraviertem Text sowie eine Kachelwand bis 60 × 60 Zellen in bettgroßen
  Feldern.
- Fünf neue druckfertige Kits (`pliers-vee-4x2`, `tweezers-floor-4x2`,
  `pen-cup-3x2`, `spool-peg-3x2`, `hammer-holder-4x2`), zusätzlich zu neun
  Erweiterungs-Kits für die älteren neuen Halter; jedes mit optionaler
  Wandplatte und Montageanleitung (DE/EN).
- Tipp für ein separates Filament für die Stützen-Kontaktschichten
  (z. B. PLA unter PETG) für leichteres Entfernen der Stützen.
- Neue Bilder: alle 16 Halter-Typen an einer Wand (Quer- und Hochformat) und
  Cover der neuen Kits.

### Changed

- Stützen: Die fertigen Projekte enthalten einen Stützblock (Stützentyp normal
  (manuell)) unter Abstandshalter und Lippe statt automatischer Stützen.
- Neue Halter (Stiftebecher, Stifte, Hammerhalter) sind ungetestete Drucke;
  für sie und die V-Kerben wird keine Tragfähigkeit angegeben.

## [1.0.0] - 2026-11-01

### Added

- Parametrische Werkzeugwand: French-Cleat-Wandplatte im 42-mm-Raster (1–7 Zellen
  breit, 1–7 Reihen hoch, eine 45°-Leiste pro Reihe; `plate_cols`, `plate_rows`,
  `plate_t`, Senkschrauben M3 / M4 / M5 über `screw`, eine pro Zelle) mit
  automatischem Fuß unter der untersten Leiste (11 mm, mit Haken 23 mm).
- Bis zu fünf einhängbare Module (`module_1` … `module_5`, Breite 1–4 Zellen):
  runde Löcher, Sechskant-Taschen (1–3 Reihen, bis 24 Taschen, wahlweise
  durchgehend), Schlitze für Zangen und Maulschlüssel (oder eigenes Maß),
  Ablage mit Gridfinity-Sockeln (42-mm-Raster) und Haken.
- Module hängen durch Eigengewicht an jeder Leiste, gleiten seitlich und werden
  durch etwa 10 mm Anheben abgenommen; ein Abstandshalter unten an der Rückwand
  verhindert das Vorkippen, auch in der untersten Reihe.
- Zweifarbiger Druck: Wandplatte in Farbe 1, Module in Farbe 2, jede Farbe auf
  eigenen Platten, kein Prime-Tower (`two_colors`, `color_plate`,
  `color_module`).
- Druckerauswahl über `printer` (P2S und andere 256-mm-Betten bis 5 Zellen, H2C
  bis 7 Zellen, A1 mini bis 4 Zellen).
- Wandplatte ohne Stützen druckbar; Module mit automatischen Stützen unter Lippe,
  Fase und Hakenspitzen (in den Profilen nur für die Module gesetzt).
- Vier Beispielvarianten (`screwdriver-rack-3x2`, `pliers-hexkeys-4x2`,
  `tray-bits-hooks-5x4`, `workshop-7x3-h2c`) mit testweise geslicten
  Bambu-Studio-Profilen für 3, 4 und 5 Wände.
- Belastbarkeitsabschätzung als Berechnung (Reibungsstatik und 2D-FEM, PETG-Werte
  aus der Literatur), ausdrücklich keine Messung.
- Automatische Prüfung an der echten Geometrie in 11 Konfigurationen
  (589 Prüfungen, 0 fehlgeschlagen) sowie 5 abgelehnte unmögliche Einstellungen.
