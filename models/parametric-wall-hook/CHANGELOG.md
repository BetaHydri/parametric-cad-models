# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-08-05

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der vierteiligen Modelldatei und der
Referenzvarianten (Dateisystem). Die Entwicklung begann am 2026-07-13.

### Added

- Klappbarer Wandhaken aus vier getrennten, support-freien Teilen: Haken (Arm),
  Gehäuse, Scharnier-Stift und Außenschale.
- Lasttragendes Stift-Scharnier (`pin_d`, `pin_play`, `holder_pin_clear`); der
  Stift wird seitlich durch Gehäuse, Arm und Gehäuse gesteckt, die Außenschale
  verdeckt seine Enden. Der Stift wird stehend gedruckt.
- Drehpunkt unten, harter Ausklapp-Anschlag durch eine Ferse an der massiven
  Rückwand (`max_open_angle`).
- Bügel-Sattelkerben als 45°-V-Nuten (`hanger_notches`, `notch_depth`) und
  Griff-Fingermulde an der Hakenspitze (`grip_notch_depth`, `grip_notch_wfrac`).
- Einrast-Noppen am Gehäuserand (`detent_enable`, `detent_grip`, `detent_pos`)
  mit passender Mulde im Haken für bündigen, einrastenden Sitz.
- Oberer Halte-Steg an der Rückwand mit Halte-Noppe (`top_seat_enable`,
  `top_seat_grip`, `top_seat_pos`).
- Außenschale mit Mantel-Relief: vertikale Rillen, horizontale Ringe, Punkte oder
  Rautung (`relief_style`, `relief_size`, `relief_depth`), optional auch auf der
  Arm-Vorderseite (`arm_relief`).
- Zwei Montagearten: Klebeband oder Senkkopf-Schrauben (`mount_mode`,
  `screw_hole_d`, `screw_head_d`); optional umlaufend geschlossenes Gehäuse ohne
  Schale (`use_shell`).
- Passungsparameter (`cover_wall`, `fit_clear`, `hinge_gap`, `snap_protr`).
- Ausgabemodi für Vorschau (ausgeklappt, zugeklappt) und Druck (Haken, Gehäuse,
  Stift, Außenschale, alle Teile auf einer Platte, mehrfarbig oder einfarbig);
  Vorschau-Farbschemata und durchscheinende Schale (`color_scheme`,
  `cover_transparent`).
- Drei Referenzvarianten (Rillen, Rautung, Punkte) mit Bambu-Studio-Profilen für
  den P2S (PETG-CF).

### Fixed

- Nicht-manifolde Kanten im Gehäuse: Die Schwenkbahn wird jetzt aus einem
  2D-Profil einmal extrudiert statt aus vielen gedrehten 3D-Körpern vereinigt.
- Haken klappte über den Anschlag hinaus: Die Ferse ist jetzt ein vollbreiter
  Keil, der flächig an der Rückwand aufsetzt.
- Der obere Halte-Steg „schwebte“: Er ist jetzt in die massive Rückwand verankert.
- Sattelkerben druckten im Scharnierspalt zu Spaghetti: Der Arm wird separat und
  flach gedruckt.
