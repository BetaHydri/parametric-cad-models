# Parametric Picture Frames – Any Size, Any Shape, Five Profiles, Snap Keys, No Glue

[← All models](../../README.md)

🌐 **English** | [Deutsch](README.de.md)

Print a picture frame **exactly as big and as shaped as your picture**: a photo,
a poster, a hexagon, a diamond. The frame is made from **mitred strips** held
together by small printed **snap keys on the back**: no glue, nothing visible from
the front, and you can take the frame apart again. Glass, photo and back board
are held by **spring prongs** you can pull out to change the picture.

[![MakerWorld](https://img.shields.io/badge/MakerWorld-Model-00AE42)](https://makerworld.com/en/models/3551154-parametric-picture-frame#profileId-4062778)
![OpenSCAD](https://img.shields.io/badge/OpenSCAD-parametric-yellow)
![Bambu Lab](https://img.shields.io/badge/Bambu%20Lab-P2S-green)
![Print files](https://img.shields.io/badge/Print%20files-MakerWorld%20only-blue)

> **The model with all print profiles is available exclusively on MakerWorld:**
> 👉 [MakerWorld link: https://makerworld.com/en/models/3551154-parametric-picture-frame](https://makerworld.com/en/models/3551154-parametric-picture-frame#profileId-4062778)
>
> ![Parametric Picture Frames: six frames in different shapes and profiles](images/01_hero.jpg)

## Table of Contents

- [Highlights](#highlights)
- [The profiles](#the-profiles)
- [The joint](#the-joint)
- [Parametric Options](#parametric-options)
- [Samples](#samples)
- [Print Recommendations](#print-recommendations)
- [Assembly](#assembly)
- [What was checked](#what-was-checked)
- [Downloads](#downloads)
- [License](#license)

## Highlights

- **Pick the picture, get the frame.** Standard sizes from 9 x 13 cm to A3 in a
  dropdown, or type any size. Or choose a **regular polygon with 3 to 12 sides**
  or a **rhombus** with any angle: every corner gets its own mitre angle
  automatically.
- **Five profiles.** Flat, bevel, half-round, steps (cassette) and cove. Width
  20 to 70 mm, depth 14 to 50 mm, lip 2 to 10 mm.
- **Joints without glue.** The back of every mitre has one pocket in each
  strip. A flat **snap key** (two split-ring heads on a bar) is pressed into
  both pockets from behind: a small bead on each head **clicks into a groove**
  at the bottom of the pocket. The key is printed lying flat, so its layers
  run along the pull of the joint and nothing stands up in the air while
  printing. Nothing is visible from the front, and a thin screwdriver in the
  round relief at the joint levers the key out again. The **key fit** setting
  tunes the grip to your printer.
- **As few pieces as possible.** The picture sets the inner size; the outer
  length of a strip (opening + 2 x frame width) must fit the bed. A strip longer
  than the bed is printed **diagonally** (up to about 1.4 times the bed length,
  about 320 mm on a 256 mm bed), so a **135 x 240 mm** frame needs only **4
  strips**, not 6. The strips lie side by side across the diagonal of the bed,
  the longest in the middle, and shorter strips fill the free places beside
  them: on a 256 mm bed the whole 135 x 240 mm frame fits on **one plate**
  (plus one for keys and prongs). Only sides that are longer still are split, into equal
  pieces with keys at the butt joints: an **A4 frame** prints on a 256 mm bed.
  Switch `diag strips` off if you prefer every strip to lie straight.
- **Glass, photo, back board.** The rabbet is as deep as your stack (glass 0 to
  6 mm, photo, board 1.5 to 8 mm) plus room for the prongs. No board? Print a
  **back plate** (if it fits the bed).
- **Change the picture any time.** The **flat spring prongs** are pushed
  straight into slots in the rabbet wall (root first) and their arm presses the
  stack forward. Pull them straight out, swap the picture, push them back in.
  The number of prongs follows the weight of the stack.
- **Hang it.** Two **keyholes** in the top strip (rectangles and polygons with a
  flat top).
- **Prints without support.** Every strip lies with its back on the bed. The lip
  that holds the picture has a **45° chamfer underneath** that runs on to the
  rabbet wall: it touches the glass only along the edge of the picture, and
  there is no flat ledge anywhere. The frame gets deeper for that: at its
  thinnest point by about the lip width minus 1 mm.
- **Foolproof.** If a setting cannot work (frame too narrow for the keys,
  frame too shallow for the stack, a strip wider than the bed, an opening that
  is too small) **a red message replaces the model**, so you can never download
  a broken part by accident.

![Hero 3:4: frames in many shapes on a wooden table](images/02_hero-hochformat.jpg)

## The profiles

| Profile | Look | Good for |
|---|---|---|
| Flat | rectangular strip | modern, slim frames, photos 10 x 15 |
| Bevel | slopes down to the picture | the classic photo frame |
| Half-round | rounded top | soft, friendly frames, polygons |
| Steps | cassette with two steps | posters, art prints, A4 |
| Cove | hollow groove | diamonds and wide frames |

## The joint

| | Snap key |
|---|---|
| **How it holds** | two split-ring heads with a small bead snap into grooves at the bottom of the pockets; a rigid bar joins them |
| **Print position** | the key lies flat: layers run along the pull, no support, no free-standing parts |
| **Fit** | `key fit` 0 to 0.15 mm: lower = tighter. The optional test corner (switch it on in the Customizer) prints three fits in one go and shows how the key fits your printer |
| **Take apart again** | lever the key out with a thin screwdriver in the round relief at the joint |
| **Spares** | 2 extra keys are printed (more in the Customizer) |

Choose **None** to glue the mitres instead.

![The snap keys on the back of the frame](images/09_rueckseite-schluessel.jpg)

![Section through the frame: the lip has a 45° chamfer underneath](images/11_schnitt-lippe-fase.jpg)

## Parametric Options

| Group | Options |
|---|---|
| Picture and outline | Rectangle (standard sizes or custom up to 600 mm), regular polygon (3 to 12 sides, side 20 to 300 mm) or rhombus (side and angle 30 to 85°) |
| Frame profile | Profile, frame width, depth and lip (the frame gets about the lip width minus 1 mm deeper at its thinnest point) |
| Picture stack and back | Thickness of glass, photo and back board, clearance (0.2 to 1 mm), own board or printed back plate, prongs on or off, keyholes on or off |
| Joints | Snap key or none; key thickness, key fit, number of spare keys, test corner (off by default: adds a first plate with three key fits) |
| Printer and colours | Long strips diagonal (on by default), bed size (pick **the same printer in the MakerWorld bed menu**), frame colour and key colour; the view menu shows the assembled frame, the back or the exploded view |

A Customizer download is a set of plates: the strips first, the keys and
prongs on the last plate. With `test corner` switched on, the test corner is
the first plate.

![Exploded view of an octagon frame](images/10_explosionsansicht.jpg)

## Samples

Ready-to-print Bambu profiles (**PETG, P2S**, 0.20 mm, 3 walls, 15 % gyroid,
test-sliced) are available on MakerWorld, every plate in one 3MF: first the
strip plates, then a plate with the snap keys and prongs.

| Sample | Picture | Profile | Joint | Parts | Time / weight |
|---|---|---|---|---|---|
| ![Photo frame 13 x 18 cm](images/03_foto-13x18-fase.jpg) **Photo frame 13 x 18 cm** | 130 x 180 mm | bevel | Snap key | 4 strips, 6 snap keys, 8 prongs | 4.5 h / 132 g (2 plates) |
| ![Photo frame 10 x 15 cm](images/04_foto-10x15-flach.jpg) **Photo frame 10 x 15 cm, flat profile** | 100 x 150 mm | flat | Snap key | 4 strips, 6 snap keys, 5 prongs | 3.2 h / 101 g (2 plates) |
| ![A4 poster frame](images/05_a4-kassette.jpg) **A4 poster frame, split sides** | 210 x 297 mm | steps (cassette) | Snap key | 6 strips, 8 snap keys, 10 prongs | 8.0 h / 255 g (3 plates) |
| ![Hexagon frame](images/06_sechseck-halbrund.jpg) **Hexagon frame** | regular 6-gon, side 70 mm | half-round | Snap key | 6 strips, 8 snap keys, 5 prongs | 3.8 h / 104 g (2 plates) |
| ![Diamond frame](images/07_raute-hohlkehle.jpg) **Diamond frame** | rhombus, side 90 mm, angle 60° | cove | Snap key | 4 strips, 6 snap keys, 8 prongs | 4.6 h / 134 g (2 plates) |
| ![Octagon frame](images/08_achteck-fase.jpg) **Octagon frame** | regular 8-gon, side 60 mm | bevel | Snap key | 8 strips, 10 snap keys, 7 prongs | 4.0 h / 108 g (3 plates) |

Print any other size or shape with the Customizer.

## Print Recommendations

| Setting | Recommendation |
|---|---|
| Printer | Bambu Lab P2S (the samples), P1S and any printer with a 256 mm bed; pick the printer in the MakerWorld bed menu |
| Filament | **PETG** for everything (ASA or PLA work too). The **keys** should be PETG (stiff, they must snap); the **prongs** can also be printed in **TPU 95A**, which is softer |
| Layer height / walls | 0.20 mm, 3 walls |
| Infill | 15 % gyroid |
| Support / brim | none (leave support off: the lip has a 45° chamfer) |
| Pose | Strips lie with their back on the bed, keys and prongs lie flat |
| Accuracy | The key snaps by a few tenths of a millimetre, so it depends on your printer. Switch `test corner` on and print it first (three fits at once). If the key is hard to press in, raise `key fit` by 0.05; if it falls out, lower it by 0.05 |

> **Status:** the geometry is checked on the real exported meshes and every
> sample is test-sliced in Bambu Studio. **Not printed yet in this version.**
> The first version had round pegs and prongs with a round head; on the first
> real print the pegs tore off, and the prongs did not fit their holes and
> gave no spring force, so joint and prongs were **redesigned**. A **test
> corner** (three key fits) is optional: switch `test corner` on in the
> Customizer (Joints) and it becomes the first plate.

## Assembly

1. Lay the strips as a ring on the table with the **back up**; the mitres touch.
2. Press a snap key into the two pockets of every joint from behind until its
   beads click and it is flush.
3. Turn the frame **face down** on a soft surface and lay in glass, photo and
   back board.
4. Push every prong, root first, into its slot in the rabbet wall until it
   stops: the arm then lies on the back board and presses the stack forward.
5. Hang it on a screw: the head goes through the round part of the keyhole, then
   slide the frame down.

## What was checked

All checks run on the **real exported meshes** (OpenSCAD, Manifold) in 25 configurations (including 135 x 240 mm on three bed sizes, with and without diagonal strips, a heavy 20 x 30 cm glass stack, narrow and wide lips) of rectangle, triangle, hexagon, octagon, rhombus, split A4, big glass, wide and narrow lip and several key settings, plus 6 deliberately wrong settings that must show the red message: **1598 checks, 0 failed**. The snap-key joint is measured on the meshes too (key head, bead, slit, clearance of every seated key in its pocket at the mouth and in the groove, pocket depth); how firmly it holds under tension can only be shown by a print, so print the optional test corner first.

- **The mitres close:** the area of all strips above the lip chamfer equals outer outline minus opening, and neighbouring strips do not overlap.
- **Rabbet:** equals the picture plus the clearance on every side; the picture fits in.
- **Every strip** is one body, flat on the bed, fits the bed and **prints without support**. The check is strict: a flat ledge hanging out more than about 0.7 mm is a failure (bridges up to 10 mm are fine). The old check let up to about 5.8 mm through and missed the flat front lip, which needed support on a real print.
- **The lip chamfer** is measured on the sections: at every height from the wall corner to the opening the material starts exactly where the 45° line says, so there is no flat step between the chamfer and the rabbet wall (an earlier version had a 1 mm flat band there, which the slicer flagged).
- **No free-standing islands:** every layer of every strip is one connected region. The first version's round pegs were separate columns up to 4.6 mm tall.
- **Walls:** at least 2 mm around every pocket and slot.
- **Keys and prongs** sit in their pockets without touching the frame (overlap volume 0.000 mm³).
- **Snap key:** the head closes by 0.25 mm while the bead is pressed through the pocket mouth, which strains the PETG by about **1.5 %** (2.2 % with the printer 0.1 mm tight; limit 3 %). The slit is wide enough, the bead still catches with the printer 0.1 mm loose, the pocket roof bridges 9.7 mm, the key prints flat without support. The bar is estimated at roughly 300 N tensile (an estimate, not a measurement).
- **Number of prongs:** a heavy stack gets more prongs, so that together they press with at least twice the weight of glass, photo and board (13 x 18 cm: 8 prongs for a 184 g stack; 20 x 30 cm with 4 mm glass: 14 prongs for 906 g).
- **Strips:** a strip longer than the bed lies diagonally (a 284 mm strip needs a 201 x 201 mm field), so a 135 x 240 mm frame has 4 strips, and on a 256 mm bed all 4 lie on one plate (two 284 mm strips in the middle, two 179 mm strips outside); every strip plate is measured: all strips on it are separate, inside the bed and not touching.
- **Prong:** measured on the real meshes: the root slides straight into its slot (the arm and pad touch nothing on the way in), the teeth are pressed in by 0.02 mm² (a press fit), the bent arm stays clear of the wall, and the pad top sits 1.5 mm inside the back board when relaxed, so the stack bends the arm by 1.5 mm. That gives about **1.6 N per prong** (beam model with the measured deflection), bending strain **1.1 %** (1.8 % while the picture is put in). All prongs together press with about 13 N on a 13 x 18 cm stack that weighs about 1.8 N. How the printed prong feels (press fit, stiffness of your PETG) is **not** measured: it depends on your printer.
- **Test corner:** two stubs and a key, flat on the bed, inside the bed.
- **All plates** are inside the bed; each sample is test-sliced and the 3MF reloads in Bambu Studio with Bambu filament only.

**Not checked yet:** how firmly the printed snap key really holds, and how much force it takes to press in and pull out (this depends on your printer's tolerance and cannot be measured from the model). Nothing of this version is printed yet. That is why the first print should be the test corner (switch it on in the Customizer).

## Downloads

Print files are intentionally available exclusively on MakerWorld.

👉 MakerWorld link: https://makerworld.com/en/models/3551154-parametric-picture-frame#profileId-4062778

Profile: <https://makerworld.com/en/@BetaHydri>

## License

Documentation and images in this repository; model and print files are
distributed exclusively via MakerWorld. Documentation and images: © BetaHydri.
The model (including source code) and all print files are under the license
stated on MakerWorld. This repository deliberately contains no model, source
code or print files.
