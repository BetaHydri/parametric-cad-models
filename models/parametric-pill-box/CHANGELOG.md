# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-10-11

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem) und der
MakerWorld-Update-Notiz „Oct 2026“; die ersten Modelldateien stammen vom
2026-07-31. Die Einträge darunter sind nach Datum aus Dateistempeln und
Entwicklungsnotizen zusammengefasst.

### Added

- Parametrische Pillendose mit `columns` (1–14 Tage je Streifen) und `rows`
  (1–6 Streifen); Fachgröße über `day_w`, `day_len`, `well_depth` und bis zu
  vier Unterfächer pro Tag (`subdiv`).
- Design A „Hinged lids“: Klappdeckel pro Tag mit Print-in-Place-Scharnier
  (Achse auf halber Höhe, Stift durchgehend, ungerade Segmentzahl,
  Versteifungssteg), flach und offen gedruckt, ohne Stützen; Scharnierspiel
  `hinge_gap`.
- Snap-Verschluss mit Nut und Feder (`latch_style`, `latch_grip`).
- Beschriftung außen (`label_style`, `label_lang`, `week_start`) und erhabene
  Innenschrift für Design A (`inner_emboss`, `inner_style`, `inner_height`,
  `inner_size`, `inner_tab_gap`) mit automatischer Verkleinerung langer Texte.
- Freitext (`front_text`, `front_text_size`) einmal graviert; Seitenwahl über
  `front_text_side` (Front, Rückseite, linke und rechte Stirnseite).
- Design B „Friction + collar stack“: lose Reibdeckel pro Tag (`lid_fit`,
  `lid_skirt`), Stapel-Kragen mit umlaufender Auflage, versenkten Deckeln und
  45°-Trichter, Zuglasche (`lift_tab`, `lift_reach`).
- Design C „Friction + foot stack“: segmentierte 45°-Füße unter jedem Fach mit
  passender Nut im Deckel, Druckausrichtung über `print_orient`.
- Stapeln schaltbar (`stackable`) und als Vorschau (`stack_preview`).
- Ausgabemodi `Preview closed`, `Preview closed 2-color`, `Multicolor Export`
  und `Single Color Export`; Vorschau-Modi mit „NOT FOR PRINTING“-Banner.
- Bauraum-Prüfung über `printer` mit Warnung in der Konsole.
- Acht Varianten mit Bambu-Studio-Profilen für den P1S (PLA, Gyroid 15 %):
  `woche_7tage`, `woche_3fach`, `zwei_wochen`, `stackable-1week`,
  `stackable-2weeks`, `stackable-7day-3slots`, `stackable-7day-2slots-pills`
  und `nonstackable-1week`.
- Eigene Rundung `front_fillet` (Standard 8 mm) zwischen Fachboden und
  Vorderwand, damit Tabletten nach vorne herausgleiten; automatisch begrenzt,
  sodass sie weder Deckelschürze, Snap-Zunge noch Kragen berührt.

### Changed

- `fillet` ist jetzt auf 1–4 mm begrenzt (Standard 4) und rundet nur noch die
  senkrechten Ecken, die Seiten und die Rückkante.
- Stapelprinzip von Design B: Das Stapelmerkmal wanderte vom Deckel (Nut mit
  gebrücktem Boden) an die Box-Schale (Kragen mit Auflage), damit die Deckel ohne
  Brücke und Stützen druckbar sind.
- Die drei Designs liegen in einer konsolidierten Modelldatei mit gemeinsamen
  Fach-, Beschriftungs- und Druckerparametern.
- Das Reibdeckel-Spiel `lid_fit` wurde auf 0,07 mm je Seite verringert, weil
  die Passung zu locker war; bei mehreren Unterfächern wird es
  automatisch etwas enger.

### Fixed

- Versteifungssteg des Scharniers kollidierte mit den Wänden und den hinteren
  Fachecken; Steg schmaler und hinter die Deckelplatte verlegt.
- Snap-Verschluss berührte die Wand kaum und hielt nicht; stumpfe Rippe, höhere
  Rippe und größere Überschneidung (`latch_grip`).
- Reibverschluss-Zunge berührte die Wand nie; Vorzeichen des Spiels korrigiert.
- Deckel schloss um wenige Grad nicht ganz; Fase an der Klappkante der Wände.
- Lose Haken und Federn im Modell (zusätzliche Volumen) durch überlappende
  Verbindung zur Zunge behoben.
- Schwebende Deckel im flachen Druck-Layout des Reibdeckel-Designs.
