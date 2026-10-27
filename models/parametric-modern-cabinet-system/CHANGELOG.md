# Changelog

Alle wesentlichen Änderungen an diesem Projekt werden in dieser Datei
dokumentiert.

Das Format basiert auf
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/), und dieses Projekt
folgt [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-10-27

Hinweis: Eine Versionsnummer ist in den Quellen nicht belegt. Das Datum ist der
Tag der Veröffentlichung dieser Dokumentation.

### Added

- Parametrisches Schrank- und Regalsystem als Mehrplatten-Bausatz für den Bambu
  Lab P2S (256 mm) und H2C (330 × 320 mm): große Platten in bauplattengroße
  Kacheln geschnitten, verbunden durch V-Nut-Feder-Fugen und
  Schmetterlingsschlüssel; Böden, Deckel und Boden gleiten in
  Halb-Schwalbenschwanz-Nuten, gesichert durch die Rückwand, optional mit
  M4-Schrauben und Mutter oder Flügelschrauben.
- Drei fertige Bausätze als 3MF: offenes Regal 360 × 500 mm (P2S, 15 Platten),
  Schrank mit einer Tür 300 × 500 mm (P2S, 19 Platten) und Sideboard mit zwei
  Türen 580 × 500 mm (H2C, 18 Platten), jeweils mit Passungstest.
- Türen mit verdeckten, gedruckten Print-in-Place-Scharnieren (Geometrie aus dem
  Hinge Designer, M3-Senkkopfschrauben, optional M3-Heat-Set-Einsätze) als
  Standard; alternativ `pivot` (bündige Tür, M4-Zapfenschrauben mit Einsätzen)
  und `knuckle` (Laschen mit gedrucktem Stift).
- Verstärkte Schraub- und Einsatzzonen als Modifier-Volumen in der 3MF (6
  Wandlinien, 100 % Füllung nur um die Löcher).
- Griffe: Bohrbilder für eigene Griffe (M3–M6), Griffmulde oder eingebauter
  gedruckter Bügelgriff; Magnete als Türverschluss.
- Montageanleitungen als PDF und Markdown, Deutsch und Englisch, für alle drei
  Bausätze: Bilder mit Pfeilen für die Schieberichtung, Nahaufnahmen von
  Schmetterlingsschlüssel, Mutter und Scharnier, Zubehörliste, Druckplan je
  Bauplatte und Zusammenfassung der Prüfungen.
- Verifikation an den echten exportierten Netzen: Druckbarkeit, simulierte
  Montage (Schiebeweg-Kollisionstests), Verriegelung und Statik; Kippen und
  Wandbefestigung sind dokumentiert.

### Known issues

- Die Festigkeitswerte der Scharniere (M3-Ausziehkraft 120 N, Einsatz 100 N) sind
  vorsichtige Annahmen und noch nicht durch einen Test belegt.
- Die Verstärkungszonen gelten nur in der 3MF; bei reinen STL-Dateien müssen 4–5
  Wände um die Scharnierschrauben selbst eingestellt werden.
