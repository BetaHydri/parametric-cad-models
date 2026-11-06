# Parametric Picture Frames – Any Size, Any Shape, Five Profiles, Snap Keys, No Glue

[← All models](../../README.md)

🌐 **English** | [Deutsch](README.de.md)

Print a picture frame **exactly as big and as shaped as your picture**: a photo,
a poster, a hexagon, a diamond. The frame is made from **mitred strips** held
together by small printed **snap keys on the back**: no glue, nothing visible from
the front, and you can take the frame apart again. Glass, photo and back board
are held by **flexible prongs** you can pull out to change the picture.

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
- **Big frames in several strips.** Sides longer than the bed minus 14 mm are
  split automatically, and the butt joints get keys too: an **A4 frame** or a
  **poster frame** prints on a 256 mm bed.
- **Glass, photo, back board.** The rabbet is as deep as your stack (glass 0 to
  6 mm, photo, board 1.5 to 8 mm) plus room for the prongs. No board? Print a
  **back plate** (if it fits the bed).
- **Change the picture any time.** The **flexible prongs** slide into small
  windows in the rabbet wall and press the stack forward. Pull them out
  sideways, swap the picture, slide them back.
- **Hang it.** Two **keyholes** in the top strip (rectangles and polygons with a
  flat top).
- **Prints without support.** Every strip lies with its back on the bed. The lip
  that holds the picture has a **45° chamfer underneath** (only a 0.5 mm band
  touches the glass), so nothing hangs in the air: slopes up to 55° and bridges
  up to 10 mm only. The frame gets about the lip width plus 1 mm deeper for it.
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
| **Fit** | `key fit` 0 to 0.15 mm: lower = tighter. The test corner shows in about 30 minutes how the key fits your printer |
| **Take apart again** | lever the key out with a thin screwdriver in the round relief at the joint |
| **Spares** | 2 extra keys are printed (more in the Customizer) |

Choose **None** to glue the mitres instead.

![The snap keys on the back of the frame](images/09_rueckseite-schluessel.jpg)

![Section through the frame: the lip has a 45° chamfer underneath](images/11_schnitt-lippe-fase.jpg)

## Parametric Options

| Group | Options |
|---|---|
| Picture and outline | Rectangle (standard sizes or custom up to 600 mm), regular polygon (3 to 12 sides, side 20 to 300 mm) or rhombus (side and angle 30 to 85°) |
| Frame profile | Profile, frame width, depth and lip (the frame gets about lip + 1 mm deeper at its thinnest point) |
| Picture stack and back | Thickness of glass, photo and back board, clearance (0.2 to 0.5 mm), own board or printed back plate, prongs on or off, keyholes on or off |
| Joints | Snap key or none; key thickness, key fit, number of spare keys, test corner on or off |
| Printer and colours | Bed size (pick **the same printer in the MakerWorld bed menu**), frame colour and key colour; the view menu shows the assembled frame, the back or the exploded view |

A Customizer download is a set of plates: the test corner first, then the
strips, the keys and prongs on the last plate.

![Exploded view of an octagon frame](images/10_explosionsansicht.jpg)

## Samples

Ready-to-print Bambu profiles (**PETG, P2S**, 0.20 mm, 3 walls, 15 % gyroid,
test-sliced) are available on MakerWorld, every plate in one 3MF: first the
test corner, then the strip plates, then a plate with the snap keys and prongs.

