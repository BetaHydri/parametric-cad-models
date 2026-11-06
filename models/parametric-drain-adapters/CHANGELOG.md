# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.1.0] - 2026-11-06

### Added

- Zoll- und DIN-Größen in der Auswahlliste: Zollschläuche 1/4" bis 2" und
  Stahlrohre nach DIN 2440 / ISO 65 (1/4" bis 4", DN8 bis DN100) sowie weitere
  metrische Größen; eigener Wert ab 5 mm. Muffen beginnen bei 10 mm.
- Schläuche unter 20 mm bekommen automatisch einen niedrigeren Wulst und eine
  dünnere Wand, damit die Bohrung offen bleibt (1/4"-Tülle: 4 mm Bohrung).
- Steilerer Trichter (38° statt 15°) bei Reduzierungen über 2,5 : 1, zum
  Beispiel 50 mm auf 1/4" in einem Teil (etwa 100 mm statt 165 mm hoch); mit
  einem Bogen beliebigen Winkels kombinierbar.
- Drei neue Beispielteile: Schlauchverbinder 1/4 Zoll, Wohnmobil-Ablauf 50 mm
  auf 1/4-Zoll-Schlauch und 45°-Bogen Muffe 50 mm auf 1/4-Zoll-Schlauch.
- Größen-Prüflauf über jede Größe der Auswahlliste (184 Konfigurationen, 4554
  Prüfungen).

### Changed

- Die Kollisionsprüfung beim Bogen rechnet gegen die echte Kontur von Ende A;
  Bögen mit stark unterschiedlichen Größen werden dadurch nicht mehr unnötig
  abgelehnt.
- Prüfskript: 46 Konfigurationen mit 1124 Prüfungen und strengere Prüfung auf
  flache Absätze.

### Fixed

- O-Ring-Nut: Das waagerechte 2-mm-Dach der Nut hing beim Druck frei in der
  Luft (Fäden in der Bohrung, Meldung "floating regions" im Slicer). Beide
  Flanken der Nut haben jetzt 45°, der gedruckte TPU-Ring folgt dem Profil.
- Schlauchanschlag der Tüllen: flache Stufe durch eine 45°-Fase ersetzt.
- Alle Beispiel-3MFs und Bilder neu erzeugt und im Bambu Studio testgeslict.

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
