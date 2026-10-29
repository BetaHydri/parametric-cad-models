# Parametric Cable Management Box – Hides Your Power Strip, Fits Any Printer

[← All models](../../README.md)

🌐 **English** | [Deutsch](README.de.md)

Parametric box that **hides a power strip together with its plugs**. Every cable
leaves through **snap-in cable gates**, a **vented lid** closes the box, and
because a power strip is long, the box **splits itself into segments that fit
your print bed**. You choose your printer and enter your strip in the MakerWorld
Customizer; it lays everything out on the right number of plates, in **two
colours**.

[![MakerWorld](https://img.shields.io/badge/MakerWorld-Model-00AE42)](https://makerworld.com/en/models/3512557-cable-management-box#profileId-4013773)
![OpenSCAD](https://img.shields.io/badge/OpenSCAD-parametric-yellow)
![Bambu Lab](https://img.shields.io/badge/Bambu%20Lab-P1S%20%7C%20P2S%20%7C%20H2C%20%7C%20A1%20mini-green)
![Print files](https://img.shields.io/badge/Print%20files-MakerWorld%20only-blue)

> **The model with all print profiles is available exclusively on MakerWorld:**
> 👉 [MakerWorld link: https://makerworld.com/en/models/3512557-cable-management-box](https://makerworld.com/en/models/3512557-cable-management-box#profileId-4013773)
>
> ![Parametric Cable Management Box – closed box with a power strip hidden under a desk](images/01_hero.jpg)

> **Safety first:** A power strip warms up and a closed box traps that heat.
> Print in **PETG or ASA (never PLA)**, keep the lid vents free, never use the
> box with heaters, kettles or other high-load appliances, never exceed the
> rating of your strip, and have mains wiring done by a qualified person. The
> box is a cover, not a certified enclosure; you use it at your own risk.

## Table of Contents

- [The Problem](#the-problem)
- [The Idea](#the-idea)
- [Highlights](#highlights)
- [Construction Details](#construction-details)
- [Parametric Options](#parametric-options)
- [Design](#design)
- [Print Recommendations](#print-recommendations)
- [Use Cases](#use-cases)
- [Troubleshooting / FAQ](#troubleshooting--faq)
- [Development History](#development-history)
- [Downloads](#downloads)
- [License](#license)

## The Problem

A box for a power strip sounds simple, but the details decide whether it works:

- Power strips are 250–450 mm long, much longer than a printer bed. A box in one
  piece does not fit on a 256 mm plate.
- The plugs have to stay on their cables. If every cable has to be pushed
  through a hole, the plugs must be unplugged first.
- A cable gate that can fall out or be pushed in is useless: a pull on a cable
  must not take the gate with it.
- A split box needs joints that hold, a lid that fits and stays put, and
  everything has to print without supports.
- A closed box heats up. It needs vents, and the material must take the heat.

## The Idea

The box is cut into **equal segments that fit your bed** and tied together by
**bow-tie keys** from underneath. Each end wall has a notch for a **cable gate**
with 1–5 U-shaped snap-in slots; you press the cables in from above, so the
plugs stay on. The notch is **diamond-shaped, widest in the middle of the
wall**, so the gate can neither be pulled out nor pushed in. The lid sits on the
wall tops with a lip inside the box; **friction ribs** on the lip hold it, and
long lids are split into pieces with **scarf-lap joints** that are flush and
print flat. Lid and gates are one colour, base and keys another, each colour on
its **own plates**, so Bambu Studio adds no prime tower. All dimensions in
millimetres.

## Highlights

- **Any strip length, any printer.** The box is cut into equal segments that fit
  your bed (P1S / P2S / X1C / A1: 248 mm, H2C: 296 mm, A1 mini: 172 mm). A
  300 mm strip on a 256 mm bed becomes two segments; a 600 mm strip on an A1
  mini becomes four. A box that fits on one plate is **not** split.
- **Plugs stay on the cables.** Nothing is pushed through a hole: you press each
  cable into a **snap-in gate slot from above**. The slot is a little narrower
  than the cable (`slot_ratio`), so the cable snaps in and is held.
- **Gates that can neither fall out nor be pushed in.** The gate sits in a
  **diamond-shaped (double-dovetail) seat**; a pull on the cable and a push from
  the inside both lock it. It lifts straight out for service.
- **Lid that stays put.** Small **friction ribs** on the lid lip press lightly
  into the walls (`lid_grip`). The lid holds without a latch and still lifts off
  by hand; finger notches under the lid edge help.
- **Flush lid joints.** Long lids are split into pieces with **scarf-lap
  joints** (slope about 39° from vertical): no gap, no steps, printed flat
  without supports. The joints lie in the middle of the base segments, so the
  lip bridges every base joint.
- **Two colours, no prime tower.** Base and keys in colour 1, lid and gates in
  colour 2, each colour on its own plates.
- **Vented lid.** Capsule slots keep the air moving; ribs under the strip lift it
  off the floor.
- **Wall or desk mounting.** Optional keyholes in the floor, one pair per
  segment; the screw heads sit inside, below the strip.
- **Support-free.** The base prints upright, the lid prints plate-down, the gates
  and keys print flat.
- **Three ready-made variants** with test-sliced Bambu Studio profiles for 3, 4
  and 5 walls (see [Print Recommendations](#print-recommendations)).

![Inside the box: strip, plugs, cables in the gates](images/03_innenansicht.jpg)

## Construction Details

The three joints that hold the box together, drawn from the default parameters
of the model (schematic, not to scale between the panels):

![Cable gate seat, lid scarf-lap joint and friction rib](images/05_construction-details.png)

- **Gate seat (left):** the notch in the end wall is widest in the middle of the
  wall thickness; the gate has the same shape with 0.15 mm play per side. Moving
  the gate by only a few tenths of a millimetre in either direction makes it
  touch the wall.
- **Lid joint (middle):** the left piece reaches over the right one; the
  0.2 mm gap keeps the pieces from touching. The sloped face leans at about 39°
  from vertical, so it prints without supports.
- **Friction rib (right):** the rib sticks out 0.35 mm from the lip (0.2 mm lid
  play plus 0.15 mm grip) and presses 0.15 mm into the wall.

## Parametric Options

The names correspond to the model's Customizer parameters.

### Power Strip and Plugs

| Parameter | Meaning | Default | Range / Unit |
|---|---|---|---|
| `strip_l` | Length of your power strip | 300 | 100–700 mm, step 5 |
| `strip_w` | Width of the strip | 55 | 30–160 mm |
| `strip_h` | Height of the strip without plugs | 38 | 15–120 mm |
| `plug_room` | Extra height above the strip for plugs and cables | 50 | 0–120 mm |
| `end_room` | Free room at each end for cables and plug bodies | 40 | 10–150 mm, step 5 |
| `side_clear` | Play between the strip and each long wall | 3 | 0–20 mm, step 0.5 |

### Cable Gates

| Parameter | Meaning | Default | Range / Unit |
|---|---|---|---|
| `cable_d` | Thickest cable that must pass a gate | 7 | 3–16 mm, step 0.5 |
| `gate_slots` | Snap-in cable slots per gate (one gate per end wall) | 2 | 1–5 |
| `slot_ratio` | Slot opening as a fraction of the cable diameter (smaller = the cable is held tighter) | 0.85 | 0.6–1, step 0.05 |

### Box and Lid

| Parameter | Meaning | Default | Range / Unit |
|---|---|---|---|
| `wall` | Wall thickness (a multiple of 0.4 mm prints cleanest) | 2.8 | 2–5 mm, step 0.4 |
| `floor_t` | Floor thickness (the keys sit in pockets in the underside) | 3.2 | 2.4–6 mm, step 0.4 |
| `corner_r` | Rounding of the vertical corners | 4 | 0–15 mm, step 0.5 |
| `cradle` | Cross ribs that lift the strip off the floor | on | on / off |
| `cradle_h` | Height of the ribs | 5 | 3–12 mm, step 0.5 |
| `lid_t` | Lid plate thickness | 2.4 | 1.6–4 mm, step 0.4 |
| `lip_h` | How far the lid lip reaches into the box | 6 | 3–15 mm |
| `lip_t` | Lip wall thickness | 1.6 | 1.2–3 mm, step 0.4 |
| `lid_fit` | Play between lid lip and walls, per side | 0.2 | 0.1–0.4 mm, step 0.05 |
| `lid_grip` | Friction grip: how far the ribs on the lip press into the walls (0 = loose lid) | 0.15 | 0–0.4 mm, step 0.05 |
| `vents` | Ventilation slots in the lid | on | on / off |
| `vent_w`, `vent_len` | Slot width and length | 4 / 30 | 2–8 mm / 10–60 mm |
| `pry_notch` | Finger notches in the front wall under the lid | on | on / off |

### Wall / Desk Mounting

| Parameter | Meaning | Default | Range / Unit |
|---|---|---|---|
| `mount` | Mounting holes in the floor | `keyholes` | `none`, `keyholes` |
| `screw_d` | Screw shank diameter | 4.2 | 3–6 mm, step 0.1 |
| `head_d` | Screw head diameter (the head sits inside, below the strip) | 8.5 | 6–12 mm, step 0.1 |

### Colours, Printer and Quality

| Parameter | Meaning | Default | Range / Unit |
|---|---|---|---|
| `two_colors` | Lid and gates in a second colour, each colour on its own plates | on | on / off |
| `color_body` | Colour of base and keys | `#2c2f36` | colour |
| `color_accent` | Colour of lid and gates | `#e8a21a` | colour |
| `printer` | Sets segment length and plate size: `P2S` (256 mm beds: P1S, P2S, X1C, A1), `H2C` (large bed, up to 296 mm), `A1M` (A1 mini, 180 mm bed). **Choose the same printer in the MakerWorld bed menu.** | `P2S` | selection |
| `$fn` | Circle quality | 48 | 24–96, step 8 |

## Design

### OpenSCAD Approach

The model is a single parametric OpenSCAD file. The outer length is
`strip_l + 2 × end_room + 2 × wall`. Everything is defined once for the **whole
box**; the segments are plain intersections of that box with slabs, so they add
up exactly to the unsplit box.

### Parametric Logic

- **Segments:** `ceil(length / usable bed length)` equal segments (248 / 296 /
  172 mm). A box that fits on one plate stays in one piece.
- **Lid pieces:** the joints of the lid lie in the middle of the base segments.
  Single-segment boxes have a single lid.
- **Plates:** every object (segment, key chunk, lid piece, gates) is listed once
  and packed in rows, tallest first, per colour group. Colour groups are packed
  on separate plates, so no plate mixes colours.

### Special Algorithms

- **Diamond gate seat:** the notch is a hexagon in plan view, widest in the middle
  of the wall, with flanks extended beyond the wall faces so the cut is
  manifold. The gate is the same shape without the 0.15 mm play.
- **Scarf-lap lid joints:** the plate of each lid piece is cut with a sloped
  profile that is extended beyond the plate faces; the lip is cut vertically,
  stops 0.4 mm before the scarf edge and sinks 0.4 mm into the plate. This avoids
  edges lying exactly in a face, which would break the mesh.
- **Friction ribs:** hulls of two thin boxes with a tapered lead-in at the lip
  tip; an even number per piece, so none sits on the finger notch in the middle.
- **Bow-tie keys:** pockets in the underside of the floor; the pocket ceiling is a
  short bridge of at most 9.3 mm.

### Print Optimisations

- No supports anywhere: base upright, lid plate-down with the lip up, gates and
  keys flat.
- No face is steeper than 45° from vertical in any print pose (checked on the
  geometry), including the lid joints and the gate flanks.
- Key pockets are short bridges (9 mm), which the profiles print cleanly.

## Print Recommendations

The profiles are built for the **Bambu Lab P2S** (and any 256 mm bed) and the
**H2C**, with PETG, 0.20 mm layer height and gyroid 15 %, and test-sliced in
Bambu Studio. Choose the same printer in the MakerWorld bed menu, because
MakerWorld only checks the selected bed.

| Setting | Recommendation |
|---|---|
| Material | **PETG or ASA** (heat); PLA is not recommended |
| Layer height | 0.20 mm |
| Walls | 3–5 (the profiles come with 3, 4 and 5) |
| Infill | 15 % gyroid |
| Supports | none |
| Plates | plate 1 base and keys in colour 1, swap the filament, plate 2 lid and gates in colour 2 |

| Variant | Strip it takes | Printer | Segments |
|---|---|---|---|
| `strip-150-compact` | 150 mm strip or a few plug-in adapters | P2S (any 256 mm bed) | 1 piece |
| `strip-300-p2s` | typical 6-way strip, 300 mm | P2S (any 256 mm bed) | 2 segments |
| `strip-450-h2c` | long 450 mm strip | H2C | 2 segments |

**Fit and tuning**

- The lid lip has 0.2 mm play per side, the gates 0.15 mm, the keys 0.15 mm and
  the lid joints 0.2 mm.
- The lid holds by friction. If it is too loose, raise `lid_grip` to 0.2–0.25; if
  it is too tight, lower it to 0.1 or change `lid_fit`. How firmly it sits
  depends on your printer and filament; test it with the first print.

**Assembly**

1. **Long boxes:** lay the base segments upside down, press the bow-tie keys into
   the pockets across the joints, then turn the box over. A drop of glue makes
   the keys permanent; on the wall or desk the surface holds them.
2. **Mount** (optional): put the box on the wall or under the desk and screw it
   through the keyholes.
3. Lay the power strip on the ribs and plug in the appliances.
4. Press every cable into a **gate slot** from above.
5. Slide each **gate** from above into its diamond seat in the end wall.
6. Put the **lid** on. To open it, pry with a fingernail or a screwdriver in the
   notch under the lid edge.

![Closed box, portrait format](images/02_hero-hochformat.jpg)

## Use Cases

- **Home office:** the power strip under the desk disappears, the cables leave
  through the gates.
- **Media corner:** TV, console and router on one strip, hidden behind the
  cabinet.
- **Workshop and hobby room:** a strip on the wall with keyholes, covered against
  dust.
- **Homelab and network corner:** a long box for a rack strip.
- **Compact variant:** 150 mm for a short strip or a few plug-in adapters.
- **Different printers:** the same design for the A1 mini (172 mm), 256 mm beds
  and the H2C; the number of segments is calculated for you.

## Troubleshooting / FAQ

| Symptom | Cause | Fix |
|---|---|---|
| The box is split although the strip is shorter than the bed | The box is longer than the strip: `strip_l + 2 × end_room + 2 × wall` | Reduce `end_room`, or accept the split; a box that fits on one plate is not split |
| The cable does not fit into the gate slot | Cable thicker than set | Increase `cable_d` |
| The cable falls out of the slot | Slot too wide for a thin cable | Lower `slot_ratio` |
| The gate is stiff to insert | The print comes out slightly larger | Deburr the gate edges and the elephant's foot |
| The lid is loose | The print comes out slightly smaller | Raise `lid_grip` to 0.2–0.25 |
| The lid is too tight | The print comes out slightly larger | Lower `lid_grip` to 0.1 or raise `lid_fit` |
| The box is too narrow for the gate | Gate wider than the box | Increase `strip_w` or `side_clear`, or reduce `gate_slots` or `cable_d` |
| The plugs do not fit under the lid | Not enough room above the strip | Increase `plug_room` |
| A plate is too big for the bed | Another printer than the selected one | Choose the matching printer in the MakerWorld bed menu |
| The box gets warm | The strip heats up | Keep the vents free, use PETG or ASA, never use it with high-load appliances |

## Development History

The box is a fully parametric design for FDM printing: any strip length, any
printer, two colours. The long box is cut into segments, the base joined by
bow-tie keys; the gates first sat in a one-sided dovetail seat.

In version 1.0.0 the gate seat became a **diamond-shaped double dovetail** that
locks in both directions, and the lid got **friction ribs** and **scarf-lap
joints**. All 8 test configurations (including H2C, A1 mini with 3 and 4
segments, a one-piece box, thick cables with four slots, no vents and one colour)
were checked automatically on the real geometry: no collisions between base,
lid, gates, keys, strip and a cable in every gate slot; gates lift out and are
locked in both directions; segments add up to the unsplit box (0.000 % volume
difference); every plate inside the bed, one colour per plate; no overhang steeper
than 45°. The profiles were rebuilt and test-sliced.

The images in this repository are renderings of the model geometry or scene
images derived from it; the power strip, plugs, cables and desk are simple
illustrations for context, not parts of the model. No photos of prints are
included.

## Downloads

Print files are intentionally available exclusively on MakerWorld.

👉 MakerWorld link: https://makerworld.com/en/models/3512557-cable-management-box#profileId-4013773

Profile: <https://makerworld.com/en/@BetaHydri>

## License

Documentation and images in this repository: © BetaHydri. The model (including
source code) and all print files are distributed exclusively via MakerWorld
under the license stated there. This repository deliberately contains no model,
source code or print files.
