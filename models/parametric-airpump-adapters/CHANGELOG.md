# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-11-01

### Added

- Parametrischer Schlauchadapter von der Pumpe auf SUP-, Boot-, Zelt-,
  Luftbett-, Pool-Spielzeug- und Ballventile: ein Drehteil, stehend und ohne
  Stützen gedruckt.
- Pumpenende als Feingewinde nach vermessenem Muster (eingängig, Rechtsgewinde,
  Außen-⌀ 7,92 mm, Steigung 0,75 mm, Tiefe 0,43 mm; `thread_d`, `thread_pitch`,
  `thread_depth`), alternativ glatter Stutzen mit 0–3 Dichtrippen oder Trichter
  (`pump_type`, `pump_d`, `pump_d_small`, `pump_len`, `pump_ribs`).
- Ventilende als Kegel mit 11° Halbwinkel, Stufenkegel, Stopfen mit Dichtrippen
  oder Ballnadel; sieben Voreinstellungen (`cone-6-12`, `cone-10-20`,
  `cone-14-26`, `steps-7-12`, `plug-8`, `plug-12`, `needle-ball`) und `custom`
  mit beliebigem Spitzen- und Basisdurchmesser, Länge, Stufen-/Rippenzahl und
  Kanaldurchmesser an der Spitze.
- Gerader, konzentrischer Luftkanal (`bore_d`), der sich über das Ventilende
  gleichmäßig verjüngt, und ein Bund, der den Adapter am Schlauch und am Ventil
  begrenzt (`collar_len`).
- Druckoptionen: 1–12 Kopien pro Platte, Druckerauswahl für P2S und andere
  256-mm-Betten, H2C und A1 mini (`printer`), Vorschaufarbe und Kreisqualität.
- Eingebaute Prüfungen, die statt eines Modells eine rote Meldung zeigen (Wand
  unter 1 mm, Kanal zu breit, Gewinde zu tief, Trichter falsch herum, zu lang
  für das Bett).
- Acht Varianten (`cone-6-12`, `cone-10-20`, `cone-14-26`, `steps-7-12`,
  `plug-8`, `plug-12`, `needle-ball`, `funnel-cone-10-20`) mit test-geslicten
  Bambu-Studio-Profilen für 3, 4 und 5 Wände.
- Automatische Prüfung am exportierten Netz (15 Konfigurationen und 9
  Verweigerungstests, 342 Prüfungen, keine fehlgeschlagen): Gewinde gegen das
  Muster, Außendurchmesser, Luftkanal, Wände, Überhänge und schwebende Inseln.
