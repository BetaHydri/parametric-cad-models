# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-10-12

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum
entspricht der letzten Änderung der Modelldatei (Dateisystem). Die Entwicklung
begann am 2026-09-03; die sechs Referenzvarianten mit Profilen entstanden am
2026-09-04.

### Added

- Parametrischer Mülleimer aus drei Teilen: Eimer (`body`), Rahmen (`frame`) und
  Schwenkklappe (`flap`), rund (`round`) oder eckig (`rect`) mit Eckenradius
  `corner_r`.
- Selbstschließende Klappe durch außermittige Schwenkachse (`pivot_offset`),
  Zapfen (`pin_d`, `pin_len`) in Rahmenbohrungen mit einstellbarem Spiel
  (`pivot_play`) und Spalt zur Öffnung (`flap_gap`).
- Anschlag-Lippe für die geschlossene Klappe (`stopper_w`, `stopper_arc`) als
  dünner Ring mit 45°-Unterseite.
- Öffnungsbegrenzung durch zwei Anschlagblätter an den Gelenkflanken
  (`swing_limit`, `stop_angle`).
- Rahmen mit Kragen auf abgesetzter Schulter des Eimers (`frame_wall`,
  `frame_overlap`, `frame_top`, `fit_clearance`, `frame_chamfer`) und
  Schnapp-Wulst (`snap_enabled`, `snap_depth`).
- Rillenstruktur mit drei Profilen (rechteckig, V-Nut, gerundet) über
  `relief_enabled`, `relief_style`, `relief_count`, `relief_depth`,
  `relief_width` und `relief_corner`.
- Drall der Rillen (`relief_angle`): Spirale beim runden, diagonal beim eckigen
  Eimer.
- Auslauf der Rillen unter dem Kragen (`relief_fade`).
- Beschriftung an der Eimerwand (Größe, Tiefe, Seite bzw. Winkel, vertikale
  Position, Freiraum um den Text) und auf der Klappenoberseite.
- Griffrillen auf der Klappe, die die Druckstelle markieren.
- Ausgabemodi `Preview assembled`, `Preview open`, `print all`,
  `Multicolor Export`, `body`, `frame` und `flap`; Vorschau-Modi mit
  „NOT FOR PRINTING“-Banner.
- Bauraumprüfung mit Konsolenwarnung für H2D, H2C, P2S und P1S
  (`target_printer`).
- Sechs Referenzvarianten (`round-120-fluted`, `rect-115-eco`,
  `round-150-vgroove`, `rect-150-recycle`, `round-160-ribbed`, `rect-118-paper`)
  mit Bambu-Studio-Profilen für P1S, P2S, H2C und H2D (PLA).

### Changed

- Die Klappe wird mit der Oberseite nach unten gedruckt, damit Fläche und
  Beschriftung sauber werden.
- Rillentiefe auf `wall` − 0,8 mm begrenzt, damit die Wand nie durchbrochen wird.

### Fixed

- Streifenband unter dem Kragen: Der Absatz am Eimerrand wird mit einem Schnitt
  erzeugt, der die Wand überragt, damit keine deckungsgleiche Fläche entsteht.
- Anschlag-Lippe: Sie füllte zeitweise die Öffnung (Hülle aus zwei Ringen) und ragte
  über die Außenwand; sie ist jetzt ein dünner Ring, an der Außenwand beschnitten.
- Schnapp-Nut im dünnen Eimerrand führte zu einem leeren Layer beim Slicen; die
  Nut entfiel, die Schnapp-Wulst am Rahmen hält den Kragen.
- Gelenk-Nocken ragten über die Außenwand des Rahmens hinaus; sie sind jetzt an die
  Außenfläche beschnitten.
- Anschlagblätter schwebten zeitweise als eigene Körper; sie sind jetzt mit
  Klappe bzw. Rahmen verschmolzen.
