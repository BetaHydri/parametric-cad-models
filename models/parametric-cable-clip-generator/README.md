# Parametric Cable Clip Generator – Einrast-Kabelclips zum Kleben, Schrauben, für Magnete und die Tischkante

[← Alle Modelle im Überblick](../../README.md)

Ein Generator für jedes Kabelproblem: Wähle 1 bis 10 Kabel, gib den Durchmesser jedes Kabels ein, wähle die
Befestigung – Klebeband, Senkschrauben, Magnete oder eine Klemme für die Tischkante – und druck einen
Einrast-Clip, der exakt passt. Auch gemischte Kabeldicken in einem Clip sind kein Problem, zum Beispiel USB
neben HDMI neben Netzkabel. Alles im MakerWorld-Customizer, ohne Stützen.

[![MakerWorld](https://img.shields.io/badge/MakerWorld-Modell-00AE42)](https://makerworld.com/en/models/3435533-parametric-cable-clip-generator)
![OpenSCAD](https://img.shields.io/badge/OpenSCAD-parametric-yellow)
![Bambu Lab](https://img.shields.io/badge/Bambu%20Lab-P1S%20%7C%20P2S%20%7C%20H2C-green)
![Lizenz](https://img.shields.io/badge/Lizenz-CC%20BY--NC--SA%204.0-blue)

> Das Modell mit allen Druckprofilen gibt es ausschließlich auf MakerWorld:
> 👉 [MakerWorld-Link: https://makerworld.com/en/models/3435533-parametric-cable-clip-generator](https://makerworld.com/en/models/3435533-parametric-cable-clip-generator)

![Sechs Kabelclips in Gelb, Grün, Blau und Grau an Wand, Tischkante und mit zehn Kabeln, mit Titel und Funktionssymbolen](images/01_hero.jpg)

## Inhaltsverzeichnis

- [Das Problem](#das-problem)
- [Die Idee](#die-idee)
- [Highlights](#highlights)
- [Parametrische Optionen](#parametrische-optionen)
- [Konstruktion](#konstruktion)
- [Varianten](#varianten)
- [Druckempfehlungen](#druckempfehlungen)
- [Was du sonst brauchst](#was-du-sonst-brauchst)
- [Anwendungsbeispiele](#anwendungsbeispiele)
- [Fehlersuche / FAQ](#fehlersuche--faq)
- [Entwicklungsgeschichte](#entwicklungsgeschichte)
- [Downloads](#downloads)
- [Lizenz](#lizenz)

## Das Problem

Kabel liegen selten dort, wo sie hinsollen:

- Fertige Clips passen auf genau eine Kabeldicke – das Ladekabel ist zu dick, das Audiokabel rutscht heraus.
- Mehrere Kabel nebeneinander brauchen mehrere Clips, die nie bündig sitzen.
- Klebeclips halten nicht überall; mal soll geschraubt, mal magnetisch befestigt werden.
- An der Tischkante fehlt ein Halter, der ohne Bohren auskommt.

## Die Idee

Ein einziges Modell erzeugt den passenden Clip: Die Kanäle sitzen nebeneinander, jeder mit eigenem
Durchmesser, und die Öffnung ist schmaler als das Kabel, sodass es einrastet und hält. Die Befestigung
wählst du getrennt davon. Der Kanal hat eine selbsttragende 45°-Dachform, deshalb braucht der Clip
keine Stützen. Alle Maße sind Millimeter, alle Werte Customizer-Parameter.

## Highlights

- **1–10 Kabel pro Clip:** Kanäle nebeneinander, jeder mit eigenem Durchmesser (2–30 mm). Ein Clip mit zehn
  Kanälen ist eine komplette Kabelordnung für Schreibtisch oder Rack.
- **Einrast-Schlitz:** Die Öffnung ist schmaler als das Kabel (`slot_ratio`), das Kabel klickt ein und bleibt sitzen.
- **Vier Befestigungen:**
  - **Kleben:** flache Rückseite für doppelseitiges Montageband.
  - **Schrauben:** zwei Senkbohrungen (M3, M4 oder beliebiger Durchmesser) mit sicherem Abstand zu Rand und Clipkörper.
  - **Magnete:** Taschen für Magnete 6 × 2 mm, unten offen, für Stahlflächen. Breite Clips bekommen automatisch bis zu vier Magnete.
  - **Tischkanten-Klemme:** C-förmige Klemme für Platten von 8 bis 60 mm Dicke mit Haltenoppen an beiden Backen.
- **Ohne Stützen:** Plattenclips liegen auf ihrer flachen Rückseite, Klemmen flach auf der Seite.
- **Jedes Maß ist ein Parameter:** Wandstärke, Cliplänge, Flanschbreite, Plattendicke, Backentiefe.

![Schraub-Clip für drei Kabel unterschiedlicher Dicke mit zwei Senkschrauben](images/03_schrauben-3-kabel.jpg)

## Parametrische Optionen

Die Namen entsprechen den Customizer-Parametern des Modells.

### Teileauswahl

| Parameter | Beschreibung | Standard | Auswahl |
|---|---|---|---|
| part | Druckteil oder reine Ansicht mit eingelegten Kabeln | clip | Clip (Druck), Vorschau mit Kabeln (nur Ansicht) |
| mount | Befestigungsart | plate | Platte (Kleben / Schrauben / Magnete), Tischkanten-Klemme |

### Kabel

| Parameter | Beschreibung | Standard | Bereich |
|---|---|---|---|
| cable_count | Anzahl der Kabelkanäle nebeneinander | 2 | 1–10 |
| cable_d | Kabeldurchmesser Kanal 1 | 6 | 2–30 mm, Schritt 0,5 |
| cable_d2, cable_d3, cable_d4 | Kabeldurchmesser Kanal 2 bis 4, 0 = wie Kanal 1 | 0 | 0–30 mm, Schritt 0,5 |
| cable_clear | Zusätzlicher Platz um das Kabel (gesamt) | 0,3 | 0–1 mm, Schritt 0,05 |
| slot_ratio | Schlitzbreite als Anteil des Kabeldurchmessers; kleiner = Kabel sitzt fester | 0,8 | 0,5–1, Schritt 0,05 |

### Weitere Kabel (Kanäle 5–10)

| Parameter | Beschreibung | Standard | Bereich |
|---|---|---|---|
| cable_d5 … cable_d10 | Kabeldurchmesser Kanal 5 bis 10, 0 = wie Kanal 1 | 0 | 0–30 mm, Schritt 0,5 |

### Körper

| Parameter | Beschreibung | Standard | Bereich |
|---|---|---|---|
| clip_length | Länge des Clips entlang des Kabels (Platte) bzw. Klemmtiefe (Tischkante) | 14 | 8–60 mm |
| wall | Wandstärke um die Kabel, Vielfache von 0,4 mm | 1,6 | 1,2–3,2 mm, Schritt 0,4 |

### Plattenbefestigung

| Parameter | Beschreibung | Standard | Bereich |
|---|---|---|---|
| fixing | Befestigung der Platte | adhesive | Klebeband, Schrauben (Senkung), Magnettaschen (6 × 2 mm) |
| plate_t | Plattendicke; wird für Schrauben und Magnete automatisch angehoben | 2,4 | 2–6 mm, Schritt 0,2 |
| flange | Plattenrand neben dem Kabelkörper; wächst bei Schrauben automatisch mit | 3 | 2–15 mm |
| screw_d | Schraubenlochdurchmesser (3,4 = M3, 4,4 = M4) | 3,4 | 2,5–5,5 mm, Schritt 0,1 |
| screw_margin | Material zwischen Senkkopf und Plattenrand bzw. Clipkörper | 2,4 | 1,6–6 mm, Schritt 0,4 |
| magnet_d | Magnetdurchmesser; die Anzahl der Taschen (1–4) folgt der Clipbreite | 6 | 4–10 mm, Schritt 0,5 |
| magnet_h | Magnethöhe | 2 | 1–4 mm, Schritt 0,5 |
| plate_extra | Zusätzliche Plattenlänge an jedem Ende | 2 | 0–10 mm |

### Tischkanten-Klemme

| Parameter | Beschreibung | Standard | Bereich |
|---|---|---|---|
| desk_t | Dicke von Tisch oder Regalboden | 25 | 8–60 mm |
| jaw_len | Tiefe der Backen über der Platte | 22 | 10–50 mm |
| jaw_t | Dicke von Backen und Rücken | 3,2 | 2,4–6 mm, Schritt 0,4 |
| grip_bump | Haltenoppen an jeder Backe, 0 = aus | 0,4 | 0–1 mm, Schritt 0,1 |

### Qualität

| Parameter | Beschreibung | Standard | Bereich |
|---|---|---|---|
| round_res | Glätte der runden Kanäle | 64 | 24–128, Schritt 8 |

## Konstruktion

### OpenSCAD-Ansatz

Das Modell ist reines OpenSCAD ohne externe Bibliotheken und läuft im MakerWorld-Customizer. Aus den
Kabeldurchmessern entsteht ein Kanalstapel; die Befestigung wird darum herum gebaut. Als Plattenclip
liegt das Profil flach, als Tischkanten-Klemme ist es ein C-Profil, das entlang der Klemmtiefe
extrudiert wird.

### Parametrische Logik

| Größe | Berechnung |
|---|---|
| Kanalradius | (Kabeldurchmesser + cable_clear) / 2 |
| Schlitzbreite | slot_ratio × Kabeldurchmesser, mindestens 1,5 mm |
| Senkkopf | Kopfdurchmesser = 2 × screw_d |
| Plattenrand bei Schrauben | mindestens Kopfdurchmesser + 2 × screw_margin |
| Plattendicke | bei Schrauben mindestens Senktiefe + 1,2 mm, bei Magneten mindestens Magnethöhe + 0,9 mm |
| Magnetanzahl | höchstens 4, abhängig von der Breite des Kanalstapels |

Mit den Voreinstellungen bei Schraubbefestigung (3,4-mm-Schraube, `screw_margin` 2,4 mm) ergibt sich ein
Kopfdurchmesser von 6,8 mm und ein Plattenrand von mindestens 11,6 mm. Die Werte sind aus den Formeln und den
Standardwerten abgeleitet.

### Besondere Algorithmen

- **Tropfenform:** Jeder Kanal besteht aus einem Kreis mit spitzem 45°-Dach, das ohne Stützen druckt.
- **Sicherer Schraubenrand:** Der Plattenrand wächst mit dem Senkkopf, damit zwischen Kopf und Rand immer
  mindestens `screw_margin` Material bleibt.
- **Gemischte Kabeldicken:** Die Kanäle werden Stück für Stück nach ihren Durchmessern gestapelt;
  `0` bedeutet „wie Kanal 1".
- **Tischkante:** Die Kanäle sitzen auf der Außenseite des Rückens, der Schlitz öffnet sich zur
  Seite; Backen haben Haltenoppen, abgeschrägte Spitzen und gerundete Innenecken.

### Druckoptimierungen

- Plattenclip auf der flachen Rückseite, Klemme flach auf der Seite – beides ohne Stützen.
- Wandstärke in Vielfachen von 0,4 mm, passend zur 0,4-mm-Düse.
- Magnettaschen sind unten offen; die Magnete werden von unten eingesetzt.

![Magnet-Clip für vier dünne Kabel](images/04_magnete-4-kabel.jpg)

## Varianten

Zum Modell gehören sechs Referenzkonfigurationen. Alle sind Einstellungen desselben Modells; im Customizer
stellst du beliebige andere Werte ein.

| Variante | Befestigung | Kabel |
|---|---|---|
| v1_adhesive_x2_6mm | Klebeband | 2 × 6 mm |
| v2_screw_x3_mixed | Senkschrauben | 3 Kabel: 4, 6 und 9 mm |
| v3_magnet_x4_4mm | Magnete | 4 × 4 mm, Cliplänge 12 mm |
| v4_desk_clamp_x2_25mm | Tischkanten-Klemme für 25 mm | 2 × 6 mm, Klemmtiefe 24 mm |
| v5_desk_clamp_x1_18mm | Tischkanten-Klemme für 18 mm | 1 × 8 mm, Backentiefe 20 mm, Klemmtiefe 24 mm |
| v6_screw_x10_4mm | Senkschrauben | 10 × 4 mm, Cliplänge 12 mm |

![Tischkanten-Clip für zwei Kabel an einer 25 mm dicken Platte](images/05_tischkante-25mm.jpg)

## Druckempfehlungen

| Einstellung | Empfehlung |
|---|---|
| Material | **PETG empfohlen**, PLA für Clips, die drinnen bleiben und selten geöffnet werden |
| Layerhöhe | 0,20 mm |
| Wände | 4 |
| Infill | 20 % Gyroid |
| Supports | keine |
| Ausrichtung Plattenclip | flach auf der Rückseite |
| Ausrichtung Tischkanten-Klemme | flach auf der Seite |

Besondere Hinweise

- **Warum PETG:** Die Schnapplippen und die Klemmbacken verbiegen sich bei jeder Benutzung. PETG biegt sich,
  statt zu brechen, kriecht unter der Dauerspannung der Klemme nicht und verträgt warme Orte (sonniges Fenster,
  Auto, neben dem Monitor) viel besser als PLA. **Für die Tischkanten-Klemme PETG verwenden.**
- **PETG-Tipp:** etwas langsamer drucken und mäßig kühlen; PETG sitzt etwas straffer, erhöhe `cable_clear`
  um etwa 0,1 mm, wenn sich ein Kabel schwer eindrücken lässt.
- **Kabel zu locker oder zu fest:** `slot_ratio` ändern (0,8 Standard; kleiner hält fester) und zuerst ein
  kurzes Probestück drucken.
- **Breite Clips (6–10 Kabel):** Eine lange flache Platte kann sich an den Ecken heben – Brim und ein
  sauberes, warmes Bett verwenden.
- **Magnete:** 6 × 2 mm Magnete von unten in die Taschen drücken, Polung beachten, einen Tropfen Kleber zugeben.
- **Kleben:** Fläche reinigen und einen Streifen doppelseitiges Montageband auf die flache Rückseite kleben.

![Schraub-Clip für zehn Kabel](images/07_schrauben-10-kabel.jpg)

## Was du sonst brauchst

- **Klebe-Clips:** doppelseitiges Montageband.
- **Schraub-Clips:** zwei kleine Senkschrauben (M3 für die Standard-Bohrung von 3,4 mm, M4 für 4,4 mm).
- **Magnet-Clips:** Neodym-Scheiben 6 × 2 mm (1–2 pro Clip) und eine Stahlfläche.
- **Tischkanten-Klemme:** ein Tisch oder Regalboden von 8 bis 60 mm Dicke – stell `desk_t` auf deine Platte ein.

## Anwendungsbeispiele

- **Schreibtisch:** Lade-, USB- und HDMI-Kabel an der Tischkante führen.
- **Wand:** Kabel an Wand oder Möbel kleben oder schrauben.
- **Stahlflächen:** Magnet-Clips an Metallflächen im Büro oder in der Werkstatt.
- **Rack und Homelab:** zehn Kabel in einem Clip ordnen.
- **Gemischte Kabel:** dünne und dicke Leitungen in einem Halter bündeln.
- **Farbcodierung:** Clips in verschiedenen Farben für verschiedene Kabelgruppen.

## Fehlersuche / FAQ

| Problem | Ursache | Lösung |
|---|---|---|
| Kabel lässt sich schwer eindrücken | Schlitz zu eng oder Druck zu straff | `slot_ratio` erhöhen oder `cable_clear` um etwa 0,1 mm erhöhen |
| Kabel rutscht heraus | Schlitz zu weit | `slot_ratio` verringern |
| Plattenecken heben sich beim Druck | Lange, flache Platte | Brim verwenden, Bett reinigen und warm halten |
| Schraubenkopf zu nah am Rand | `screw_margin` zu klein | `screw_margin` erhöhen; Flansch und Plattenlänge wachsen automatisch |
| Klemme sitzt zu locker oder zu stramm | `desk_t` passt nicht zur Platte | `desk_t` auf die tatsächliche Dicke einstellen |
| Klemmbacke bricht | Material zu spröde | PETG statt PLA verwenden |
| Magnete haften falsch herum | Polung nicht einheitlich | Alle Magnete gleich herum einsetzen |

## Entwicklungsgeschichte

Das Modell entstand im Oktober 2026 als Generator für Kabelclips und wurde im selben Monat auf MakerWorld
veröffentlicht. Zuerst gab es bis zu vier Kanäle, später wuchs die Zahl auf zehn.

Die Bilder in diesem Repository sind Renderings der Modellgeometrie beziehungsweise daraus abgeleitete
Szenenbilder; Wand, Tischplatte und die Kabel sind illustrativ.

![Gelber Klebe-Clip für zwei Kabel an einer Wand](images/02_kleben-2-kabel.jpg)

![Gelber Tischkanten-Clip für ein dickes Kabel an einer 18 mm dicken Platte](images/06_tischkante-18mm.jpg)

## Downloads

Print files are intentionally available exclusively on MakerWorld.

👉 MakerWorld-Link: [https://makerworld.com/en/models/3435533-parametric-cable-clip-generator](https://makerworld.com/en/models/3435533-parametric-cable-clip-generator)

Profil: [https://makerworld.com/en/@BetaHydri](https://makerworld.com/en/@BetaHydri)

## Lizenz

Dokumentation und Bilder in diesem Repository: © BetaHydri. Das Modell (inkl. Quellcode) und alle
Druckdateien werden ausschließlich über MakerWorld unter der dort angegebenen Lizenz
(CC BY-NC-SA 4.0) verteilt. Dieses Repository enthält bewusst keine Modell-, Quellcode- oder Druckdateien.
