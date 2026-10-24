# Regal für schmale Nischen 3D-drucken: parametrisch, gerade oder schräg, mit gedruckten Schraubfüßen

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3464475-parametric-niche-shelf-system – Profil:
<https://makerworld.com/en/@BetaHydri>

![Camper Niche Shelf System – zwei fertige Sets](images/01_hero.jpg)

## Motivation: Eine Lücke, in die kein Regal passt

Neben der Toilette im Camper gibt es eine Nische von 160 × 300 × 380 mm. Ein
fertiges Regal in diesem Maß gibt es nicht, und im Fahrbetrieb muss alles
festsitzen: Flaschen, Sprühdosen, Toilettenpapier. Dazu läuft oben ein
Lüftungsschlauch durch. Das **Parametric Niche Shelf System** löst das mit
einem Baukasten: Maße im MakerWorld-Customizer eintragen, Schalen, Pfosten,
Füße, Wandplatten und Abdeckung werden dazu berechnet – und alles lässt sich
auf einem Drucker drucken.

## Funktionen im Überblick

- **1 bis 4 Schalen** mit Rand vorne und seitlich, jede mit eigener Höhe und
  Tiefenbegrenzung.
- **Gerade oder schräge Nische:** `niche_w_back` und `niche_w_front` getrennt
  einstellen, die Schalen folgen der schrägen Wand.
- **Fünf Befestigungsarten:** Pfosten und Füße mit Rückwandschrauben, mit
  Wandwinkeln, freistehend ohne Wandkontakt, nur Wandwinkel, nur Rückwand.
- **Gedruckte Schraubfüße** mit Trapezgewinde zum Ausgleichen des Bodens –
  nichts zu kaufen außer Schrauben.
- **Vorderrand massiv oder als Wabengitter.**
- **Schlauchabdeckung** als eingeschobenes „L“ mit Wandarmen.
- **Passungstest** in fünf Minuten, bevor der große Druck startet.
- **Zwei fertige Sets** (3MF, vier Platten) für den Bambu Lab H2C in ASA.

![Schräge Nische mit 160 mm hinten und 110 mm vorn](images/06_schraege-nische.jpg)

## Entwicklungsprozess

Der Anfang war ein Besuch mit dem Maßband in der Nische: Tiefe, Breite
hinten und vorn, Höhe, Lage des Schlauchs. Diese Maße bilden die Vorgaben des
ersten Modells. Damit das Regal auch anderswo passt, ist alles ein Parameter,
und das Modell prüft die Eingaben selbst: Liegen Schalen zu dicht beieinander,
ist die Schale zu schmal oder sind Schraubenlöcher zu nah, bricht die
Berechnung mit einer klaren Meldung ab.

![Nische mit Maßband und Lüftungsschlauch](images/11_nische-vermessen.jpg)

Der Statushinweis gehört dazu: Alles ist in der Konstruktion geprüft und für
die 3MF-Dateien probegeslict, **aber noch nicht von mir gedruckt**. Deshalb
gibt es die Passungstest-Platte als ersten Druck.

## Technische Hintergründe

**Schräge Wand.** Die Breite an der Position y ist eine lineare Funktion
zwischen `niche_w_back` und `niche_w_front`. Die rechte Kante jeder Schale,
Pfostenpositionen und Wandwinkel werden aus dieser Funktion abgeleitet; die
Schalenbreite wird zusätzlich durch `tray_max_w` begrenzt.

**Pfosten und Füße.** Die Pfosten stehen unten in einer Zentriertasche und
werden nur oben von einer M4-Schraube gehalten. Bei einer kürzeren oberen
Schale (`tray_depth_limit`) rücken die Pfosten automatisch nach hinten. Die
Schraubfüße haben ein grobes Trapezgewinde (Ø 18 mm, Steigung 3,5 mm), das als
reiner Perimeter-Druck funktioniert.

**Schlauchabdeckung.** Ein geschlossenes „U“ lässt sich um einen an beiden
Enden befestigten Schlauch nicht montieren. Deshalb ist die Abdeckung ein „L“,
das von vorne eingeschoben und an Wandarmen unterhalb des Schlauchs
festgeschraubt wird. Eine Pfadsimulation bestätigt, dass sie sich einschieben
lässt und Schlauch, Anschluss und Schalen freibleiben.

**Wandwinkel.** Für die Befestigungsarten mit Winkeln rechnet das Modell eine
Lastabschätzung (Gewicht je Schale, Faktor für Fahrbetrieb) und warnt, wenn die
Auszugskraft je Wandschraube zu hoch wird. Das ist ein Richtwert; die Wand
muss der Nutzer selbst prüfen.

![Explodierte Vorschau](images/05_vorschau-explodiert.jpg)

