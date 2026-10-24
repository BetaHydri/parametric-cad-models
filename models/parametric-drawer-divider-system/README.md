# Parametric Drawer Divider System – Plug-In Drawer Dividers for Any Drawer

[← All models](../../README.md)

🌐 **English** | [Deutsch](README.de.md)

Parametric divider system for drawers: you enter the inner dimensions of your drawer and the number of
compartments, and print flat dividers that plug into each other like an egg carton. Long dividers are split
into puzzle pieces that fit on the print bed – even a 600 mm kitchen, workshop or camper-van drawer is no
problem. All in the MakerWorld Customizer, flat and without supports.

[![MakerWorld](https://img.shields.io/badge/MakerWorld-Model-00AE42)](https://makerworld.com/en/models/3437057-parametric-drawer-divider-system)
![OpenSCAD](https://img.shields.io/badge/OpenSCAD-parametric-yellow)
![Bambu Lab](https://img.shields.io/badge/Bambu%20Lab-P1S%20%7C%20P2S%20%7C%20H2C-green)
![License](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-blue)

> The model with all print profiles is available exclusively on MakerWorld:
> 👉 [MakerWorld link: https://makerworld.com/en/models/3437057-parametric-drawer-divider-system](https://makerworld.com/en/models/3437057-parametric-drawer-divider-system)

![Six drawers with orange and blue dividers on a wooden table, with title and feature icons](images/01_hero.jpg)

The system is intended for kitchen, cutlery, desk, workshop and camper-van drawers. It can also take the
inner dimensions directly from the **Stackable Parametric Drawer System**
([MakerWorld](https://makerworld.com/en/models/3024548-parametric-stackable-drawer-system),
[documentation on GitHub](../stackable-drawer-organizer/README.md)).

## Table of Contents

- [The Problem](#the-problem)
- [The Idea](#the-idea)
- [Highlights](#highlights)
- [Parametric Options](#parametric-options)
- [Construction](#construction)
- [Variants](#variants)
- [Print Recommendations](#print-recommendations)
- [Working with the Stackable Drawer System](#working-with-the-stackable-drawer-system)
- [Application Examples](#application-examples)
- [Troubleshooting / FAQ](#troubleshooting--faq)
- [Development History](#development-history)
- [Downloads](#downloads)
- [License](#license)

## The Problem

Drawers are rarely the same size as the inserts from the store:

- Ready-made cutlery trays and organizers do not fit exactly; gaps remain in which things slide around.
- Dividers without hold rattle when opening and closing.
- Long dividers do not fit on a print bed.
- In narrow drawers, individual dividers tip over.
- Camper-van drawers are often unusually large or small, and the material has to withstand heat.

## The Idea

A made-to-measure divider system: you measure inner width, inner depth and inner height, choose columns and
rows, and get a plug-in grid. Long dividers plug into each other with slots from below, cross dividers with
slots from above – without glue, without screws. All dimensions are millimeters, all values are Customizer
parameters.

## Highlights

- **Any drawer size:** Inner width, depth and height are parameters (width and depth 40–700 mm, height 15–200 mm).
- **Plug-in egg carton:** The slots are exactly one divider thickness plus a small clearance wide (`slot_clear`);
  the dividers hold, but can be taken apart for cleaning.
- **Equal or unequal compartments:** 1–12 columns and 1–12 rows, each equally sized or with one double-width
  compartment (first, last or middle).
- **Puzzle joints:** Dividers that are longer than the selected piece length (`max_piece`) are split into pieces
  with puzzle joints. The joints lie away from the slots.
- **Wedge ends:** Small crush ribs at the divider ends (`grip`) clamp the divider between the drawer walls so
  that nothing rattles.
- **Finger scoops:** optionally a round scoop at the top edge of each compartment.
- **Edge rails for narrow drawers:** If there is only one divider direction (for example 1 × 4), two low rails
  along the side walls keep the dividers upright. The middle of the drawer stays free.
- **Matches the Stackable Drawer System:** Choose the source "Stackable Drawer System" and enter the same unit
  values – the grid then matches the inner dimensions of that drawer.
- **Flat and without supports:** Every part lies flat on the bed. The model distributes the parts over as many
  build plates as needed and shows the number.

![Stackable drawer with 2 × 2 dividers](images/02_stapelbar-2x2.jpg)

## Parametric Options

The names correspond to the model's Customizer parameters.

### Part Selection

| Parameter | Description | Default | Selection |
|---|---|---|---|
| part | What is generated | plate | PRINT (all parts of one plate), OVERVIEW (shows all plates for counting, not for printing), long dividers only, cross dividers only (advanced), preview in the drawer (not for printing) |
| plate_no | Plate to print (1 = first); each plate contains dividers and rails | 1 | 1–8 |

### Drawer

| Parameter | Description | Default | Range |
|---|---|---|---|
| drawer_source | Custom drawer (enter inner dimensions) or Stackable Drawer System (calculated) | custom | Custom drawer, Stackable Drawer System |
| inner_w | Inner width, left–right; only for a custom drawer | 300 | 40–700 mm |
| inner_d | Inner depth, front–back; only for a custom drawer | 400 | 40–700 mm |
| inner_h | Inner height; only for a custom drawer | 60 | 15–200 mm |

### Compartments

| Parameter | Description | Default | Selection |
|---|---|---|---|
| cols | Number of compartments across the width (cols − 1 cross dividers) | 3 | 1–12 |
| rows | Number of compartments along the depth (rows − 1 long dividers) | 4 | 1–12 |
| col_layout | Width distribution | equal | Equal width, first / last / middle column twice as wide |
| row_layout | Depth distribution | equal | Equal depth, first / last / middle row twice as deep |

### Dividers

| Parameter | Description | Default | Range |
|---|---|---|---|
| div_t | Divider thickness, multiples of 0.4 mm | 2.0 | 1.2–4 mm, step 0.4 |
| div_h | Divider height, 0 = drawer height minus 1 mm | 0 | 0–200 mm |
| fit_gap | Total gap between divider ends and drawer walls | 0.4 | 0–2 mm, step 0.1 |
| grip | Height of the crush ribs at the ends, 0 = off | 0.35 | 0–1 mm, step 0.05 |
| slot_clear | Additional width of the plug-in slots | 0.25 | 0.1–0.6 mm, step 0.05 |
| base_rail | Low rails when there is only one divider direction (1 column or 1 row) | 1 | Off, two edge rails (recommended), one center rail |
| rail_h | Rail height | 16 | 12–40 mm |
| finger_notch | Finger scoop at the top edge of each compartment | 1 | 0 = off, 1 = on |
| notch_r | Radius of the finger scoop | 12 | 6–25 mm |

### Printing

| Parameter | Description | Default | Range |
|---|---|---|---|
| max_piece | Longest piece in one print; longer dividers are split with a puzzle joint | 220 | 80–400 mm, step 5 |
| plate_w | Width of the build plate for the arrangement | 240 | 100–400 mm, step 10 |
| plate_d | Depth of the build plate | 240 | 100–400 mm, step 10 |
| plate_gap | Spacing between the parts on the plate | 4 | 2–12 mm |
| joint_clear | Clearance of the puzzle joint | 0.2 | 0.1–0.5 mm, step 0.05 |

### Stackable Drawer System (only with the source "Stackable Drawer System")

| Parameter | Description | Default | Range |
|---|---|---|---|
| sd_unit_width | Unit width | 120 | 70–250 mm |
| sd_unit_depth | Unit depth | 150 | 80–320 mm |
| sd_shell_wall | Wall thickness of the housing | 4.0 | 3.2–8 mm, step 0.1 |
| sd_side_gap | Side gap | 1.0 | 0.4–3 mm, step 0.1 |
| sd_drawer_wall | Wall thickness of the drawer | 2.0 | 1.6–8 mm, step 0.1 |
| sd_rail_backstop | Stop of the rail | 3.0 | 0–12 mm, step 0.5 |
| sd_front_t | Thickness of the front | 3.0 | 2–6 mm, step 0.1 |
| sd_inner_h | Inner height of the chosen drawer (h1 … h6 of the drawer system) | 50 | 18–160 mm |

## Construction

### OpenSCAD Approach

The model is pure OpenSCAD without external libraries and runs in the MakerWorld Customizer. The dividers are
flat plates that are extruded: Long dividers have their slots at the bottom, cross dividers at the top, so that
they cross in the middle and plug into each other flush. The parts are distributed over build plates; the model
numbers the plates (`plate_no`) and shows in the overview how many you need.

### Parametric Logic

| Value | Calculation |
|---|---|
| Divider height | `div_h`, at 0 the inner height minus 1 mm |
| Slot width | `div_t` + `slot_clear` |
| Length of a long divider / cross divider | inner dimension minus `fit_gap` |
| Compartment edges | inner dimension, proportionally by weighting (equal or one double-width compartment) |
| Number of pieces | divider length / `max_piece`, rounded up |
| Inner dimension from the Stackable Drawer System | Width = `sd_unit_width` − 2 × `sd_shell_wall` − 2 × `sd_side_gap` − 2 × `sd_drawer_wall`; depth = `sd_unit_depth` − `sd_shell_wall` − `sd_rail_backstop` − `sd_front_t` − 0.6 − 2 × `sd_drawer_wall`; height = `sd_inner_h` |

With the default settings of the Stackable Drawer System, this results in inner dimensions of 106 × 135.4 mm at
50 mm height. The values are derived from the formulas and the default values.

### Special Algorithms

- **Egg carton:** Long dividers and cross dividers have opposing slots – at the bottom and at the top – and
  thus plug into each other.
- **Puzzle joint:** The separation points are chosen automatically so that they lie at a distance from the
  slots; tongue and pocket have the clearance `joint_clear`.
- **Edge rails:** If there is only one divider direction, low rails along the side walls (or one in the middle)
  with slots for each divider are generated. They keep the dividers upright.
- **Finger scoops:** One scoop per compartment, only if the compartment is wide enough and the scoop does not
  hit a joint.
- **Plate distribution:** The parts are packed onto as many plates as the print area (`plate_w` × `plate_d`)
  requires.

### Print Optimizations

- All parts lie flat on the bed, without supports and without overhangs.
- Crush ribs at the ends (`grip`) clamp the dividers between the drawer walls.
- Divider thickness in multiples of 0.4 mm, matching the 0.4 mm nozzle.

![Orange and blue divider piece with puzzle joint](images/07_puzzleverbindung.jpg)

## Variants

Reference configurations belong to the model. All are settings of the same model; in the Customizer you set any
other values you like.

| Variant | Drawer | Compartments | Special feature |
|---|---|---|---|
| v1_stackable_2x2 | Stackable Drawer System (calculated) | 2 × 2 | – |
| v2_stackable_3x2_wide | Stackable Drawer System (calculated) | 3 × 2 | first row twice as deep |
| v3_utensil_200x280_3x2 | 200 × 280 mm, 45 mm high | 3 × 2 | cutlery and utensils |
| v4_narrow_150x420_1x4 | 150 × 420 mm, 50 mm high | 1 × 4 | narrow drawer, edge rails |
| v5_kitchen_300x400 | 300 × 400 mm, 60 mm high | 3 × 4 | `max_piece` 110 mm, three build plates |

![Narrow drawer 150 × 420 mm with 1 × 4 dividers](images/05_schmal-1x4.jpg)

## Print Recommendations

| Setting | Recommendation |
|---|---|
| Material | **PETG recommended**; in a van or camper PETG or ASA; PLA for normal drawers in the house |
| Layer height | 0.20 mm |
| Walls | 3 |
| Infill | 15% gyroid |
| Supports | none |
| Orientation | all parts flat on the plate |

Special notes

- **Why PETG:** Slightly flexible, so that wedge ends and slots grip without breaking, and it withstands heat.
  In a van or camper, the interior gets hot in summer and PLA becomes soft.
- **Warping:** Long, thin parts can lift at the corners – use a brim and a clean bed.
- **Assembly:** Long dividers have the slots at the bottom, cross dividers at the top. Plug them together at
  the crossings, then place the grid in the drawer. Lay split dividers next to each other and press the tongue
  into the pocket from above.
- **Too tight or too loose in the drawer:** Increase `fit_gap` (looser) or increase `grip` (firmer) and print a
  short test piece.
- **How to get all parts:**
  1. Set the drawer dimensions and compartments.
  2. Choose `part` = OVERVIEW; each plate is labeled "PLATE 1 OF N".
  3. Choose `part` = PRINT, load plate 1, then set `plate_no` to 2, 3 … up to N and load each plate.
  Each plate contains dividers and rails; together the plates are the complete set.

![Kitchen drawer 300 × 400 mm with 3 × 4 dividers](images/06_kueche-3x4.jpg)

## Working with the Stackable Drawer System

Set `drawer_source` to "Stackable Drawer System" and enter the same values you used for the drawer:
`sd_unit_width`, `sd_unit_depth`, `sd_shell_wall`, `sd_side_gap`, `sd_drawer_wall`, `sd_rail_backstop`,
`sd_front_t` and the inner height of the drawer `sd_inner_h` (h1 … h6 of the drawer system). The dividers then
match the inner dimensions of the printed drawer. Use them instead of or together with the built-in flat
inserts.

![Stackable drawer with 3 × 2 dividers](images/03_stapelbar-3x2.jpg)

## Application Examples

- **Kitchen:** Organize cutlery, utensils and kitchen helpers.
- **Desk:** Separate pens, tape, cables and odds and ends.
- **Workshop:** Sort screws, bits and tools by type.
- **Van and camper:** Drawers made to measure, dividers in PETG or ASA.
- **With the Stackable Drawer System:** Dividers that match the inner dimensions of the drawer exactly.
- **Color coding:** Dividers in two colors for a clear grid.

![Utensil drawer 200 × 280 mm with dividers inserted](images/04_besteck-3x2.jpg)

## Troubleshooting / FAQ

| Problem | Cause | Solution |
|---|---|---|
| Dividers rattle in the drawer | Too much gap | Decrease `fit_gap` or increase `grip` |
| Dividers jam when inserting | Too little gap | Increase `fit_gap` or decrease `grip` |
| Dividers cannot be plugged into each other | Slots too narrow for your printer | Increase `slot_clear` |
| Puzzle pieces fit too tightly or too loosely | Clearance does not suit the printer | Adjust `joint_clear` |
| Parts are missing from the print | Only one plate was printed | Check the plate count with `part` = OVERVIEW and step through `plate_no` |
| Dividers tip over in a narrow drawer | Only one divider direction | Keep `base_rail` = edge rails (recommended) |
| Corners lift during printing | Long, thin parts | Use a brim, clean the bed |
| Dividers too tall for the drawer | Height does not fit | Set `div_h`; 0 takes the inner height minus 1 mm |

## Development History

The model came about in October 2026 as a divider system for any drawer, including the Stackable Parametric
Drawer System, and was published on MakerWorld in the same month. For drawers with only one divider direction,
edge rails were added that keep the dividers upright.

The scene images in this repository were created with AI assistance from rendered model geometry (environment,
lighting and material appearance); the dividers correspond to the model. Drawer, contents and furniture are
illustrative.

## Downloads

Print files are intentionally available exclusively on MakerWorld.

👉 MakerWorld link: [https://makerworld.com/en/models/3437057-parametric-drawer-divider-system](https://makerworld.com/en/models/3437057-parametric-drawer-divider-system)

Profile: [https://makerworld.com/en/@BetaHydri](https://makerworld.com/en/@BetaHydri)

## License

Documentation and images in this repository: © BetaHydri. The model (including source code) and all print
files are distributed exclusively via MakerWorld under the license stated there (CC BY-NC-SA 4.0). This
repository intentionally contains no model, source code or print files.
