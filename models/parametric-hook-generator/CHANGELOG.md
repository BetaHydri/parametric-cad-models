# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-11-04

### Added

- Parametrischer Klemm- und Einhänge-Haken ohne Werkzeug: Befestigung oben als
  runder Stab, U-Klammer über Kanten (Brett, Tür, Regal) oder Heizkörperrippe
  (`mount_preset`, `mount_type`, `bar_d`, `slot_w`, `tongue_len`, `tongue_t`,
  `slot_r_in`, `slot_r_out`, `mount_tip_angle`, `fit_clear`, `handle_gap`).
- Hakenseite unten als runde oder eckige Mulde mit eigenen Radien, Öffnungswinkel
  und Spitzenwulst (`hook_type`, `hook_d`, `hook_w`, `hook_h`, `hook_r_in`,
  `hook_r_out`, `hook_tip_angle`, `hook_lip`, `hook_side`).
- Festigkeitsabschätzung nach Balkenformeln (Sicherheitsfaktor etwa 5) für Hakenbogen,
  Befestigungsbogen, Stiel und Klammerschenkel (`material`, `load_kg`). Bei zu
  hoher Last zeigt die Vorschau eine rote Warnung mit Last, geschätztem Maximum und
  schwächstem Teil; der Export wird blockiert.
- Narrensichere Eingaben: Wand mindestens 3 mm, sichere Radien, ausreichend
  breite Hakenöffnung, PLA am Heizkörper abgelehnt, Druckbett-Prüfung.
- Freitext auf dem Stiel, erhaben oder als bündiges Inlay in zweiter Farbe,
  automatisch skaliert: auf der Vorderwand, der Rückwand, beiden Wänden oder der
  Seitenfläche (Druckseite, Bettseite oder beide; Bettseite immer bündig)
  (`text_mode`, `text_face`, `text_side`, `text_dir`).
- Vorschau mit grauem Modell des gegriffenen Objekts und aufrechter Ansicht der
  Textwand; vier Beispielvarianten (Türgriff, Brett, Heizkörper, eckiger Haken)
  mit Zweifarb-3MF für den Bambu Lab P2S in PETG.
- Prüfskript mit 84 Fällen (benannte Fälle, abgelehnte Fälle, Zufallssätze,
  Textrichtung, Auswahllisten-Prüfung) an der echten exportierten Geometrie.

### Fixed

- Auswahllisten im Customizer: Einträge enthalten keine Kommas mehr, weil der
  Customizer Listen an Kommas trennt (Leserichtung und Seitenfläche).
- Kein Spalt zwischen Stiel und Mulden mehr; Radien übersteigen nie die
  Wandstärke; gespiegelte runde Mulde kollidiert nicht mehr mit dem Stiel.
