# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.1.0] - 2026-10-25

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum ist der
Tag der Veröffentlichung dieser Dokumentation.

### Added

- Set D „Drei Schalen, gestaffelte Tiefe, Wandwinkel“: wie Set C, dazu gedruckte
  Wandwinkel unter jeder Schale (Customizer-Datei 2), Nische 160 × 228 × 400 mm.
  Ein 3MF für den Bambu Lab P2S (ASA) mit fünf Platten (drei Schalen, Pfosten
  und Füße, Wandwinkel) plus Passprobe. Set C liegt jetzt ebenfalls als P2S-3MF
  vor; jede Platte passt auch auf das Bett des P1S.

- Set C „Drei Schalen, gestaffelte Tiefe“: Nische 160 × 223 × 400 mm, Schalen
  220 / 180 / 120 mm tief, gedruckte Pfosten und kurze Füße. Ein 3MF für den
  Bambu Lab H2C (ASA) mit einer eigenen Bauplatte je Teilegruppe, dazu eine
  Passprobe. Schalen dürfen jetzt bis 100 mm flach sein (vorher 150 mm).
- Sechs Customizer-Dateien statt einer Gesamtdatei: je eine pro Befestigungsart
  (`1-posts-backwall-screws`, `2-posts-wall-brackets`, `3-freestanding-posts`,
  `4-brackets-no-posts`, `5-backwall-no-posts`) und eine eigenständige
  Schlauchabdeckung (`6-hose-cover`). Jede Datei zeigt nur die für sie
  relevanten Parameter; die Geometrie ist mit der früheren Gesamtdatei
  identisch.
- Lastabschätzung für die Befestigung nur an den Rückwandschrauben (Datei 5):
  Auszugskraft je Schraube und maximale Schalentiefe (bei 2 kg, Faktor 4 und
  2 Schrauben etwa 181 mm, mit 4 Schrauben etwa 365 mm).
- Rote Meldung in der Vorschau, wenn eine Einstellung nicht möglich ist, statt
  eines leeren Modells („Current top level object is empty“ auf MakerWorld).

### Changed

- Wandwinkel passen sich schmalen und schrägen Schalen an: dünner (bis etwa
  22 mm, höhere Rippe), dann weniger Winkel, unter flachen Schalen kürzere
  Arme. Die Wandarme der Schlauchabdeckung werden in schmalen Nischen ebenfalls
  schmaler.
- Die Schalen-Dateien kennen den Schlauch nicht; für die Kombination mit der
  Abdeckung gelten Höhengrenzen für die oberste Schale (Standard-Nische
  ≤ 187 / 213 / 229 mm je nach Befestigung).

### Fixed
- Gewinde der gedruckten Schraubfüße: Die Zähne waren nur etwa 0,2 mm dick und konnten nicht gedruckt oder gedreht werden. Jetzt echtes Trapezgewinde (60° Flanken, Steigung 3,5 mm, Zahn 1,0–2,2 mm, 0,25 mm Spiel); Dateien 1 bis 3 und Set A, C und D sind neu gebaut.

- Wandwinkel in schrägen Nischen konnten neben die Schale oder in die
  Nischenwand ragen, weil sie nur nach der Breite an der Rückwand platziert
  wurden. Sie liegen jetzt über ihre ganze Länge unter der Schale.

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
