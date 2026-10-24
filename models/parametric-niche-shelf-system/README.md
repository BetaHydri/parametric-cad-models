# Parametric Niche Shelf System – Shelf for Narrow Niches with Corner Posts, Screw Feet and Hose Cover

[← All models](../../README.md)

🌐 **English** | [Deutsch](README.de.md)

A parametric, fully printable shelf system for a narrow niche – created for
the gap next to a camper toilet, usable for any niche (storage gap, bathroom,
van, workshop). The trays have a rim at the front and on the sides to keep
things from sliding out, a printed back wall with screw holes, stackable corner
posts, height-adjustable **printed** screw feet and, optionally, a standalone
cover for a ventilation hose.

[![MakerWorld](https://img.shields.io/badge/MakerWorld-Model-00AE42)](https://makerworld.com/en/models/3464475-parametric-niche-shelf-system)
![OpenSCAD](https://img.shields.io/badge/OpenSCAD-parametric-yellow)
![Bambu Lab](https://img.shields.io/badge/Bambu%20Lab-H2C%20%7C%20P2S%20%7C%20P1S-green)
![Print files](https://img.shields.io/badge/Print%20files-MakerWorld%20only-blue)

> **The model with all print profiles is available exclusively on MakerWorld:**
> 👉 [MakerWorld link: https://makerworld.com/en/models/3464475-parametric-niche-shelf-system](https://makerworld.com/en/models/3464475-parametric-niche-shelf-system)
>
> ![Camper Niche Shelf System – Set A with screw feet and Set B with honeycomb front](images/01_hero.jpg)

In the MakerWorld Customizer you enter the dimensions of your niche (depth,
width at the back and front, height, optionally the position of a hose), and
the model calculates the trays, posts, feet, wall plates and cover to match.
The system works in **straight and sloped niches** and offers **five mounting
options** – from a free-standing shelf to wall mounting.

## Table of Contents

- [The Problem](#the-problem)
- [The Idea](#the-idea)
- [Highlights](#highlights)
- [Ready-Made Sets](#ready-made-sets)
- [Parametric Options](#parametric-options)
- [Sloped Niche](#sloped-niche)
- [Mounting Options](#mounting-options)
- [Design](#design)
- [What Do I Need to Buy?](#what-do-i-need-to-buy)
- [Print Recommendations](#print-recommendations)
- [Assembly](#assembly)
- [Use Cases](#use-cases)
- [Troubleshooting / FAQ](#troubleshooting--faq)
- [Development History](#development-history)
- [Downloads](#downloads)
- [License](#license)

## The Problem

Narrow niches are hard to use: ready-made shelves rarely fit a size like
160 × 300 mm, and in a moving camper, bottles, spray cans and toilet paper
have to stay in place during braking and starting. In addition, there are
peculiarities of the niche:

- Walls that are not parallel, for example a sloped side toward the toilet.
- A ventilation hose that runs across the top of the niche and needs space.
- A floor that is not level.
- A wall you do not want to drill into everywhere.

## The Idea

Instead of a rigid shelf, there is a kit made of a few parts:

- **Trays** with a rim at the front and on the sides that adapt to the niche.
- **Corner posts** on which the next tray stands – with no screws in the lower
  end, with a centering pocket.
- **Printed screw feet** that level out the floor. Nothing has to be bought.
- **Back wall plates** or **wall brackets** if the shelf is to be mounted on the
  wall.
- A **hose cover** that is slid in from the front.

Everything is calculated from the same dimensions. If the values do not fit
together (trays too close, rim too low, screw holes too near), the model stops
with a clear message instead of silently delivering bad geometry.

![Preview of the assembled shelves in the niche](images/04_vorschau-montiert.jpg)

## Highlights

- **1 to 4 trays** stacked, each with its own height and its own depth limit
  (for example, a shorter upper tray so that a latch remains reachable).
- **Straight or sloped niche:** width at the back and front can be set
  separately.
- **Five mounting options**, from "free-standing, nothing in the wall" to
  "wall brackets only, without posts".
- **Printed screw feet** (trapezoidal thread, height adjustment by hand) – or
  purchased M8 leveling feet, or no feet at all.
- **Front rim solid or as a honeycomb grid** (lighter, less filament).
- **Optional hose cover** with wall arms, ventilation slots and stiffening
  ribs, tested for slide-in feasibility.
- **Fit-test plate** (5 minutes of printing) to check the niche before the big
  print.
- **Two joint types:** self-tapping screw holes or threaded inserts (heat-set
  inserts) with threaded studs.
- **Selectable screw head:** countersunk or socket head hex; M2 to M5 for all
  wall screws.
- **Load estimate** for wall brackets (weight per tray, factor for driving).
- **Checks and hints** in the console: height reserve per compartment, post
  lengths, shopping list for exactly your settings.

## Ready-Made Sets

Two complete sets for my own niche (160 × 300 × 380 mm, Bambu Lab H2C, ASA) are
available on MakerWorld. Each set is a 3MF with four plates.

| | Set A "Screw Feet" | Set B "Flat + Honeycomb Front" |
|---|---|---|
| Front rim | solid | **honeycomb grid** |
| Lower tray | on four **printed screw feet** (compensates for unevenness) | **directly on the floor** (saves 37 mm of height) |
| Posts | 4 × 115 mm | 4 × 152 mm |
| Suitable for | uneven floors, easy leveling | low niches, few parts, airy look |

![Set A with printed screw feet](images/02_set-a-schraubfuesse.jpg)

![Set B with honeycomb front, directly on the floor](images/03_set-b-wabenfront.jpg)

You export your own dimensions and other mounting options from the Customizer.

## Parametric Options

The options in the Customizer are arranged in groups:

| Group | What you set |
|---|---|
| Part selection (`part`) | preview assembled / exploded, all parts single-color or multicolor, single tray, wall bracket, posts and feet, hose cover, fit test |
| Quick settings | number of trays (`tray_count`), feet (`feet`), hose cover on/off (`hose_enable`) |
| Niche dimensions | depth, width at the back and front, height, maximum tray width |
| Hose | height left and right, diameter, distance to the back wall, air around the pipe, connector piece |
| Clearances | distance to the wall on the left and right, distance at the front, fit clearance of the wall brackets |
| Trays | height of each tray, depth limit per tray, floor thickness, rim thickness, rim heights, corner radius, dividers, drain slots, front rim solid or honeycomb |
| Mounting | `mounting`, screw size, head shape, number of wall holes, back wall thickness and height, wall gap |
| Wall brackets | number, thickness, length, web dimensions, locking of the tray |
| Load check | weight per tray, factor for driving, permissible stress and pull-out force |
| Posts, feet, joints | post diameter, joint type, insert dimensions, M8 leveling feet |
| Printed screw feet | thread diameter and pitch, adjustment range, foot disc, thread clearance |
| Hose cover | thickness, height, air to the hose, number and dimensions of the wall arms, ventilation, ribs |
| Colors, print bed, quality | colors of the trays and parts, print bed size (for warnings only), smoothing |

Lists such as `tray_z` (height of each tray) and `tray_depth_limit` (depth of
each tray) consist of one value per tray.

![Exploded preview](images/05_vorschau-explodiert.jpg)

## Sloped Niche

Not every niche has parallel walls. If the right side (or an obstacle such as
the toilet) runs at an angle, you enter the free width **at the back wall**
(`niche_w_back`) and **at the opening** (`niche_w_front`) separately, for
example 160 mm at the back and 110 mm at the front. The right edge of each
tray, the rims, the back wall plates, the posts and the wall brackets then
follow the sloped wall; the gap stays `side_gap_right`. The tray becomes a
wedge instead of a rectangle.

- Works with all five mounting options and with 1 to 4 trays
  (verified in the design for 160 → 110 mm).
- The tray width is limited by `tray_max_w` (default 170 mm) and must be at
  least 40 mm, otherwise a message appears.
- If something protrudes at only one spot, use the **smaller** value or
  increase `side_gap_right`.
- Wedge-shaped trays are not rectangular: print the **fit test** first, it
  shows the exact contour.

![Sloped niche: 160 mm at the back, 110 mm at the front](images/06_schraege-nische.jpg)

## Mounting Options

One setting (`mounting`), no contradictory combinations:

| Option | Support | Additionally required | Suitable for |
|---|---|---|---|
| **Posts and feet + back wall screws** (default) | posts and feet carry the load; the printed back wall of each tray is screwed to the wall | wall screws (`wall_holes` per tray) | camper, any use involving movement |
| **Posts and feet + wall brackets** | as above, plus printed wall brackets under the trays | 4 wall screws per bracket, 1 × M3 × 8 as tray lock | heavier loads, more rigidity |
| **Posts and feet only** | free-standing, **nothing in the wall** | only the M4 screws | rental apartment, tiles, stationary use |
| **Wall brackets only without posts** | no posts or feet, each tray hangs on wall brackets (tray 1 stands on the floor) | 4 wall screws per bracket (`bracket_count` 2–3) | maximum freedom between the compartments |
| **Back wall screws only without posts** | trays hang only on the wall screws (console warns) | wall screws | light loads, solid wall |

Further settings for this:

- **Feet** (`feet`, only with posts): printed screw feet, purchased M8 leveling
  feet, or none (tray stands on the floor, saves about 37 mm).
- **Wall gap** (`wall_gap`, 0 to 30 mm): printed spacer sleeves behind the back
  wall plates for uneven walls.
- **Wall brackets:** `bracket_count`, `br_len`, `br_inset`, `lock_tray`. The
  console outputs a load estimate; it is only a guideline, check your wall.

![Wall bracket variant](images/07_wandwinkel.jpg)

## Design

- **Trays** have a rim at the front and on both sides, rounded front corners
  and four corner holes for the posts. On the back there is a plate with
  countersinks for the wall screws.
- **Posts** stand in centering pockets (8 mm deep) on the tray below and are
  fixed only at the top with an M4 screw through the next tray. If an upper
  tray has a smaller depth, the posts automatically move toward the back.
- **Printed screw feet:** the foot block and foot have a coarse trapezoidal
  thread (Ø 18 mm, pitch 3.5 mm, verified combination). The foot can be turned
  by hand; the adjustment range is 8 mm.
- **Hose cover:** not a closed "U" (which could not be mounted around a hose
  that is fixed at both ends), but an **L** that is slid in from the front and
  screwed to small wall arms below the hose, where a screwdriver can reach. A
  path simulation confirmed that the cover can be slid in and that the hose,
  connector and trays remain clear.
- **Fit test:** thin outline plate of the tray in the size of your inputs.

![Upper tray with posts, feet and foot blocks](images/08_obere-schale-pfosten-fuesse.jpg)

![Hose cover with wall arms](images/09_schlauchabdeckung.jpg)

## What Do I Need to Buy?

Almost nothing: posts, feet and back wall plates are printed. Only screws are
missing.

Standard setup (2 trays, back wall screws, printed feet, hose cover):

| Quantity | Screw | Purpose |
|---|---|---|
| **8** (Set A) / **4** (Set B) | **M4 × 10 countersunk** (ISO 10642 / DIN 7991) | tray → feet / posts; they cut their own thread into the printed 3.3 mm holes |
| **6** | **Wall screws, countersunk**, size M3 (default), M2 to M5 possible | 2 per tray back wall plus 1 per wall arm of the cover; type and length depend on **your** wall |
| **2** | **M3 × 8 countersunk** | hose cover → wall arms |
| 4, optional | felt or rubber discs Ø 26 mm, self-adhesive | under the screw feet (Set A) |

- **Socket head hex instead of countersunk:** `screw_head = Socket head hex
  screw`, then M4 × 8 for tray → post and M3 × 6 for the cover.
- **Threaded inserts:** `joint = Heat-set inserts`, then M4 inserts (bore
  Ø 5.6 mm, adjustable), M4 threaded studs and M4 × 10 countersunk screws for
  the top tray. The trays are clamped between the foot block and the post.
- The console in OpenSCAD outputs the exact list for your settings.

## Print Recommendations

- **Material:** **ASA** or PETG. A parked camper gets hot; PLA softens from
  about 50 °C.
- **Trays and cover:** 0.4 mm nozzle, 0.2 mm layer height, 2 to 4 walls, 15 %
  infill.
- **Foot blocks and screw feet (Set A):** 0.16 mm layer height, 4 walls, 40 %
  infill, slow outer walls – a thread consists almost entirely of perimeters.
- **Posts and wall arms:** 3 to 4 walls, 25 to 40 % infill.
- **Supports:** not needed; all parts lie print-ready.
- **Printer:** The sets are sliced for the **Bambu Lab H2C** (the lower tray is
  297 mm deep). On a 256 mm printer, you shorten the trays in the Customizer
  (`front_setback`, `wall_gap`); the model warns if something does not fit on
  the print bed (`bed_xy`).
- **Thread test:** Print one foot block and one screw foot and screw them
  together. Too tight: `thread_clear` from 0.35 to 0.45; too loose: 0.25.

The estimated values of the sets (Bambu Studio) are about 15.5 h and 455 g for
Set A and 14.75 h and 420 g for Set B.

![Fit-test plate](images/10_passungstest.jpg)

## Assembly

1. **Feet (Set A):** Turn each screw foot into the foot block from below, leaving
   about 4 mm between disc and block (one turn = 3.5 mm). Set all four the same;
   the rear ones are hard to reach later.
2. **Lower tray:** For Set A, place it on the four foot blocks and screw one
   M4 × 10 from above through each corner hole; for Set B, simply place it on
   the floor.
3. **Posts:** Stand them in the four centering pockets (not screwed at the
   bottom).
4. **Upper tray:** Place it on the posts and screw one M4 × 10 from above into
   each post. For 3 to 4 trays, repeat steps 3 and 4.
5. **Align** with a spirit level (Set A: turn the front feet by hand).
6. **Wall:** Mark the holes, pre-drill, screw each tray to the wall. With a wall
   gap, first press the sleeves into the pockets.
7. **Hose cover (optional):** Screw the wall arms on below the hose, slide the
   cover in from the front and fix it to the arms with one M3 × 8 each.

## Use Cases

- **Camper niche next to the toilet** (the original): two trays, shorter upper
  tray, hose cover above.
- **Single tray under a drawer:** `tray_count` = 1, no posts, for example
  85 × 290 mm.
- **Sloped niche in a bathroom or van:** different `niche_w_back` and
  `niche_w_front`.
- **Rental apartment:** `mounting = Posts and feet only`, nothing in the wall.
- **Little space between the compartments:** wall brackets without posts.

## Troubleshooting / FAQ

**Can I also use it outside of a camper?**
Yes, tested for niches from 90 to 300 mm in width, 180 to 420 mm in depth and
250 to 900 mm in height.

**Which side is the hose on?**
On the right when looking into the niche. For a mirrored niche, swap the side
gaps.

**Wide trays sag.**
Trays wider than 200 mm rest on only four posts: increase `tray_t` to 4 to
5 mm and add dividers (`tray_dividers`).

**Why is the upper tray with cover only about 187 mm high?**
The wall arms of the cover need space; the console shows the limit.

**A red sign says "NO POSTS", "NO BRACKETS" or "NO HOSE COVER".**
The selected entry is not used with your settings. Choose a different entry or
change `mounting`, `hose_enable` or `cover_enable`.

**The preview cannot be printed.**
Correct: the two preview entries are for viewing only and show a red "NOT FOR
PRINTING" sign. To print, choose a print entry.

**Limits:** 1 to 4 trays; trays and cover are not split automatically.

> ⚠️ **Status:** verified in the design (all mounting options, 1 to 4 trays,
> many niche sizes, every entry of the `part` menu) and test-sliced for all
> supplied 3MF files. **Not yet printed by me.** Please print the fit test first
> and report in the comments how it worked for you.

## Development History

It started with a tape measure in the camper niche (see photo): depth, width at
the back and front, height and the position of the ventilation hose. These
dimensions are the foundation of the model. Because every niche is different,
they are implemented as parameters, and a checking package in the model (trays,
posts, cover, mounting) stops wrong inputs with a clear message instead of
producing bad geometry. On top of that came the printed screw feet, the sloped
niche and the five mounting options, so that the shelf also fits where my niche
is not.

![Niche measured with a tape measure and ventilation hose](images/11_nische-vermessen.jpg)

The images in this folder are renderings of the model geometry or scene images
derived from it; the niche photo is a real photograph.

## Downloads

Print files are intentionally available exclusively on MakerWorld.

👉 MakerWorld link: https://makerworld.com/en/models/3464475-parametric-niche-shelf-system

Profile: <https://makerworld.com/en/@BetaHydri>

## License

Documentation and images in this repository: © BetaHydri. The model (including
source code) and all print files are distributed exclusively via MakerWorld
under the license stated there. This repository intentionally contains no
model, source code or print files. Model and print files are distributed
exclusively via MakerWorld.
