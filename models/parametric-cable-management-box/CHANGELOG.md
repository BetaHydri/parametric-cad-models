# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-10-29

### Added

- Parametrische Box für Steckdosenleisten mit Steckern: Basis, Deckel, Kabelgates
  und Schmetterlings-Keys; lange Boxen teilen sich automatisch in Segmente, die
  auf das gewählte Bett passen (P2S und andere 256-mm-Betten 248 mm, H2C 296 mm,
  A1 mini 172 mm; Parameter `printer`).
- Kabelgates mit 1–5 Einrast-Schlitzen (`cable_d`, `gate_slots`, `slot_ratio`),
  von oben einzudrücken, die Stecker bleiben an den Kabeln.
- Zweifarbiger Druck: Basis und Keys in Farbe 1, Deckel und Gates in Farbe 2,
  jede Farbe auf eigenen Platten, kein Prime-Tower (`two_colors`, `color_body`,
  `color_accent`).
- Belüfteter Deckel, Fingerkerben, Querrippen unter der Leiste und optionale
  Schlüssellöcher für Wand- oder Tischmontage.
- Rautenförmiger doppelter Schwalbenschwanz-Sitz für die Gates: sperrt Zug nach
  außen und Druck nach innen; das Gate lässt sich nach oben herausheben.
- Reibungsrippen an der Deckellippe (`lid_grip`, Standard 0,15 mm): der Deckel
  hält ohne Rastung.
- Schäftungsfalz an den Deckelstößen: bündig, ohne Stützen druckbar.
- Drei Varianten (`strip-150-compact`, `strip-300-p2s`, `strip-450-h2c`) mit
  test-geslicten Bambu-Studio-Profilen für 3, 4 und 5 Wände.
- Automatische Prüfung an der echten Geometrie in 8 Konfigurationen:
  Kollisionen, Gate-Sitz in beide Richtungen, Reibungsübermaß, Deckelstöße,
  Segmentsumme, Platten und Überhänge.

### Changed

- Die Aussage, der Deckel halte die Basis zusammen, wurde präzisiert: Die Lippe
  hält die Basis-Segmente seitlich fluchtend, nimmt aber keine Zugkräfte auf.
