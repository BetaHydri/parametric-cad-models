# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-10-15

### Added

- Parametrischer Etikettenhalter-Generator: Aufsteckclip für Wände von 1–9 mm
  (`wall_t`, `clip_fit`, `clip_grip`, `hook_depth`, `clip_w`, `arm_t`, `tilt`),
  Kleber- oder Klebebandplatte und Clip + Kleber.
- Zwei Etikettenarten: Papiertasche (nimmt Papierstreifen oder gedruckte
  Kachel auf; `pocket_t`, `overlap`) und in den Halter gravierter Text
  (`label_text`, `text_size`, `text_font`, `text_depth`, automatische
  Textgröße).
- Beliebige Etikettengröße von 16 × 8 mm bis 120 × 60 mm (`label_w`,
  `label_h`).
- Teileauswahl im Customizer: Vorschau an Beispielwand, Etikettenhalter,
  gedruckte Etikettenkachel, Halter + Kachel einfarbig, Halter + zweifarbiges
  Etikett (3 Farben, getrennte Farbgruppen und Körper) und nur zweifarbiges
  Etikett.
- Sechs fertige Varianten mit Bambu-Studio-Profilen (P1S), die flachen
  Varianten zusätzlich als Zweifarb-Datei.
- Druck ohne Stützen: Clips aufrecht auf zwei Armen, Klebeplatten flach auf
  der Rückseite, Kacheln flach mit der Vorderseite nach oben.
