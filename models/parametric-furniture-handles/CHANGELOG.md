# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-17

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht dem Neubau des Beispielvarianten-Satzes am 17. August 2026; das
Projekt begann am 16. August 2026 (Notizen und Dateisystem).

### Added

- Parametrischer Möbelgriff-Generator mit sechs Bauformen: `bar_handle`,
  `bow_handle`, `bar_pull`, `t_bar`, `knob` und `edge_pull`.
- Schraubaufnahmen für M2 bis M8 mit eingebauter Maßtabelle: gedrucktes
  metrisches Gewinde, selbstschneidende Kunststoffschraube, Sechskant- und
  Vierkantmutter, Heat-Set-Einsatz und Durchgangsloch.
- Zehn Lochabstände als Voreinstellung (16 bis 320 mm) und
  `hole_center_custom` für eigene Werte.
- Drei Griffquerschnitte (`round`, `rounded`, `rect`).
- Zweifarbige Clip-Abdeckung für Bügelgriff, Rundgriff und T-Griff.
- Oberflächenrelief `flutes`, `knurl`, `rings` und `facets` mit den
  Rillenprofilen `rounded`, `rect` und `vgroove`.
- Knopf-Formen `dome`, `cylinder`, `faceted` und `square`.
- `edge_relief` für den Kantengriff (`diagonal`, `crosshatch`).
- Optionale getrennte Schraubpfosten (`post_mode = separate`) mit
  Zapfen und Durchgangsbolzen.
- Zehn Beispielvarianten mit Bambu-Studio-Profilen für P1S und PLA
  (Gyroid 30 %, 3 Wände), je mit Test-Slice.
- Schutzprüfungen in der Konsole: Schraubenaufnahme zu groß für den Fuß, Griff
  zu dünn für Pfosten-Sockel, Abdeckung für die Bauform nicht verfügbar.
- Konsolenhinweise zu Stützen, Brim und Druckorientierung je Bauform.

### Changed

- Die zweifarbige Abdeckung nutzt standardmäßig den bündigen Inlay-Sitz
  (`cover_style = inlay`) mit Schnapp-Nut. Die zuerst entwickelte aufschiebbare
  Kappe (`clip_over`) bleibt als Alternative erhalten.
- Die Schnapp-Nut folgt der Griffkontur als Offset-Ring statt als Keil mit
  festen Y-Koordinaten.
- `relief_margin` = 0 lässt die Struktur bis zur Kante laufen.

### Fixed

- Schraubbohrung am D-Griff brach seitlich aus dem Schenkel aus: Die Tiefe ist
  auf den geraden Schenkelabschnitt begrenzt, der Durchmesser wird geprüft.
- Das Relief durchstieß D-Griff, Knopf und Kantengriff; es ist auf gerade
  Griffe beschränkt.
- Geisterkörper an den Füßen des D-Griffs in der Vorschau (Schnitt per
  `intersection()`); die Füße werden stattdessen per Subtraktion
  abgeflacht.
- Montierte Renderings des Kantengriffs zeigten die Schraubenseite zum
  Betrachter; die Darstellung nutzt jetzt die zusammengebaute Pose.
