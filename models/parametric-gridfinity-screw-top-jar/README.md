# Parametric Gridfinity Screw-Top Jar – Screw-Top Jar for Every Gridfinity Baseplate

[← All models](../../README.md)

🌐 **English** | [Deutsch](README.de.md)

Parametric screw-top jar that fits any standard Gridfinity baseplate: grid from
1×1 to 4×4 cells, height in Gridfinity units, optional magnet pockets and a
labelable cap – all in the MakerWorld Customizer, printable without supports.

[![MakerWorld](https://img.shields.io/badge/MakerWorld-Model-00AE42)](https://makerworld.com/en/models/3434732-parametric-gridfinity-screw-top-jar)
![OpenSCAD](https://img.shields.io/badge/OpenSCAD-parametric-yellow)
![Bambu Lab](https://img.shields.io/badge/Bambu%20Lab-P1S%20%7C%20P2S%20%7C%20H2C-green)
![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-blue)

> The model with all print profiles is available exclusively on MakerWorld:
> 👉 [MakerWorld link: https://makerworld.com/en/models/3434732-parametric-gridfinity-screw-top-jar](https://makerworld.com/en/models/3434732-parametric-gridfinity-screw-top-jar)

![Several screw-top jars in different sizes and colours on a Gridfinity baseplate, with screws beside them](images/01_hero.jpg)

The jar is a proper screw-top container in the Gridfinity system: you choose the
footprint (1×1 to 4×4 cells), the height in units of 7 mm and optionally a cap
text – and print a closable jar that sits flush with every other Gridfinity bin
in the drawer. Screws, beads, spices, SD cards and craft supplies stay where
they belong.

## Table of Contents

- [The Problem](#the-problem)
- [The Idea](#the-idea)
- [Highlights](#highlights)
- [Parametric Options](#parametric-options)
- [Construction](#construction)
- [Variants](#variants)
- [Print Recommendations](#print-recommendations)
- [What Else You Need](#what-else-you-need)
- [Usage Examples](#usage-examples)
- [Troubleshooting / FAQ](#troubleshooting--faq)
- [Development History](#development-history)
- [Downloads](#downloads)
- [License](#license)

## The Problem

Gridfinity organises workshop, drawer and shelf in a 42 mm grid – but for small
parts, a closable container is often missing:

- Open bins let screws and beads jump out as soon as you open the drawer
  abruptly.
- Ready-made screw-top tins do not have the Gridfinity feet and do not fit in
  the baseplate.
- Printed screw threads have overhangs, jam or fit too loosely.
- A jar that is taller or shorter than the neighbouring bins breaks the clean
  look and the stacking height.

## The Idea

The jar stands on a genuine Gridfinity foot according to the public
specification and gets a coarse trapezoidal thread with 45° flanks that prints
without supports. The cap screws on from the outside and stays within the
footprint of the bin. The closed height is always exactly
**units × 7 mm**, just like with normal Gridfinity bins. All dimensions are
millimetres, all values are Customizer parameters.

## Highlights

- **Genuine Gridfinity foot:** 42 mm grid, foot profile 0.8 / 1.8 / 2.15 mm,
  0.5 mm gap between bins (`base_gap`). Fits standard baseplates.
- **Self-supporting thread:** 90° trapezoid with 45° flanks – no overhang in the
  thread. Optionally the ISO 60° thread.
- **Height in Gridfinity units:** closed height = `height_units` × 7 mm. If the
  jar is too low for the thread, the model raises the height automatically.
- **Magnet pockets (optional):** 4 per cell, open at the bottom – for gluing in
  (6.5 × 2.4 mm) or press-fitting (5.9 × 2.0 mm) magnets 6 × 2 mm.
- **Cap label:** text on the cap, in the two-colour variant in the colour of the
  jar.
- **Grip grooves:** vertical grooves on the cap, the number grows with the cap
  size.
- **Baseplate fit test:** small baseplate (1–5 cells per side) for testing the
  fit before you print a large plate.
- **Without supports:** the jar stands on its foot with the opening facing up,
  the cap is printed with the top face down.

![1×1 jar with cap label "M3" next to an open jar on a baseplate](images/02_1x1-schrauben-m3.jpg)

## Parametric Options

The names correspond to the model's Customizer parameters.

### Part Selection

| Parameter | Description | Default | Selection |
|---|---|---|---|
| part | Which part is generated | Preview open | Preview assembled (cap on, view only), Preview open (cap beside it, view only), jar + cap (print), two-colour 2 colours (print), jar only, cap only, baseplate fit test (print) |

The two preview views are for display only and not for printing.

### Gridfinity Footprint

| Parameter | Description | Default | Range |
|---|---|---|---|
| grid_size | Footprint in cells (N × N, 42 mm each) | 1 | 1–4 |
| height_units | Closed height in units of 7 mm | 7 | 4–15 |
| base_gap | Gap between adjacent bins (0.5 = standard) | 0.5 | 0.3–0.8 mm, step 0.05 |
| magnets | Magnet pockets in the base | none | None, pockets 6.5 × 2.4 mm (glue in), press-fit pockets 5.9 × 2.0 mm |

### Walls and Floor

| Parameter | Description | Default | Range |
|---|---|---|---|
| wall | Wall thickness of the jar, at least 2.0 | 2.4 | 2.0–6.0 mm, step 0.1 |
| floor_z | Height of the inner floor above the bed; raised automatically above magnet pockets | 3.4 | 2.6–8.0 mm, step 0.2 |

### Thread and Cap

| Parameter | Description | Default | Range |
|---|---|---|---|
| thread_style | Thread form | trap90 | Trapezoid 90° (self-supporting), ISO 60° |
| thread_depth | Thread depth of the trapezoid form | 1.0 | 0.6–1.4 mm, step 0.1 |
| thread_pitch | Pitch; coarse = easy to screw by hand | 2.8 | 1.5–4.0 mm, step 0.1 |
| thread_turns | Number of thread turns | 3 | 2–6, step 0.5 |
| thread_slop | Print clearance between jar and cap thread | 0.12 | 0.05–0.30 mm, step 0.01 |
| lid_tolerance | Additional diameter in the cap thread | 0.1 | 0–1.0 mm, step 0.05 |
| cap_wall | Wall thickness of the cap around the thread | 2.2 | 1.6–6.0 mm, step 0.2 |
| cap_top | Thickness of the cap top face | 2.4 | 2.0–6.0 mm, step 0.2 |
| cap_margin | Distance of the cap from the edge of the footprint | 0.5 | 0.2–1.5 mm, step 0.1 |
| lip_height | Height of the shoulder rim below the thread on which the cap sits | 3.5 | 2–8 mm, step 0.5 |
| lip_round | Rounding of the upper outer edge of the shoulder rim | 1.0 | 0–2 mm, step 0.25 |
| cap_chamfer | Chamfer on the cap's lower edge against elephant's foot | 0.6 | 0–2 mm, step 0.1 |

### Cap Grip

| Parameter | Description | Default | Range |
|---|---|---|---|
| grip_style | Grip grooves or smooth | flutes | Vertical grooves, smooth |
| grip_pitch | Target spacing of the grooves; the count scales with the cap | 6 | 3–15 mm, step 0.5 |
| grip_depth | Groove depth; keep up to 0.6 so the thread wall stays strong | 0.5 | 0.3–0.8 mm, step 0.1 |

### Text on the Cap

| Parameter | Description | Default | Range |
|---|---|---|---|
| lid_text_enabled | Engrave text into the cap top face | 0 | 0 = off, 1 = on |
| lid_text | Text | M3 | Free text |
| lid_text_size | Font size, 0 = automatically fitted to the cap | 0 | 0–40 mm, step 0.5 |
| lid_text_depth | Engraving depth | 0.6 | 0.3–1.5 mm, step 0.1 |

### Baseplate Fit Test

| Parameter | Description | Default | Range |
|---|---|---|---|
| baseplate_cells | Cells per side (N × N) | 2 | 1–5 |
| baseplate_floor | Floor thickness under the cells | 1.2 | 0.8–3.0 mm, step 0.2 |
| baseplate_rim | Additional rim around the cells | 1.2 | 0.4–4.0 mm, step 0.2 |
| baseplate_clearance | Clearance between bin foot and cell per side | 0.15 | 0.05–0.40 mm, step 0.05 |

### Quality

| Parameter | Description | Default | Range |
|---|---|---|---|
| round_res | Render smoothness | 96 | 48–180, step 8 |
| thread_res | Segments per thread turn | 48 | 24–96, step 8 |

## Construction

### OpenSCAD Approach

The model is OpenSCAD and uses the BOSL2 library for the robust trapezoidal
thread. The Gridfinity geometry is written from the public specification. The
jar is round and fills the footprint; the cap screws on from the outside and
stays within the bin envelope.

### Parametric Logic

The dimensions result from the inputs as follows:

| Size | Calculation |
|---|---|
| Footprint | grid_size × 42 − base_gap (1 cell: 41.5 mm) |
| Cap outer radius | footprint / 2 − cap_margin |
| Jar and thread radius | cap radius − cap_wall − lid_tolerance / 2 |
| Closed height | units × 7 mm |
| Minimum height | as many units as needed for the foot, jar body, shoulder rim and cap including thread to fit |
| Inner floor | at least above the magnet pockets (pocket height + 0.8 mm); with several cells at least 1 mm above the foot gaps |

With the default settings (1×1, 7 units), the result is a height of 49 mm and a
thread outer diameter of about 36 mm; the minimum height is 4 units (28 mm). The
values are derived from the formulas and the default values.

### Print Optimizations

- **Self-supporting thread:** 45° flanks, the cap is printed with the top face
  down.
- **No elephant's foot on the cap:** `cap_chamfer` chamfers the lower edge.
- **Thread as perimeters:** the thread consists almost only of outer walls,
  hence 4 walls.
- **Multi-cell floors:** the inner floor lies above the foot gaps so that the
  floor does not become see-through.
- **Large jars:** from 3×3, jar and cap are generated as separate objects; the
  slicer places them on two plates if necessary.

![2×2 baseplate fit test with two inserted jars](images/06_grundplatte-passprobe.jpg)

## Variants

Five reference variants belong to the model. All are settings of the same model;
in the Customizer you can set any other values.

| Variant | Grid | Height | Magnets | Cap text |
|---|---|---|---|---|
| v1_1x1_screws_49mm | 1×1 | 7 units (49 mm) | Glue-in | M3 |
| v2_1x1_beads_35mm | 1×1 | 5 units (35 mm) | Press-fit | BEADS |
| v3_2x2_spices_42mm | 2×2 | 6 units (42 mm) | Glue-in | SPICE |
| v4_3x3_bulk_56mm | 3×3 | 8 units (56 mm) | Glue-in | BULK (jar and cap separate) |
| v5_baseplate_2x2_test | 2×2 cells | – | – | Baseplate fit test |

![1×1 jar with cap label "BEADS", behind it an open jar with visible thread](images/03_1x1-perlen.jpg)

## Print Recommendations

| Setting | Recommendation |
|---|---|
| Material | PLA for dry storage, PETG for a tougher feel |
| Layer height | 0.20 mm |
| Walls | 4 (the thread consists of perimeters) |
| Infill | 15 % gyroid |
| Supports | none |
| Jar orientation | upright on the Gridfinity foot, opening facing up |
| Cap orientation | top face down, opening facing up |
| Baseplate orientation | flat |

Special notes

- **Thread fit:** If the cap jams, increase `thread_slop` to about 0.15. If it
  sits too loosely, reduce it.
- **Magnets:** insert them into the pockets from below, mind the polarity and
  fit all jars and plates the same way round. For the glue-in pockets, a drop of
  superglue is enough.
- **Fit in the baseplate:** If the jars fit tightly, increase `base_gap` to
  0.6 mm. If you have a baseplate from elsewhere, print the fit test first.
- **Test before the big print:** If you change thread or fit values, print a
  test piece first.

![3×3 storage jar with cap label "BULK"](images/05_3x3-vorrat.jpg)

## What Else You Need

The jar is the **bin**, not the baseplate. To use it in the Gridfinity system,
you need:

1. **A Gridfinity baseplate** (42 mm grid) – plain, magnetic or screw-down.
   You can print the **fit test** from this model (1–5 cells per side) or search
   MakerWorld for "Gridfinity baseplate". For a plate sized to your drawer, the
   [Gridfinity Layout Tool](https://gridfinitylayouttool.com/) or
   [Gridfinity Rebuilt for OpenSCAD](https://github.com/kennetek/gridfinity-rebuilt-openscad),
   for example, can help.
   Background and specification: [gridfinity.xyz](https://gridfinity.xyz/).
2. **Magnets (optional):** 6 × 2 mm neodymium discs, 4 per cell, only if your
   plate has magnet pockets.
3. **A little glue** for the magnets (for glue-in pockets).
4. **A compartment** that matches the baseplate: measure the inner dimension,
   divide by 42 mm, print that many cells.

Without a baseplate, the jars also work as free-standing screw-top jars.

## Usage Examples

- **Workshop:** Sort screws, nuts, wall plugs and small parts in the grid and
  label them ("M3").
- **Electronics:** SD cards, jumper wires, small parts for projects.
- **Crafts:** Beads, buttons, sewing supplies.
- **Kitchen:** Spices in the drawer ("SPICE" variant).
- **Storage:** Large 3×3 jar for bulk goods.
- **Colour coding:** Jars and caps in different colours for different contents.

## Troubleshooting / FAQ

| Problem | Cause | Solution |
|---|---|---|
| Cap jams | Thread clearance too small for your printer | Increase `thread_slop` to about 0.15 |
| Cap sits loosely | Thread clearance too large | Reduce `thread_slop` |
| Jar fits tightly in the baseplate | Gap too small | Increase `base_gap` to 0.6 mm |
| Jar is taller than set | A minimum height is needed for the thread, the model raises the height automatically | Intended; with fewer thread turns (`thread_turns`) or a smaller shoulder (`lip_height`) the minimum height drops |
| Inner floor is higher than set | The floor is raised above magnet pockets and foot gaps | This is intended; omit the magnets or check `floor_z` |
| Magnets stick the wrong way round | Polarity not uniform | Fit all jars and plates the same way round |
| Jar and cap are on two plates | 3×3 and larger are separate objects | Print on two plates in the slicer |

## Development History

The model was created in October 2026 as a screw-top jar for the Gridfinity
system and was published on MakerWorld in the same month. The thread uses a
coarse, self-supporting trapezoid form; the ISO form was kept as an option.

The images in this repository are renderings of the model geometry or scene
images derived from it; environment, labelling and accessories such as screws
are illustrative.

![2×2 jar with yellow cap "SPICE" on a baseplate, with a removed cap beside it](images/04_2x2-gewuerze.jpg)

## Downloads

Print files are intentionally available exclusively on MakerWorld.

👉 MakerWorld link: [https://makerworld.com/en/models/3434732-parametric-gridfinity-screw-top-jar](https://makerworld.com/en/models/3434732-parametric-gridfinity-screw-top-jar)

Profile: [https://makerworld.com/en/@BetaHydri](https://makerworld.com/en/@BetaHydri)

## License

Documentation and images in this repository: © BetaHydri. The model (including
source code) and all print files are distributed exclusively via MakerWorld
under the licence stated there (CC BY-NC-SA 4.0). This repository deliberately
contains no model, source code or print files.

Gridfinity is an open standard by Zack Freedman ([gridfinity.xyz](https://gridfinity.xyz/)).
The geometry of this model is written from the public specification.
