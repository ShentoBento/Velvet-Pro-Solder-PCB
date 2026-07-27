# Velvet Pro Solder PCB

<img src="images\VP_Solder_Front_Render.png" width="700">

A solder PCB designed to fit the Velvet Pro keyboard by Ampersandy.

Firmware: https://github.com/ShentoBento/Velvet-Pro-PCB-Firmware

---

## Specs

- Solder
- MCU: STM32F072CBTx
- JST SH 4-pin connector (for C3 Unified Daughterboards)
- Fixed ANSI enter
- Fixed 7u bottom row
- Fixed split right shift
- Stepped or full caps lock
- Split or full backspace
- VIA and Vial compatible (via the firmware linked above)

---

## Requirements

- **KiCad 10** or newer. Earlier versions will not open these files.
- Nothing else. All symbols, footprints, and 3D models used by this project are
  included in this repo — no external libraries to install, no PCM packages,
  no library paths to configure.

---

## Opening the project

1. Clone or download this repo.
2. Open `VP_Solder_KiCad/VP_Solder.kicad_pro` in KiCad.

The library paths are stored relative to the project folder, so the repo works
from any location on any operating system. If KiCad reports missing symbols or
footprints, the most likely cause is that the `shentobento_kicad_library/`
folder was not cloned alongside `VP_Solder_KiCad/`.

---

## What's in this repo

### `VP_Solder_KiCad/`

The KiCad project. These are the files you edit.

| File | What it is |
|---|---|
| `VP_Solder.kicad_pro` | Project file — **open this one** |
| `VP_Solder.kicad_sch` | Schematic |
| `VP_Solder.kicad_pcb` | Board layout |
| `fp-lib-table`, `sym-lib-table` | Point KiCad at the bundled library |
| `fabrication-toolkit-options.json` | Settings for the JLCPCB fabrication plugin |

### `VP_Solder_KiCad/production/`

Ready-to-order manufacturing files, generated with the JLCPCB Fabrication Toolkit plugin.

| File | Upload it to |
|---|---|
| `VP_Solder.zip` | JLCPCB's gerber upload — this is the board itself |
| `bom.csv` | Assembly service (which parts) |
| `positions.csv` | Assembly service (where they go) |

If you modify the design, **regenerate these** rather than reusing them. Stale
production files that don't match the current board are how wrong PCBs get
manufactured.

### `shentobento_kicad_library/`

Every symbol and footprint this project uses, in one place.

- `shentobento.kicad_sym` — all symbols
- `shentobento.pretty/` — all footprints
- `3dmodels/` — 3D models for the parts that need them

Symbols come with their footprints pre-assigned, so dragging a part into a
schematic gives you a working part with no footprint assignment step.

This folder is self-contained and can be copied into other keyboard projects.

### `reference files and images`

Not needed to build the board — useful if you're modifying the layout.

- `Plate_File_No_Flex_Cuts.dxf` / `Plate_File_with_Flex_Cuts.dxf` — the official
  Velvet Pro plate files, used to align switch and stabilizer positions
- `VP PCB DXF.dxf` — the official board outline, thanks to Andykit
- Various images of the PCB and schematic

---

## Credits and licenses

Keyboard footprints and symbols are derived from
[marbastlib](https://github.com/ebastler/marbastlib) by ebastler, licensed under
CERN-OHL-P v2. See `shentobento_kicad_library/LICENSE-marbastlib.txt`.

Generic footprints (passives, SOT-23, LQFP-48, JST SH, test points) are copied
from the KiCad standard libraries.

Modifications made to third-party files are recorded in
`shentobento_kicad_library/NOTICE.md`.

The Velvet Pro case and plate files are the work of Ampersandy.
