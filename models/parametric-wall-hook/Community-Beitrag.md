# Klappbaren Wandhaken 3D-drucken: parametrisch, mit Stift-Scharnier und Dekorschale

👉 **MakerWorld-Link:** <https://makerworld.com/en/models/3056446-parametric-foldable-wall-hook> – Profil:
<https://makerworld.com/en/@BetaHydri>

![Die vier Teile des Wandhakens](images/01_hero.png)

## Motivation: Der Haken, der nur bei Bedarf da ist

Ein Haken, der geschlossen bündig in der Wand sitzt und nur bei Bedarf
herausklappt, ist praktisch – im Flur, im Bad, im Wohnmobil. Gedruckt ist er
aber tückisch: Scharnier-Spalt, Anschlag, Haltekraft und Druckorientierung
greifen ineinander. Ich wollte ein Modell, das ich in Breite, Länge und Optik
anpassen kann und das trotzdem ohne Support aus dem Drucker kommt. Der
**Parametric Foldable Wall Hook** besteht deshalb aus vier getrennten Teilen und
läuft im MakerWorld-Customizer.

## Funktionen im Überblick

- **Vier Teile:** Haken (Arm), Gehäuse, Stift und Außenschale – alle ohne Support.
- **Lasttragender Stift** (`pin_d`, Standard 4 mm), von der Außenschale gesichert.
- **Harter Ausklapp-Anschlag:** eine Ferse trifft bei `max_open_angle` flächig auf
  die massive Rückwand.
- **Bündiger, einrastender Sitz:** seitliche Einrast-Noppen und oberer Halte-Steg,
  beide mit einstellbarer Haltekraft.
- **Bügel-Sattelkerben** (45°-V-Nuten) und **Griff-Fingermulde**.
- **Relief auf der Schale:** Rillen, Ringe, Punkte oder Rautung.
- **Montage** per Klebeband oder Senkkopf-Schrauben.
- **Drei Referenzvarianten** für den Bambu Lab P2S.

![Außenschale mit Rautung-Relief](images/02_relief-rautung.png)

## Entwicklungsprozess

Am 13. Juli 2026 stand ein Klapphaken aus einer druckbaren Einheit (Rahmen und
Haken Print-in-Place) mit Dekorschale. Der Scharnierspalt war die Quelle fast
aller Probleme:

- Die Sattelkerben liegen im Gebrauch auf der Innenseite des Arms, im Druck
  aber unten über dem Scharnierspalt – das ergab Spaghetti.
- In der Variante mit eingeknipstem Lager wanderte der Haken beim Ausklappen aus
  der Lagerschale nach vorn. Der Drehpunkt rutschte, die Ferse verfehlte die
  Rückwand, der Anschlag fehlte.
- Der Anschlag war zunächst ein dünner Lappen, der sich unter Last wegbog.

Am 14. Juli folgte die Entscheidung für einen **separaten Stift**: Der Arm hat eine
Durchbohrung, der Stift wird durch beide Gehäusewände gesteckt, die Außenschale
verdeckt die Enden. Der Arm wird flach und getrennt gedruckt, es gibt keinen
Spalt darunter. Am 15. Juli kamen die Einrast-Noppen und der obere Halte-Steg
dazu, am 5. August 2026 die drei Referenzvarianten.

## Technische Hintergründe

**Kinematik.** Der Drehpunkt liegt unten, der Haken klappt oben zu und nach vorn
aus. Eine anhängende Last drückt den Arm in den Anschlag statt ihn zuzuklappen.
Weil die Spitze beim Öffnen nach vorn und unten wandert, kann nichts oben den Arm
am Aufklappen hindern; den eigentlichen Halt im geschlossenen Zustand liefert der
seitliche Einrast-Noppen, der obere Steg sorgt für den bündigen Sitz und einen
sanften Klick.

**Ferse als Keil.** Die hintere Keilfläche liegt nach der Drehung um den
Öffnungswinkel flächig in der Rückwandebene. Die Fersenlänge ergibt sich aus
(Barrel-Radius + `hinge_gap` + `pin_play` + 0,2) / sin(`max_open_angle`), mit
den Standardwerten rund 5,5 mm. Der Keil endet genau an dieser Fläche und
klemmt deshalb nicht früher.

**Seitliche Noppe.** Der Arm dreht um die X-Achse, daher biegt sich der Arm nicht
in X. Stattdessen federt die Gehäusewand beim Schließen auf, wenn die
Arm-Seitenfläche an der Noppe vorbeifährt. Die Mulde im Arm sitzt exakt auf dem
Noppenmittelpunkt, es gibt einen definierten Klick ohne Dauerspannung.

**Schwenkbahn.** Der Freischnitt der Hakenbahn ist ein einmal extrudiertes
2D-Profil. Die erste Version vereinte rund 15 gedrehte 3D-Körper, deren
Deckflächen auf einer Ebene lagen; das erzeugte nicht-manifolde Kanten im Gehäuse,
die Bambu Studio meldete.

**Stift.** Er wird stehend gedruckt: Jede Schicht ist ein Kreis, das ergibt den
präzisesten Rundquerschnitt. Der Preis ist, dass die Schichten quer zur Last
liegen; bei einem 4-mm-Vollstift ist das unkritisch, und im Slicer lässt er sich
bei Bedarf umlegen.

![Außenschale mit Punkte-Relief](images/03_relief-punkte.png)