| Sample | Picture | Profile | Joint | Parts | Time / weight |
|---|---|---|---|---|---|
| ![Photo frame 13 x 18 cm](images/03_foto-13x18-fase.jpg) **Photo frame 13 x 18 cm** | 130 x 180 mm | bevel | Snap key | 4 strips, 6 snap keys, 8 prongs, test corner | 5.3 h / 148 g (3 plates) |
| ![Photo frame 10 x 15 cm](images/04_foto-10x15-flach.jpg) **Photo frame 10 x 15 cm, flat profile** | 100 x 150 mm | flat | Snap key | 4 strips, 6 snap keys, 5 prongs, test corner | 3.9 h / 117 g (3 plates) |
| ![A4 poster frame](images/05_a4-kassette.jpg) **A4 poster frame, split sides** | 210 x 297 mm | steps (cassette) | Snap key | 8 strips, 10 snap keys, 10 prongs, test corner | 9.0 h / 278 g (4 plates) |
| ![Hexagon frame](images/06_sechseck-halbrund.jpg) **Hexagon frame** | regular 6-gon, side 70 mm | half-round | Snap key | 6 strips, 8 snap keys, 5 prongs, test corner | 4.4 h / 121 g (3 plates) |
| ![Diamond frame](images/07_raute-hohlkehle.jpg) **Diamond frame** | rhombus, side 90 mm, angle 60° | cove | Snap key | 4 strips, 6 snap keys, 8 prongs, test corner | 5.5 h / 156 g (3 plates) |
| ![Octagon frame](images/08_achteck-fase.jpg) **Octagon frame** | regular 8-gon, side 60 mm | bevel | Snap key | 8 strips, 10 snap keys, 7 prongs, test corner | 4.8 h / 126 g (4 plates) |

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
| Accuracy | The key snaps by a few tenths of a millimetre, so it depends on your printer. Print the **test corner** first. If the key is hard to press in, raise `key fit` by 0.05; if it falls out, lower it by 0.05 |

> **Status:** the geometry is checked on the real exported meshes and every
> sample is test-sliced in Bambu Studio. **Not printed yet in this version.**
> The first version had round pegs on the back of the strips; on the first
> real print they tore off (each peg was a free-standing column), so the joint
> was **redesigned**. The first plate of every download is a **test corner**
> (two short strip stubs and a key): print it before a whole frame.

## Assembly

1. Lay the strips as a ring on the table with the **back up**; the mitres touch.
2. Press a snap key into the two pockets of every joint from behind until its
   beads click and it is flush.
3. Turn the frame **face down** on a soft surface and lay in glass, photo and
   back board.
4. Slide every prong into its window, the pad of the arm pressed flat onto the
   board.
5. Hang it on a screw: the head goes through the round part of the keyhole, then
   slide the frame down.

## What was checked

All checks run on the **real exported meshes** (OpenSCAD, Manifold) in 16
configurations of rectangle, triangle, hexagon, octagon, rhombus, split A4,
big glass, wide and narrow lip and several key settings, plus 6 deliberately
wrong settings that must show the red message: **951 checks, 0 failed**.

- **The mitres close:** the area of all strips above the lip chamfer equals the
  outer outline minus the opening, and neighbouring strips do not overlap.
- **Rabbet:** equals the picture plus the clearance on every side.
- **Every strip** is one body, lies flat on the bed, fits the bed and **prints
  without support**. The check is strict: a flat ledge hanging out more than
  about 1 mm fails (bridges up to 10 mm are fine). The earlier check let up to
  about 5.8 mm through and missed the flat front lip, which needed support on a
  real print.
- **The lip chamfer** is measured on the sections: at every height the material
  starts exactly where the 45° line says.
- **No free-standing islands:** every layer of every strip is one connected
  region. The first version's round pegs were separate columns up to 4.6 mm
  tall.
- **Walls:** at least 2 mm around every pocket and window.
- **Keys and prongs** sit in their pockets without touching the frame (overlap
  volume 0.000 mm³).
- **Snap key:** the head closes by 0.25 mm while the bead is pressed through the
  pocket mouth, which strains the PETG by about **1.5 %** (2.2 % with the printer
  0.1 mm tight; limit 3 %). The bead still catches with the printer 0.1 mm
  loose, and the key prints flat without support. The bar is estimated at
  roughly 300 N tensile (an estimate, not a measurement).
- **Prong:** about **1.7 N** on the stack for 1.5 mm deflection, bending strain
  while sliding in **1.8 %**.
- **All plates** are inside the bed; each sample is test-sliced and the 3MF
  reloads in Bambu Studio with Bambu filament only.

**Not checked yet:** how firmly the printed snap key really holds and how much
force it takes to press in and pull out; this depends on your printer's
tolerance. Nothing of this version is printed yet.

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
