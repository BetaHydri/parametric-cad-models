# Möbelgriffe parametrisch drucken: Der Furniture Handle Generator für Bambu Lab

👉 **MakerWorld-Link:** https://makerworld.com/en/models/3181516-ultimate-parametric-furniture-handles – Profil:
<https://makerworld.com/en/@BetaHydri>

![Parametric Furniture Handle Generator – Griffe in mehreren Farben](images/01_hero.jpg)

## Motivation: Ein Griff, der zu deinen Löchern passt

Wer Schubladen, Schranktüren oder Klappen nachrüstet, kennt das Problem: Die
Bohrungen sind da, der Abstand beträgt zum Beispiel 96 oder 128 Millimeter, und
ein gekaufter Griff passt oft nicht dazu. Beim Selbstdruck kommt eine zweite
Frage hinzu: Wie wird der
Griff befestigt? Gedrucktes Gewinde, Mutter, Einsatz oder Kunststoffschraube
brauchen jeweils andere Aussparungen.

Der **Parametric Furniture Handle Generator** löst beides mit Parametern. Eine
OpenSCAD-Datei erzeugt sechs Bauformen, jede übliche Schraubenaufnahme von M2
bis M8 und auf Wunsch eine zweite Farbe. Alles stellst du im
MakerWorld-Customizer ein, ohne CAD-Software.

## Funktionen im Überblick

- **Sechs Bauformen:** Bügelgriff (`bar_handle`), D-Griff (`bow_handle`),
  Rundgriff auf Füßen (`bar_pull`), T-Griff (`t_bar`), Knopf (`knob`) und
  Kantengriff (`edge_pull`).
- **Sechs Schraubaufnahmen:** gedrucktes Gewinde, selbstschneidende
  Kunststoffschraube, Sechskant- und Vierkantmutter, Heat-Set-Einsatz,
  Durchgangsloch. Standard ist M4.
- **Lochabstände von 16 bis 320 mm** als Voreinstellung, dazu ein freier Wert
  (`hole_center_custom`).
- **Zweifarbig ohne AMS:** Die dekorierte Front ist ein separates Teil, das
  auf die Basis geclipst wird. Kein Farbwechsel im Druck, kein Purge-Turm.
- **Oberflächenrelief:** Längsrillen, Diamant-Rändelung, Ringe oder Facetten
  mit rundem, rechteckigem oder V-förmigem Profil.
- **Zehn Beispielvarianten** mit Bambu-Studio-Profilen für P1S und PLA.

![Bügelgriff mit Längsrillen an einer Holzschublade](images/02_bar-handle-flutes.jpg)

## Entwicklungsprozess

Das Projekt begann im August 2026. Die Rillenprofile übernimmt der Generator
vom parametrischen Gefäß derselben Modellreihe.

Die wichtigste Entscheidung betraf die zweite Farbe. Die erste Version war eine
Kappe, die von außen über den Bügel greift. Sie funktionierte, stand aber als
Kante auf dem Griff. Bei einem Bauteil, das täglich angefasst wird, ist das
störend. Die Lösung war ein **bündiger Inlay-Sitz**: Die Griffoberseite wird
um die Abdeckungsdicke ausgespart, die Abdeckung rastet in eine
Schnapp-Nut und schließt auf gleicher Höhe ab. Nach dem Zusammenstecken wirken
Basis und Abdeckung wie ein Teil. Die Kappe bleibt als Alternative erhalten
(`cover_style = clip_over`).

## Technische Hintergründe

**Aufnahme per Maßtabelle.** Für jede Schraubengröße steht eine Tabelle mit
Gewindesteigung, Durchgangsloch, Mutter-Schlüsselweite, Mutterdicke sowie
Heat-Set-Durchmesser und -Länge im Modell. Bei M4 sind das beispielsweise
0,7 mm Steigung, 4,5 mm Durchgangsloch, 7 mm Schlüsselweite und ein Einsatz mit
5,6 mm Durchmesser und 8,1 mm Länge. Das Gewinde wird als einzelner
dreieckiger Gang per Verdrehextrusion erzeugt, was die Vorschau schnell und die
Körper geschlossen hält.

**Querschnittslogik für die Abdeckung.** Basis und Abdeckung entstehen aus
2D-Querschnitten mit Offsets: Außenkontur, Sitz (Kontur minus Wand minus Spiel)
und Innenkontur. Dieselbe Logik gilt für runde, abgerundet-rechteckige und
rechteckige Griffe. Die Schnapp-Nut folgt der Kontur als Offset-Ring. Eine
frühere Version mit festen Keilkoordinaten riss runde Basen auf und war nicht
manifold.

**Schutz vor Fehlkonfiguration.** Der Generator prüft, ob die Schraubenaufnahme
in den Fuß passt (Umkreis plus 1 mm Restwand), und gibt sonst eine
Konsolenwarnung aus. Beim D-Griff ist die Schraubtiefe auf den geraden
Schenkelabschnitt begrenzt, weil die Bohrung sonst seitlich aus dem
gekrümmten Schenkel bricht. Das Relief ist auf gerade Griffe beschränkt: Auf
D-Griff, Knopf und Kantengriff erzeugte es lose Reststücke.

## Druck-Erfahrungen

Die Beispielprofile sind für **Bambu Lab P1S** mit PLA Basic erstellt: 0,2 mm
Layer, drei Wände, Gyroid 30 % Infill. Ein Griff ist ein Lastteil, daher
liegt der Infill höher als bei Dekoteilen.

Die Orientierung ist je Bauform eingebaut:

- Gerade Basis (`rounded` oder `rect`): Grifffläche unten, Schraubpfosten
  oben, normalerweise ohne Stützen.
