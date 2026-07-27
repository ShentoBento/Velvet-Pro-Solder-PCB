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

## Ordering the bare board

1. Go to [jlcpcb.com](https://jlcpcb.com) and click **Add gerber file**.
2. Upload `VP_Solder.zip`.
3. Wait for the preview to load, then check it against the images in this
   repo's README. The board outline should match.
4. Leave the defaults alone unless you want a specific colour. The defaults
   (1.6 mm thickness, HASL finish, 2 layers) are correct for this board.
5. Add to cart and check out.

---

## Ordering with assembly

Same as above, then:

1. Toggle **PCB Assembly** on before adding to cart.
2. Choose **Assemble top side** — all components on this board are on the top.
3. Continue, and upload `bom.csv` when asked for the BOM and `positions.csv`
   when asked for the CPL / pick-and-place file.
4. JLCPCB will show you each part and whether it's in stock. Parts that are
   out of stock need a substitute or must be hand-soldered.
5. Review the component placement preview. Check that the MCU's pin 1 marker
   lines up with the silkscreen dot.

Note that switches, stabilizers, and the JST connector are **not** assembled —
those you solder yourself.

---

## After it arrives

Flash the firmware:
https://github.com/ShentoBento/Velvet-Pro-PCB-Firmware

---

## If something looks wrong in the preview

Don't order. Open an issue on this repo with a screenshot of what you're
seeing. A wrong board costs more than a delay.