## Druck-Erfahrungen und Empfehlungen

Die Profile sind für den **P2S** mit **PETG-CF** erstellt und im Slicer getestet:
0,20 mm Layerhöhe, 3 Wände, 15 % Gyroid. Für den tragenden Haken und den Stift
sind 4 Wände und mehr Infill sinnvoll. Der Haken liegt flach mit der Vorderseite
nach oben, Gehäuse und Schale mit der Rückwand auf dem Bett, der Stift steht mit
Brim.

Die Profile enthalten alle vier Teile als ein Objekt: In Bambu Studio
rechtsklicken und „In Objekte aufteilen“ wählen. Zusammenbau: Haken ins Gehäuse,
Stift seitlich durchstecken, die Baugruppe von vorn in die Schale drücken.

Zu schwergängig? `pin_play` erhöhen. Stift klemmt beim Durchstecken? `holder_pin_clear`
erhöhen. Haken zu schwer zu öffnen? `detent_grip` und `top_seat_grip` verkleinern.

## Einsatzideen

- Handtuchhaken im Bad
- Platzsparender Jackenhaken im Flur
- Beutel- und Taschenhaken in Werkstatt oder Büro
- Bügelhalter mit Sattelkerben
- Haken im Wohnmobil, der beim Fahren geschlossen bleibt

![Hero: Gehäuse, Haken, Außenschale mit Rillen und Stift](images/01_hero.png)

## Fazit und Aufruf zum Mitmachen

Der Wandhaken ist ein Baukasten: Maße, Haltekräfte und Optik lassen sich einstellen,
ohne die Mechanik neu zu bauen. Wenn du ihn druckst, freue ich mich über **Makes**
mit Fotos. Rückmeldungen zu Lagerspiel und Haltekräften auf anderen Druckern helfen,
die Voreinstellungen zu verbessern. Schreib einfach einen Kommentar auf MakerWorld.

👉 **MakerWorld-Link:** <https://makerworld.com/en/models/3056446-parametric-foldable-wall-hook>

---

## 10 SEO-Titel

1. Klappbaren Wandhaken 3D-drucken: parametrisch mit Stift-Scharnier
2. Wandhaken ohne Support drucken: vier Teile, alle flach
3. Parametric Foldable Wall Hook für Bambu Lab: Maße und Relief im Customizer
4. Handtuchhaken 3D-Druck: klappbar, bündig und einrastend
5. Klapphaken konstruieren: Anschlag, Ferse und Stift richtig auslegen
6. Wandhaken mit Dekorschale: Rillen, Ringe, Punkte oder Rautung
7. Gedrucktes Scharnier mit separatem Stift statt Print-in-Place
8. Wandhaken für Bad, Flur und Wohnmobil 3D-drucken
9. Foldable Wall Hook 3D Print: Detent Click and Hard Stop
10. Einrast-Noppen im 3D-Druck: bündiger Sitz ohne Dauerspannung

## 20 relevante Suchbegriffe

- Wandhaken 3D-Druck
- Klapphaken 3D drucken
- klappbarer Haken 3D-Druck
- Handtuchhaken 3D-Druck
- Jackenhaken 3D-Druck
- parametrischer Wandhaken OpenSCAD
- Foldable wall hook 3D print
- Fold out hook
- Flip out hook 3D print
- Scharnier mit Stift 3D-Druck
- Print in place Scharnier Probleme
- Einrast-Noppe 3D-Druck
- Haken ohne Support drucken
- Wandhaken Wohnmobil
- Bügelhalter 3D-Druck
- PETG-CF Haken
- Bambu Lab P2S Haken
- MakerWorld Wandhaken
- Customizer Wandhaken
- funktionale 3D-Drucke

## 10 GitHub-Tags

- wall-hook
- foldable
- parametric
- openscad
- 3d-printing
- bambu-lab
- makerworld
- customizer
- no-supports
- functional-print

## 5 LinkedIn-Post-Ideen

1. „Warum der Haken aus dem Lager wanderte“: Fehleranalyse eines eingeknipsten
   Gelenks und die Lösung mit separatem Stift.
2. „Ein Fehler, der eine Zeile braucht“: nicht-manifolde Kanten durch vereinte
   gedrehte Körper, gelöst mit einem einmal extrudierten 2D-Profil.
3. „Klick ohne Dauerspannung“: Wie eine Noppe und eine Mulde im geschlossenen
   Zustand exakt aufeinander liegen.
4. „Druckorientierung als Entwurfsparameter“: Warum der Arm flach und der Stift
   stehend gedruckt wird.
5. „Vom Print-in-Place zum Mehrteiler“: Wann ein Gelenk besser aus getrennten Teilen
   besteht.

## 5 Reddit-Post-Ideen

1. r/functionalprint – „Foldable wall hook with a separate load-bearing pin, four
   parts, no supports“ mit dem Hero-Bild.
2. r/3Dprinting – „Why my print-in-place hook failed and how a separate pin fixed
   it“.
3. r/openscad – „Sweeping a cutter: one 2D fan extruded once instead of many
   rotated solids“ (ohne Quelltext, nur Ansatz).
4. r/BambuLab – „Four-part hook on one plate: split to objects in Bambu Studio“.
5. r/3Dprinting – „How much detent force feels right for a closed hook? 0.15 vs
   0.30 mm“ als Diskussionsfrage.
