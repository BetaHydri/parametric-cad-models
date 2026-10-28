# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.1.0] - 2026-10-28

### Added

- Klebefreie Schwalbenschwanz-Halterung: zwei 45°-Schienen im Schirm greifen
  über die angefasten Längskanten der Halterplatte; leicht konisch, damit sich
  die Platte hinten leicht ansetzen lässt und beim Einschieben klemmt
  (`dovetail`, `flush_bracket`, `dt_bevel`, `dt_bevel_lo`, `dt_clear`,
  `dt_taper`, `dt_rail_tip`, `dt_front_stop`).
- Zweifarbiger Druck: Der Diffusor hat eine eigene Farbe auf einer eigenen
  Platte (`two_colors`, `color_shell`, `color_diffuser`), gedacht für
  transluzentes PETG in Rot, Blau oder Grün. Jede Platte hat nur eine Farbe,
  damit kein Prime-Tower entsteht.
- MakerWorld-Platten: eine Platte für Schirm und Halterung, eine für den
  Diffusor (bei sehr breiten Lampen automatisch mehr) sowie eine
  Zusammenbauansicht; `part` steht standardmäßig auf `none`.
- Prüfskripte für den Zusammenbau (Diffusor von unten einschieben, Halterung von
  hinten einschieben) und für die Platten (Bettgrenzen, eine Farbe je Platte).

### Changed

- Die Halterplatte schließt bündig mit der Unterkante des Schirms ab; der
  Absatz und der 5 mm zurückgesetzte Hals entfallen, der Diffusor sitzt
  entsprechend tiefer (233 statt 228 mm hoch).
- Die drei Beispielvarianten sind zweifarbige Zwei-Platten-Profile für den P1S.
- Der Schirm hat im Schienenbereich keinen Überhang über 45° mehr; insgesamt
  sank die Fläche steiler Überhänge am Schirm von etwa 1790 auf 1110 mm².
- Der Schirm außen bleibt unverändert; alle Änderungen liegen innerhalb der
  Innenwand.

### Removed

- Der Absatz mit 45°-Fase für die Halterplatte (ersetzt durch die Schienen).

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
