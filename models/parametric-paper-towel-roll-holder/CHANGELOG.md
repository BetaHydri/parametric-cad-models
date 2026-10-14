# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-31

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Beschreibung des Modells (Dateisystem); die
ersten Dateien stammen vom 2026-08-06.

### Added

- Parametrischer Küchenrollenhalter in drei Montagearten: Wand
  (`Vertical wall`), Unterschrank (`Under-shelf`) und Tischständer mit
  beschwertem Fuß, Säule und Kugel.
- Rollenvoreinstellungen (`roll_preset`: Standard 230, Deutsch 260,5, Groß 250,
  Kompakt 180, Eigen) sowie Kern- und Außendurchmesser (`core_inner_dia`,
  `roll_outer_dia`); `clearance_roll_dia` und `roll_clear_gap` halten den
  Unterschrank-Winkel für die größte Rolle frei.
- Federbremse gegen Abrollen mit zwei Bauarten (`brake_type`): Clip-Federblatt
  zum Einclipsen (`insert`, Standard) und druckintegriertes Blatt
  (`integrated`) mit abknipsbaren Haltestegen (`brake_tie_*`); Bremskraft über
  `brake_preload`.
- Clip-Federblatt mit kräftigem Fuß, Rastlippe, verjüngter Federzunge und
  gerundetem Dom an der Spitze; Parameter `brake_blade_*`,
  `brake_spring_thk`, `brake_tip_w` und `brake_slot_clear`.
- Gedrucktes Grobgewinde (`thread_*`, `split_at`) zum Teilen von Wandspindel
  und Tischsäule für 256-mm-Druckbetten.
- Ausgabemodi `Wall holder`, `Wall holder split`, `Table base`, `Table post`,
  `Table split` und `Brake spring`; Vorschauen mit Geisterrolle und
  „NOT FOR PRINTING“-Banner; der Clip wird bei Teilen mit Schlitz automatisch
  auf die Platte gelegt.
- Befestigung per Schrauben oder Klebeband (`screw_hole_dia = 0`), Plattenmaße
  `wall_plate_*`, Unterschrank-Parameter `shelf_*` und `web_t`,
  Tischparameter `base_*`, `post_h`, `knob_dia` und `weight_recess`.
- Bambu-Studio-Profile in PETG für P2S (geteilte und kleine Teile) und H2C
  (einteilige hohe Teile).