- Die Abdeckung im Inlay-Modus steht auf der Stirnseite und braucht Brim oder
  Raft.
- Runde Griffe haben nur Linienkontakt mit dem Bett und brauchen Stützen vom
  Druckbett aus plus 5 bis 8 mm Brim.
- Der D-Griff braucht Stützen unter der langen oberen Spanne, der Knopf keine.

Praktischer Tipp: Beim ersten Griff mit `print_single` einen
einfarbigen Test drucken und die Passung der Schraube prüfen, bevor der
Zweifarb-Satz folgt. Beim gedruckten Gewinde lässt sich das Spiel über
`thread_clear` (Standard 0,25 mm) nachjustieren.

![D-Griff in Salbeigrün an einer Holzschublade](images/03_d-handle.jpg)

## Fazit und Aufforderung

Mit dem Generator druckst du Möbelgriffe, die zu deinem Lochabstand, deiner
Schraube und deinem Geschmack passen – einfarbig oder mit klickbarer
Zweitfarbe. Das Modell mit allen Profilen gibt es auf MakerWorld:
https://makerworld.com/en/models/3181516-ultimate-parametric-furniture-handles.

Poste deine **Makes** dort in den Kommentaren, zeig die Griffe an deinen Möbeln
und schreib, welche Kombination aus Bauform, Aufnahme und Relief bei dir
funktioniert hat. Rückmeldungen zu Passung und Druckerprofilen helfen,
Standardwerte und Beispielvarianten zu verbessern.

## 10 SEO-Titel

1. Möbelgriffe 3D drucken: Parametrischer Griff-Generator für Bambu Lab
2. Schubladengriff selbst drucken: 6 Bauformen, jeder Lochabstand
3. 3D-gedruckte Möbelgriffe mit gedrucktem Gewinde – ohne Zukaufteile
4. Zweifarbige Griffe ohne AMS: Clip-Abdeckung für den 3D-Drucker
5. Parametrischer Möbelgriff in OpenSCAD: M2 bis M8, Heat-Set, Mutter, Gewinde
6. Küchengriffe nachrüsten: Lochabstand 96, 128, 160 mm im Customizer einstellen
7. Möbelgriff 3D-Druck: Knopf, D-Griff, T-Griff und Kantengriff in einer Datei
8. Bambu Lab P1S: Funktionale Möbelgriffe in PLA mit Gyroid-Infill
9. Griffe mit Rillen, Rändelung und Facetten: Relief-Generator für den 3D-Druck
10. Griff-Generator für MakerWorld: Bügelgriff, Rundgriff, Kantengriff

## 20 Suchbegriffe

1. Möbelgriff 3D Druck
2. Schubladengriff selbst drucken
3. parametrischer Griff OpenSCAD
4. Möbelgriff Lochabstand 128 mm
5. Möbelgriff Lochabstand 96 mm
6. Möbelgriff Lochabstand 160 mm
7. 3D gedruckter Türgriff
8. Heat-Set-Einsatz Griff
9. gedrucktes Gewinde M4
10. selbstschneidende Kunststoffschraube Griff
11. Zweifarbiger Griff ohne AMS
12. MakerWorld Customizer Möbelgriff
13. Bambu Lab P1S Möbelgriff
14. D-Griff 3D Druck
15. T-Griff Schrank 3D Druck
16. Schrankknopf 3D Druck
17. Kantengriff Fingermulde
18. Küchengriffe nachrüsten
19. Griff Generator Customizer
20. funktionale 3D-Drucke Haushalt

## 10 GitHub-Tags

- `parametric`
- `openscad`
- `furniture-handle`
- `drawer-pull`
- `3d-printing`
- `bambu-lab`
- `makerworld`
- `customizer`
- `functional-print`
- `diy`

## 5 LinkedIn-Post-Ideen

1. **Von der Bohrung zum Griff:** Wie ein Parameter-Generator den Lochabstand
   (96, 128, 160 mm) zur Eingabe statt zur Einschränkung macht.
2. **Design-Entscheidung:** Warum die bündige Inlay-Abdeckung die aufgesetzte
   Kappe ablöste – ein Beispiel für nutzerorientiertes Design bei einem
   Alltagsprodukt.
3. **Constraint-Prüfung im Modell:** Wie Schutzprüfungen (Schraubenaufnahme
   zu groß, Bohrung bricht am Schenkel aus) Fehlkonfigurationen schon im
   Customizer abfangen.
4. **Zweifarbig ohne Multimaterial:** Struktur und Dekor trennen, zwei Teile
   einfarbig drucken, zusammenstecken – weniger Abfall, einfachere Workflows.
5. **Was ein Schraubentabellen-Modell lehrt:** Normteile (M2 bis M8) als Daten
   statt als Handarbeit; Parallelen zu Konfigurations-Management in der IT.

## 5 Reddit-Post-Ideen

1. **r/3Dprinting:** „Parametric furniture handles with printed M4 threads – six
   designs, any hole spacing“ mit Fotos der montierten Griffe.
2. **r/BambuLab:** Zweifarbige Griffe auf P1S ohne AMS-Wechsel dank
   Clip-Abdeckung; Profil, Infill und Orientierung als Kurzbericht.
3. **r/openscad:** Offset-Ringe statt fester Keilkoordinaten für eine
   Schnapp-Nut, die runde, abgerundete und eckige Profile abdeckt.
4. **r/functionalprint:** Nachgerüstete Schubladen- und Schrankgriffe als
   Praxisbericht: Heat-Set vs. gedrucktes Gewinde.
5. **r/DIY:** Alte Möbel nachrüsten: So passt du einen gedruckten Griff an
   deinen vorhandenen Lochabstand an.
