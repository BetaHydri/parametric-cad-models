# Schreibtisch-Organizer 3D-drucken: schräge Schale, austauschbare Einsätze, parametrischer Stifthalter

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3022869-parametric-deskorganizer – Profil:
<https://makerworld.com/en/@BetaHydri>

![Parametric Desk Organizer – schräge, geriffelte Schale mit Stifthalter und Einsätzen](images/01_hero_front_left.png)

## Motivation: Ordnung, die sich dem Bedarf anpasst

Mein Schreibtisch wechselt zwischen Büro, Elektronik-Basteln und
Homelab-Schrauberei. Jeder Organizer, den ich gebaut oder gekauft habe, war für
genau einen Zustand optimiert: viele Stifte, oder viele Kleinteile, oder
Haftnotizen. Sobald sich der Zustand änderte, passte die Aufteilung nicht mehr.
Ein einteiliges Druckteil mit festen Fächern löst das nicht, weil jede Änderung
einen Neudruck des ganzen Teils bedeutet.

Beim **Parametric Desk Organizer** liegt die Struktur deshalb in
**herausnehmbaren Einsätzen**. Die Schale druckst du einmal, die Einsätze nach
Bedarf – und tauschst sie, wenn sich der Schreibtisch ändert.

## Funktionen im Überblick

- **Schräge, geriffelte Schale:** vorne niedrig, hinten hoch (`front_height`,
  `back_height`), mit gerundeten senkrechten Ecken (`corner_r`) und
  Rippenstruktur an der Außenwand.
- **Fünf oder sechs Fächer:** `split_top_right` teilt das breite hintere Fach in
  zwei Einsätze.
- **Sieben Einsatztypen pro Fach:** offene Box, Stift-Löcher, zwei Fächer, drei
  Fächer, 2×2-Raster, drei Schlitze und Kombi (ein großes plus zwei kleine
  Fächer).
- **Frei skalierbar:** `outer_width` (120–360 mm), `outer_depth` (90–320 mm)
  und die Verhältniswerte der Spalten und Reihen; Einsätze rechnen sich
  mit.
- **Passung einstellbar:** `insert_clearance` (Standard 0,15 mm je Seite).
- **Zweifarb-Optik:** Schale und Einsätze als getrennte Objekte in
  verschiedenen Farben drucken.

![Der Organizer von vorne rechts: breite Fächer und feine Rippen an der Außenwand](images/02_front_right.png)

## Entwicklungsprozess

Der erste Stand stammt vom Juli 2026: eine Schale mit festen Fächern. Aus dem
Wunsch, Fächer nachträglich zu ändern, wurde das Einsatzsystem. Anfang August
2026 folgten vier Referenzvarianten (Standard, geteiltes hinteres Fach,
kompakt mit 160 × 120 mm und breit mit 250 × 170 mm) samt Profilen für den
P1S. Die letzte Änderung der Modelldatei stammt vom 31. August 2026.

## Technische Hintergründe

**Die Schräge.** Die Schale ist die konvexe Hülle von vier senkrechten
Zylindern: zwei vorne mit niedriger, zwei hinten mit hoher Höhe. Die Oberkante
bleibt eine saubere Gerade, und nur die senkrechten Außenecken sind gerundet.
Der Innenraum entsteht aus zwei dünnen Scheiben und wird 1 mm über die
Außenschräge hinausgezogen, damit vorne kein Restdach stehen bleibt.

**Die Zellenliste.** Das Modell baut eine Liste aller Fächer mit Position,
Breite, Tiefe und Einsatztyp auf. Schale, Einsätze und Vorschau lesen dieselbe
Liste. Spalten und Reihen werden aus Verhältniswerten berechnet: Spaltenbreite
= nutzbare Innenbreite × Verhältnis / Summe der Verhältnisse. Mit den
Standardwerten ergeben sich Spalten von ca. 65,2 / 75,0 / 75,0 mm und Reihen
von je 72,6 mm Tiefe.

**Der Einsatz.** Jeder Einsatz ist das Fachmaß minus zweimal
`insert_clearance`, und seine Oberkante folgt der Schräge der Schale – mit
`insert_top_gap` (0,2 mm) unter dem Rand. Die Wandstärke ist getrennt
einstellbar (`insert_wall_t`, Standard 1,8 mm).

**Der Stifthalter.** Der Stifteinsatz ist ein Vollblock mit Sacklöchern von
oben. Aus Lochdurchmesser, Steg (`pen_gap`) und Randabstand berechnet das
Modell, wie viele Zeilen und Spalten passen, zentriert das Raster und versetzt
jede zweite Zeile (Zeilenabstand × 0,866 bei hexagonaler Packung). Bei
`pen_row_diameters = 1` wird die Tiefe in Drittel geteilt: vorne 8 mm
(Bleistift, Kugelschreiber), Mitte 12 mm (Filz-, Malstift), hinten 20 mm
(Klebestift), jeweils plus 0,25 mm Spiel. Die Bohrung reicht über die höchste
Stelle der Einsatz-Schräge hinaus, damit jedes Loch ein voller Kreis ist.

**Die Rippen.** Die Rillen werden pro Seitenwand gleichmäßig verteilt. Der
Abstand ist Umfang / `relief_count`, an jeder Ecke bleibt `relief_corner`
frei. Die Rillentiefe wird auf Wandstärke − 0,7 mm begrenzt, damit die Wand
nie durchschnitten wird.

