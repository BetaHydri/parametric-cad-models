# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-10-09

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem); die ersten
Dateien des Modells stammen vom 2026-10-02.

### Added

- Parametrischer Wandschirm als D-förmiger Halbturm mit gerundeter Front,
  eckiger Rückseite, geschlossenem Dach sowie offener Rückwand und Unterseite;
  Maße über `lamp_width`, `lamp_height`, `lamp_depth`, `wall_t` und
  `corner_radius`.
- Fensterfelder mit vier Stilen (`imperial`, `slots`, `grid`, `none`) für Front
  und Seitenwände, einstellbar über Kapselbreite, Abstände und Randzonen.
- Zahnrad-Emblem als massives Speichenrad (`top_emblem`, `side_emblem`,
  `emblem_diameter`, `emblem_bar`, `emblem_teeth`); die geschlossene Zone oben
  wächst mit dem Emblem.
- Verdeckte Schlüssellochaufhängung in einer Teil-Rückwand
  (`back_panel`, `back_panel_len`, `mount_screw_d`, `mount_head_d`).
- Einschiebbare LED-Halterplatte für drei Lichtquellen: E14-Schraubfassung,
  kleiner E14-Konverter und Bambu-LED-Kit-Puck (`led_mode`, `e14_*`, `puck_*`),
  mit Kabelkanal und Zugentlastung (`cable_d`, `cable_strain`).
- Loser Diffusor als dünne U-Schale zum Wechseln der Leuchtfarbe.
- Absatz für die Halterplatte mit 45°-Fase; der Schirm druckt mit dem Dach auf
  dem Bett ohne Stützen.
- Ausgabemodi `Preview assembled`, `Preview exploded`, `DRUCK Schirm`,
  `DRUCK LED-Halter` und `DRUCK Diffusor`; Vorschau mit
  „NOT FOR PRINTING“-Banner.
- Drei Varianten (`imperial-e14`, `imperial-sides-puck`, `slots-e14-small`) mit
  Bambu-Studio-Profilen für P1S mit PLA, jeweils mit Schirm, Halter und
  Diffusor.