## Druck-Erfahrungen und Empfehlungen

Die Sets sind für den **Bambu Lab H2C** in **ASA** (Bambu-Profil, 0,20 mm,
2 Wände, 15 % Gitter-Infill) probegeslict. PETG funktioniert ebenfalls; PLA ist
für einen geparkten Camper zu weich. Die Fußblöcke und Schraubfüße drucke ich
mit 0,16 mm, 4 Wänden und langsamen Außenwänden. Ist das Gewinde zu streng,
erhöhst du `thread_clear` von 0,35 auf 0,45. Alle Teile liegen druckfertig und
brauchen keine Stützen. Für einen 256-mm-Drucker verkürzt du die Schalen im
Customizer.

## Einsatzideen

- Camper-Nische neben der Toilette
- Spalt im Bad oder Vorratsschrank
- Einzelschale unter einer Schublade
- Van-Ausbau oder Werkstattregal in einer schrägen Ecke
- Mietwohnung ohne Bohren: `Posts and feet only`

![Set B mit Wabenfront](images/03_set-b-wabenfront.jpg)

## Fazit und Aufruf zum Mitmachen

Das Regal ist ein Baukasten für Nischen, in die sonst nichts passt. Wenn du es
druckst, freue ich mich über **Makes** mit Fotos, besonders mit deinen
Nischenmaßen, schrägen Wänden und anderen Druckern. Rückmeldungen zu den
Schraubfüßen und zum Gewindespiel in ASA oder PETG helfen, die
Voreinstellungen zu verbessern. Schreib einfach einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3464475-parametric-niche-shelf-system

---

## 10 SEO-Titel

1. Regal für schmale Nische 3D-drucken: parametrisch nach Maß (OpenSCAD)
2. Camper-Regal neben der Toilette: Nischenregal aus dem 3D-Drucker
3. Schräge Nische, gerades Regal: Schalen folgen der Wand
4. Regal ohne Bohren: freistehend mit gedruckten Schraubfüßen
5. Höhenverstellbare Füße 3D-drucken: Trapezgewinde ohne Stützen
6. Schlauch verstecken: Abdeckung zum Einschieben für den Lüftungsschlauch
7. Wandwinkel oder Pfosten: fünf Befestigungsarten für dein Regal
8. ASA-Regal für den Camper: hitzefest und druckfertig für Bambu Lab
9. Parametric Niche Shelf System: One Model – Any Niche
10. Regalsystem mit 1 bis 4 Schalen: Maße im Customizer statt Bastelei

## 20 relevante Suchbegriffe

- Nischenregal 3D-Druck
- Camper Regal Toilette
- Wohnmobil Regal schmal
- Regal schmale Nische nach Maß
- Regal Van Ausbau 3D-Druck
- parametrisches Regal OpenSCAD
- Schraubfüße 3D-Druck
- höhenverstellbare Füße drucken
- Bambu Lab H2C ASA Regal
- Eckpfosten Regal gedruckt
- Schlauchabdeckung Camper
- Lüftungsschlauch verstecken
- Wandwinkel 3D-Druck
- Regal ohne Bohren
- Schale mit Rand gegen Herausrutschen
- Wabenmuster Front Regal
- Regal Bad Spalt
- MakerWorld Customizer Regal
- Stauraum Camper selber drucken
- Regal schräge Wand

## 5 LinkedIn-Post-Ideen

1. „Eine Lücke, kein Regal“: Wie aus einer Camper-Nische ein parametrisches
   Regalsystem wurde.
2. „Wenn die Wand schräg ist“: Warum zwei Breitenwerte reichen, damit Schalen,
   Pfosten und Winkel mitgehen.
3. „Füße aus dem Drucker“: Ein Trapezgewinde, das ohne Stützen funktioniert.
4. „Fehlermeldung statt schlechter Geometrie“: Eingabeprüfungen im
   parametrischen Modell.
5. „Ehrlicher Status“: Warum ich ein Modell mit „noch nicht gedruckt“
   veröffentliche und zuerst einen Passungstest empfehle.

## 5 Reddit-Post-Ideen

1. r/functionalprint – „Parametric niche shelf for a camper: trays, posts and
   printed screw feet“ mit dem Hero-Bild.
2. r/openscad – „One parameter pair makes the shelf follow a slanted wall“ ohne
   Quelltext.
3. r/BambuLab – „ASA shelf system sliced for the H2C: two ready sets, 4 plates
   each“.
4. r/vandwellers bzw. r/Camper – „Printed a shelf for the gap next to the
   toilet“ (nur wenn das Forum Selbstvorstellungen erlaubt).
5. r/3Dprinting – „Printed trapezoid thread feet: what thread clearance works
   for you?“ als Diskussionsfrage.
