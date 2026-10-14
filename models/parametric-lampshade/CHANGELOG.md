# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-07-17

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht den frühesten Vorschaubildern und der Modellbeschreibung
(Dateisystem); die Einträge fassen den Stand bis zur letzten Änderung der
Modelldatei am 2026-08-05 zusammen.

### Added

- Parametrischer Lampenschirm als offenes, wasserdichtes Rohr mit frei
  einstellbarer Grundform: `shade_height`, `base_diameter`, `top_diameter`,
  `belly_bulge`, `belly_position`, `wall_thickness`.
- Zwei Betriebsarten in einer Datei: Tischlampe (LED nach oben, Tischfuß) und
  Hängelampe (LED nach unten, Hängekappe mit mittigem Kabelweg).
- Sechs Oberflächenstile: `smooth`, `vertical_waves`, `twist_flutes`,
  `ripple`, `scallop`, `facets`, dazu `surface_twist`.
- Fünf Durchbruch-Muster: `none`, `diamond`, `hex`, `mesh`, `slots`.
- LED-Halter für das Bambu LED Lamp Kit 001 (MH001) mit anpassbarem Puck,
  Schraubenabstand und Kabelnut.
- Parameter `plug_dia` für den Steckerdurchmesser: Das Kappenloch, die
  Knotenmulde und die Kabelnut am Fuß werden für den Stecker bemessen.
- Optionaler Diffusor mit konzentrischen oder radialen Rillen.
- Vorschau-Modi für Tisch- und Hängelampe (zweifarbig, mit LED-Puck und rotem
  „NOT FOR PRINTING“-Banner) sowie die Druckmodi `DRUCK Schirm`,
  `DRUCK Tischfuss`, `DRUCK Haengekappe`, `DRUCK Diffusor`,
  `DRUCK Tischlampe Platte` und `DRUCK Haengelampe Platte`.
- Versteifungsringe für `slots` (`slot_rings`, `slot_ring_width`) und feste
  Stegzahl `slot_count`.
- Drei Druckvarianten (`wellen`, `hex`, `twist`) mit Bambu-Studio-Profilen für
  P1S und PLA (Schirm und Tischfuß als zwei Objekte), Stand 2026-08-04.
- Studio-Renderbilder der montierten Tischlampe je Variante.

### Changed

- `wall_thickness` Standardwert 1,2 mm, damit die Wand lichtdurchlässig ist.
- `opening_style` Standardwert `hex`: Das offene Muster ist standardmäßig aktiv,
  damit die Lampe von Anfang an leuchtet.
- Der Abstand der Teile in der Kombi-Platte berücksichtigt jetzt
  `belly_bulge`, `wave_amp` und `base_flange`.

### Fixed

- Tischfuß: Der LED-Halter war von einer massiven Platte und einem vollen
  Lippenzylinder abgedeckt (Puck nicht einsetzbar, Licht blockiert). Die Lippe
  ist jetzt ein Ring und eine offene Lichtbohrung führt nach oben.
- Schirm: Die Flächenwicklung war invertiert (negatives Volumen); die
  Normalen zeigen jetzt nach außen.
- `twist_flutes` war identisch mit `vertical_waves`; der Stil hat ein eigenes
  Profil mit eingebauter Halbdrehung.
- `ripple` in Kombination mit `slots` zerfiel in lose Teile; die
  Oberflächenstörung wird bei `slots` gedämpft.
- `mesh`: Die Lochgröße ist begrenzt, damit Stege nicht verschwinden.
- Diffusor: Die Vorschau mit konzentrischen Rillen brach wegen verschachtelter
  Differenzen ab; jede Rille ist jetzt ein einzelner Schneidkörper.
- Die Kombi-Platte aus Schirm und Fuß passte nicht auf ein 256-mm-Bett; die
  Profile laden beide Teile als getrennte Objekte.

### Removed

- Nichts.
