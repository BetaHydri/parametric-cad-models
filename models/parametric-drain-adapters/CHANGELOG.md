# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-11-05

### Added

- Parametrischer Abflussadapter mit den Formen gerade (Reduzierstück,
  Erweiterung, Verlängerung mit zusätzlichem Rohr bis 300 mm), Bogen (5 bis
  120°), T- / Y-Stück (Abzweig 30 bis 90°) sowie Kappe und Stopfen.
- Für jedes Ende (A, B, bei T- / Y-Stücken C) wahlweise Schlauchtülle (Größe =
  Innendurchmesser des Schlauchs) oder Muffe (Größe = Außendurchmesser des
  Rohrs) in 20 bis 130 mm, mit Auswahlliste der üblichen Größen.
- Muffe mit konischer Bohrung, Rohranschlag und O-Ring-Nut (3-mm-Schnur);
  Dichtung wahlweise O-Ring, gedruckte TPU-Ringe auf einer zweiten Platte oder
  keine.
- Tülle mit 2 bis 6 Rippen, einstellbare Wandstärke (2 bis 6 mm) und
  Bogenradius; das größere der Enden A und B steht automatisch auf dem Bett.
- Platz für jeden Schlauch an T- und Y-Stücken; aufrechter Druck ohne Stützen
  bis 35°, darüber gemalte Stützstreifen in den 3MF.
- Narrensichere Eingaben: eine rote Meldung ersetzt das Modell bei unzulässigen
  Größen, zu großen Teilen für das gewählte Druckbett oder sich berührenden
  Enden eines Bogens.
- Schnittansicht zur Prüfung von Wand und Bohrung sowie Wahl der Bettgröße im
  Customizer.
- Zehn Beispielteile (Wohnmobil-Auslass, Reduzierstück, Verlängerung, Schlauch
  auf Kanalrohr DN100, 90°- und 45°-Bogen, Y- und T-Stück, Kappe, Stopfen) als
  3MF für den Bambu Lab P2S in ASA.
- Prüfskript mit 705 Prüfungen in 28 Konfigurationen an der echten
  exportierten Geometrie.