![Draufsicht: Stifthalter mit versetzt gepackten Löchern und Fächer mit Trennwänden](images/04_top_iso.png)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für den **P1S** mit PLA gebaut: 0,20 mm Layerhöhe, 3 Wände,
Gyroid 15 %. Die Schale ist oben offen, die Einsätze stehen aufrecht –
Stützen sind nicht nötig. Für die feinste Rippenstruktur kannst du auf 0,16 mm
gehen. Bei PETG erhöhst du `insert_clearance` auf ca. 0,20–0,25 mm.

Die Einsätze exportierst du einzeln: `part_mode = 1` ist die Schale, `2` bis
`7` sind die Einsätze in der Fachreihenfolge (hinten links, hinten rechts,
dann vorne links nach rechts). Für Zweifarb-Optik weist du im Slicer Schale und
Einsätzen verschiedene Filamente zu; die Farben im Customizer
(`shell_color`, `insert_color`) gelten nur für die Vorschau.

Wenn ein Einsatz zu stramm sitzt, erhöhst du `insert_clearance`; wenn er
wackelt, verringerst du es.

## Einsatzideen

- Stifte nach Größe sortiert plus offene Boxen für Haftnotizen und Büroklammern
- Elektronik-Arbeitsplatz: Bits, Lötzinn, SD-Karten, USB-Sticks
- Homelab-Kleinteile: Schrauben, Kabelbinder, Käfigmuttern
- Passgenau für die Schublade über Breite und Tiefe
- Nähtisch oder Bastelecke mit der Kombi aus großem und zwei kleinen Fächern

![Mehrere Organizer in verschiedenen Farbkombinationen auf einem Schreibtisch](images/06_lineup-schreibtisch.jpg)

## Fazit und Aufruf zum Mitmachen

Der Organizer ist ein Baukasten: eine Schale, die sich an dein Maß anpasst, und
Einsätze, die du nachdrucken kannst. Wenn du ihn druckst, freue ich mich über
**Makes** mit Fotos, besonders mit eigenen Maßen und Einsatzkombinationen.
Rückmeldungen zur Passung auf anderen Druckern helfen, den Standardwert für
`insert_clearance` zu verbessern. Schreib einfach einen Kommentar auf
MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3022869-parametric-deskorganizer

---

## 10 SEO-Titel

1. Schreibtisch-Organizer 3D-drucken: schräge Schale mit austauschbaren Einsätzen
2. Parametrischer Organizer für Bambu Lab: Maße und Fächer im Customizer
3. Stifthalter 3D-Druck mit automatischer Lochverteilung (OpenSCAD)
4. Organizer mit herausnehmbaren Einsätzen: nur den Einsatz neu drucken
5. Schreibtisch-Ordnung nach Maß: parametrischer Organizer für jede Schublade
6. Stifthalter mit drei Lochgrößen: Bleistift, Filzstift, Klebestift
7. Organizer ohne Stützen drucken: oben offene Schale, aufrechte Einsätze
8. Zweifarbiger Organizer: Schale und Einsätze in Kontrastfarben
9. Parametric Desk Organizer: sloped ribbed shell with swappable inserts
10. Geriffelte Außenwand 3D-drucken: Rippenprofil, Anzahl und Tiefe einstellen

## 20 relevante Suchbegriffe

- Schreibtisch-Organizer 3D-Druck
- Organizer 3D drucken
- Stiftehalter 3D-Druck
- Stifthalter parametrisch
- Desk organizer 3D print
- Parametric desk organizer
- Organizer mit Einsätzen
- modularer Organizer
- Büro Organizer 3D-Druck
- Schreibtisch aufräumen 3D-Druck
- OpenSCAD Organizer
- Bambu Lab P1S Organizer
- MakerWorld Organizer
- Customizer Organizer
- Kleinteile Organizer 3D-Druck
- Elektronik Arbeitsplatz Organizer
- Schubladen Organizer nach Maß
- Organizer ohne Support
- Zweifarb Organizer 3D-Druck
- funktionale 3D-Drucke

## 10 GitHub-Tags

- desk-organizer
- organizer
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- modular
- functional-print

## 5 LinkedIn-Post-Ideen

1. „Struktur in die Einsätze, nicht in die Schale“: Warum ein Organizer mit
   herausnehmbaren Teilen besser altert als ein einteiliges Druckteil.
2. „Ein Stifthalter, der sich selbst füllt“: Wie das Modell aus Lochdurchmesser
   und Steg die Zeilen und Spalten berechnet.
3. „Das richtige Spiel für einen Einsatz“: Warum `insert_clearance` ein eigener
   Regler ist und wie PETG sich vom PLA unterscheidet.
4. „Eine Zellenliste als Single Source of Truth“: Wie Schale, Einsätze und
   Vorschau dieselben Daten lesen.
5. „Vom starren Teil zum Baukasten“: Entwicklung vom Juli-Stand bis zu den vier
   Referenzvarianten.

## 5 Reddit-Post-Ideen

1. r/functionalprint – „Desk organizer with removable inserts, sloped ribbed
   shell, fully parametric“ mit dem Hero-Bild.
2. r/openscad – „Auto-filling a block with hex-packed holes of three sizes by
   depth zone“: Erklärung des Ansatzes ohne Quelltext.
3. r/BambuLab – „Two-tone organizer: print shell and inserts as separate
   objects with different filaments“.
4. r/3Dprinting – „Sloped insert tops that follow the shell edge: how I derive
   front and back height per cell“.
5. r/3Dprinting – „Insert clearance on a printed organizer: what works for you
   in PLA vs PETG?“ als Diskussionsfrage.
