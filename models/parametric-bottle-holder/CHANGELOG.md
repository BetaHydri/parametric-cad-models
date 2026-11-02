# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-10-29

### Added

- Parametrischer Halter für Flaschen und Dosen mit drei Befestigungen: Wand
  (zwei Schrauben, Köpfe in Senkungen im Inneren des Bechers), Fahrrad
  (64-mm-Lochbild für Flaschenhalter mit M5-Langlöchern, Rohrmulde für 20–60 mm,
  Gurttunnel für Klettband oder Kabelbinder) und Auto (Getränkehalter-Adapter mit
  Flansch und Quetschrippen).
- Sieben Presets (Dose 250 ml, Dose 330 ml schlank, Dose 330 / 440 / 500 ml,
  PET-Flasche 0,5 l, Flasche 0,75 l, Fahrradflasche 0,75 l, Weithalsflasche 1 l)
  sowie ein eigener Durchmesser von 40–110 mm (`preset`, `custom_d`, `fit`).
- Offener, einrastender C-Clip (`style`, `opening_pct`) mit Dehnungsabschätzung
  der Arme; zu enge Öffnungen werden verweigert. Alternativ geschlossener Becher.
- Wahl von Schraubengröße (M3 / M4 / M5) und Sitz (Senkung oder Zylindersenkung),
  Wandstärke, Bodenstärke, Ablaufloch und Höhe (`screw`, `seat`, `wall`,
  `floor_t`, `drain`, `holder_h`).
- Fahrrad: Rohrdurchmesser, Gurttunnel und Gurtbreite (`tube_d`, `strap`,
  `strap_w`); Auto: Getränkehalter-Durchmesser und -Tiefe, Anzahl und Quetschung
  der Rippen, Flanschbreite (`cup_d`, `adapter_depth`, `ribs`, `crush`, `flange`).
- Bis zu sechs Halter pro Platte (`copies`); stufenweise eingerückte erste Lagen
  gegen den Elefantenfuß; stützenfreier Druck.
- Vier Varianten (`wall-can-330-500`, `wall-bottle-075`, `bike-bottle-075`,
  `car-adapter-can-75`) mit test-geslicten Bambu-Studio-Profilen für den P2S mit
  3, 4 und 5 Wänden.
- Automatische Prüfung an der echten Geometrie in 17 Konfigurationen
  (308 Prüfungen, 0 fehlgeschlagen): Flaschenabstand, echte Schraubenmodelle,
  Material hinter den Sitzen, C-Clip-Dehnung, Rohrmulde, Gurttunnel,
  Quetschrippen, ein massiver Körper, Überhänge und drei verweigerte
  Einstellungen.
