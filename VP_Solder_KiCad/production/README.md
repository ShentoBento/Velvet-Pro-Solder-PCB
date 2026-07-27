# How to order this PCB from JLCPCB

You do **not** need KiCad for this. Everything you need is in
`VP_Solder_KiCad/production/`.

---

## What you need

| File | What it's for |
|---|---|
| `VP_Solder.zip` | The board itself. Required. |
| `bom.csv` | Which parts to solder on. Only needed for assembly. |
| `positions.csv` | Where those parts go. Only needed for assembly. |

If you're soldering the components yourself, you only need `VP_Solder.zip`.

---

## Ordering from JLCPCB with Assembly

1. Go to [jlcpcb.com](https://jlcpcb.com), click order, and then **Add gerber file**.
2. Upload `VP_Solder.zip`.
3. Wait for the preview to load, then check it against the images in this
   repo's README. The board outline should match.
4. Leave the defaults alone unless you want a specific colour. The defaults
   (1.6mm thickness, HASL, 2 layers, FR4) are correct for this board. 1.2mm
   also works but you will need stabilizer shims. Don't change anything in the
   **High-Spec Options** section.
6. Toggle **PCB Assembly** on.
7. Choose **Assemble bottom side** — all components on this board are on the bottom.
   You will need to choose the **Standard** PCBA option, keep other options as default
   (Parts Selection by customer, OPTIONAL: Confirm parts placement).
9. CLick **Save to Cart** and you will see a preview of the PCB, click next, and
   upload `bom.csv` when asked for the BOM and `positions.csv` when asked for the
   CPL / pick-and-place file. Then click **Process BOM & CPL**.
11. JLCPCB will show you each part and whether it's in stock. Parts that are
   out of stock need a substitute or must be hand-soldered.
12. Review the component placement preview. Check that the MCU's pin 1 marker
   lines up with the silkscreen dot.

---

## After it arrives

Flash the firmware:
https://github.com/ShentoBento/Velvet-Pro-PCB-Firmware
