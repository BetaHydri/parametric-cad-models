# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-10-24

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum ist der
Tag der Veröffentlichung dieser Dokumentation.

### Added

- Parametrisches Regalsystem für schmale Nischen mit 1 bis 4 Schalen,
  Eckpfosten, Rückwandplatten mit Wandschrauben und optionaler
  Schlauchabdeckung.
- Gerade und schräge Nischen über getrennte Breiten `niche_w_back` und
  `niche_w_front`; Schalen, Ränder, Pfosten und Wandwinkel folgen der Wand.
- Fünf Befestigungsarten über `mounting`: Pfosten und Füße mit Rückwandschrauben
  (Standard), mit Wandwinkeln, nur Pfosten und Füße, nur Wandwinkel, nur
  Rückwandschrauben.
- Gedruckte, höhenverstellbare Schraubfüße mit Trapezgewinde (Ø 18 mm,
  Steigung 3,5 mm), alternativ M8-Stellfüße oder keine Füße.
- Vorderrand massiv oder als Wabengitter.
- Verbindungen über selbstschneidende Löcher oder Gewindeeinsätze mit
  Gewindestiften; Schraubenkopf Senkkopf oder Innensechskant, M2 bis M5.
- Schlauchabdeckung als eingeschobenes „L“ mit Wandarmen, Lüftungsschlitzen und
  Rippen.
- Wandabstand `wall_gap` mit gedruckten Abstandshülsen für unebene Wände.
- Lastabschätzung für Wandwinkel (`design_load_kg`, `dyn_factor`).
- Passungstest-Platte (`Fit test footprint`).
- Ausgabemodi `Preview assembled` und `Preview exploded` mit „NOT FOR
  PRINTING“-Schild; Vorschau blickt von der Nischenöffnung in die Nische.
- Eingabeprüfungen mit Klartext-Meldung (Schalenabstand, Schalenbreite, Rand,
  Schraubenlöcher) und Konsolenausgabe mit Höhenreserve, Pfostenlängen und
  Einkaufsliste.
- Zwei fertige Sets für den Bambu Lab H2C (ASA): Set A „Schraubfüße“ und
  Set B „Flach + Wabenfront“, je ein 3MF mit vier Platten.
