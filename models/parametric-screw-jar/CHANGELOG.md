# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-31

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem); alle Dateien des
Projekts stammen vom 2026-08-31 bzw. 2026-09-01. Das Modell entstand aus dem
runden Gefäß-Modell (`parametric-vessel`) mit Reibdeckel.

### Added

- Parametrisches rundes Schraubglas aus Glas und Schraubkappe: `diameter`
  (30–200 mm), `height` (30–300 mm), `wall` und `floor_t`.
- Grobes Trapezgewinde mit BOSL2 `threaded_rod`: Außengewinde mit vollem
  Körperdurchmesser auf einer Schulter (`lip_height`, `lip_flange`), Kappe mit
  Innengewinde; Steigung `thread_pitch` (Standard 2,8 mm), Eingriff
  `thread_turns` (Standard 3 Umdrehungen), Druckspiel `thread_slop` und
  `lid_tolerance`.
- Neun Oberflächenmuster für das Glas (`pattern`): glatt, V-Rillen, runde
  Rillen, rechteckige Nuten, Ringe, 45°-Diagonale, Kreuzschraffur, Noppen,
  Facetten; Steuerung über `pattern_count`, `pattern_depth`, `pattern_width`,
  `facet_width` und `pattern_fade`.
- Eigenes Muster für die Kappe (`cap_pattern`): wie das Glas (`match`),
  Rändel (`grip`) oder ein beliebiges Glasmuster; `cap_grip_count` und
  `cap_grip_depth`.
- Beschriftung auf der Glaswand (Buchstabe für Buchstabe auf dem Bogen, mit
  `body_text_angle`, `body_text_vpos`, `body_text_z`, `text_panel_margin`) und
  auf dem Kappendeckel; die Schrift bleibt bei jedem Muster lesbar.
- Ausgabemodi `Preview assembled`, `Preview open`, `both`, `Multicolor Export`,
  `body` und `lid`; Vorschau-Modi mit „NOT FOR PRINTING“-Banner und
  Start-Kamera, die beide Teile zeigt.
- Zweifarb-Gruppen für Glas, Kappe und Text; die Beschriftung bekommt jeweils
  die Farbe des anderen Teils.
- Getrennte Auflösung für Rundungen (`round_res`) und Gewinde (`thread_res`).
- Fase an der Unterkante (`bottom_chamfer`) gegen Elefantenfuß.
- Sechs Varianten (Kaffee, Zucker, Tee, Mehl, Gewürze, Nudeln) mit
  Bambu-Studio-Profilen für P1S und Bambu PLA Basic sowie zweifarbigen
  3MF-Dateien.

### Changed

- Das selbst gebaute Trapezgewinde mit schmalem, abgesetztem Hals wurde durch
  die BOSL2-Architektur ersetzt (Gewinde mit vollem Durchmesser, Kappe als
  schlanker Zylinder).
- Die Schulterunterseite läuft in 45° aus der Wand aus (selbsttragend) und hat
  eine verrundete Oberkante (`lip_round`); sie war zuvor ein waagerechter
  Überhang.
- Die Standard-Musterzahl `pattern_count` sank von 120 auf 60.
- Vertikale Rillen sind ein flacher Extrusionskörper über das Band zwischen
  den Randbändern statt einer verjüngten Form; `pattern_fade` bezeichnet jetzt
  das eingerückte glatte Band.

### Fixed

- Rechenbaum der OpenCSG-Vorschau und von MakerWorld sprengte die Grenze, wenn
  Muster und Gewinde in einer Differenz standen; die Musterdifferenz steht jetzt
  getrennt.
- Facettenmuster fraß als subtraktives Muster die Wand durch; es ist jetzt ein
  Schnitt mit einem Polygonprisma.
- Verjüngte Rillen erzeugten im Manifold-Renderer Millionen Facetten und
  Dateien im dreistelligen Megabyte-Bereich.
- Noppen reichten bis zum Rand oder explodierten bei hoher Musterzahl; die
  Zahl ist jetzt größenabhängig und auf rund 300 begrenzt, mit Randabstand.
- Beschriftung auf Facetten war nur teilweise lesbar; die Wand wird im
  Textfenster rund aufgefüllt.
- Zweifarbige 3MF-Dateien verloren in Bambu Studio die Farben
  („invalid config, load geometry data only“); die Metadaten der Datei wurden
  so gebaut, dass Bambu Studio die Konfiguration übernimmt.
