# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-11-04

### Added

- Parametrische Hundemarke in drei Formen: rund, Pfote und Knochen
  (`shape`, `tag_d`, `paw_w`, `bone_l`, `bone_w`, `bone_hole`); Pfote und Knochen
  sind standardmäßig größer, damit die Schrift Platz behält.
- Name bündig in zweiter Farbe auf der Vorderseite (`name`, `name_depth`).
- Rückseite wahlweise mit bis zu drei Zeilen erhabener Adresse oder mit dem Namen
  als bündiges Inlay auf beiden Seiten (`back_side`, `line1` bis `line3`).
- Automatische Schriftanpassung: Schriftgröße und Position werden so gewählt, dass
  der Rand zu Kante und Aufhängeloch immer bleibt (`text_margin`, mindestens Fase
  + 1 mm).
- Aufhängeloch mit garantierter Wand zum Rand (`hole_d`, `hole_tol`, `hole_wall`);
  bei Pfote und Knochen sitzt es in einer Öse.
- Vereinfachtes Menü: Preview, Multi colour, Single colour.
- Prüfskript mit 106 Fällen (benannte Fälle und Zufallssätze) an der echten
  exportierten Geometrie; Beispiel-Varianten REX und LUNA mit Zweifarb-3MF.

### Fixed

- Löcher (Hohlräume) in der Pfote und falsche Schnitthöhe beim Knochen.
- Einfarbige Variante: erhabene Schrift ist jetzt 0,02 mm in den Körper
  eingebettet und damit mit dem Körper verbunden.
