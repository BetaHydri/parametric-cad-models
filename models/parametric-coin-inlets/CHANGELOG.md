# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-09-01

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht den Projektnotizen und der letzten Änderung der Modelldatei
(Dateisystem).

### Added

- Parametrischer Münzsortierer aus Gefäß, Deckel und herausnehmbarem
  Münzeinsatz in einer OpenSCAD-Datei.
- Gefäßtypen: rund mit Reibdeckel, rund als Schraubglas (BOSL2-Gewinde),
  rechteckig mit Reibdeckel.
- Automatische Dimensionierung des Gefäßes aus der Münzauswahl
  (`sizing_mode = auto`) und manueller Modus mit Warnung, wenn die Münzen nicht
  passen.
- Euro- und US-Münzen mit hinterlegten Maßen; Fächerzahl je Nennwert von 0 bis
  24 (`n_2eur` bis `n_1cent`, `n_dollar` bis `n_penny`).
- Füllmodus `slot_fill` für rechteckige Raster, damit kein Fach leer bleibt.
- Höhenmodi `manual` (`tray_height`) und `auto` (`stack_coins`, bezogen auf die
  dickste gewählte Münze).
- Kompakte Ring-Anordnung mit variablem Abstand (`tight_pack`) für runde
  Einsätze, rechteckiges Raster mit reserviertem Zentrum.
- Abgesenkter Mittelgriff (`grip_r`, `grip_bar_w`, `grip_sink`, `grip_web`) und
  Daumenaussparung je Fach (`thumb_slot`, `notch_facing`).
- Spardosen-Deckel mit Münzschlitz (`lid_slot`, `slot_len`, `slot_width`).
- Musterbibliothek (Rillen, Rippen, Ringe, Diagonale, Karo, Noppen, Facetten)
  sowie Wand- und Deckeltext für runde Gefäße.
- Explodierte Vorschau mit "NOT FOR PRINTING"-Banner und Mehrfarbexport mit je
  einer Farbe für Gefäß, Einsatz und Deckel (`col_body`, `col_tray`,
  `col_lid`).
- Druckprofile für Bambu Lab P1S (PLA, 3 Wände, Gyroid 15 %) für sieben
  Beispielvarianten.

### Changed

- Der Einsatz füllt das Gefäß bis auf `tray_fit` (Standard 0,15 mm je Seite);
  der Reibdeckel-Rand sitzt im Freiraum über dem Einsatz.
- Die Zähler je Nennwert ersetzen die früheren Ein-/Aus-Schalter je Münze.
- Der Fachring wurde kompakter: Einsatzdurchmesser beim Euro-Vollsatz von
  114,5 auf 100,7 mm; Standardwerte `well_gap` 1,0 mm und `rim_wall` 1,2 mm.

### Fixed

- Rechteckige Form mit Schraubglas-Auswahl erzeugt jetzt automatisch den
  Reibdeckel, damit die Teile zusammenpassen.
- Der Einsatz liegt flach auf, weil seine Unterkante den Innenradius am
  Gefäßboden (`inner_fillet`) freihält.
