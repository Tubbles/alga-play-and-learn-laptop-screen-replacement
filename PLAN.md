# Plan: Alga Play & Learn Laptop — screen replacement

## Goal

The Alga (Swedish toy brand, BRIO group) "Play & Learn" kids laptop has a broken ~6" LCD. Get the toy working again with a functioning screen, by whatever route is cheapest in owner time. Owner time is the scarce resource; money and elegance are secondary.

## Ground rules

- No purchases and no online posts (forum asks, marketplace bids, support tickets) without explicit owner approval.
- Owner does physical tasks (photos, teardown, probing) in batched sessions — collect everything needed per session up front so each session counts.
- Every decision goes in [LOG.md](LOG.md).

## Status

- 2026-07-31: Project started. Three research tracks running: product identification (exact model, OEM origin, screen tech, teardowns, spare-part channels), Swedish second-hand market scan (Tradera/Blocket/Sellpy/eBay + new-unit price), and generic toy-LCD repair/replacement landscape. Awaiting results and first info from owner.

## Step 0 — Triage (do this before committing to any option)

"Broken LCD" covers several different failures, and some of them do not need a new panel at all:

| Symptom | Likely fault | Fix difficulty |
|---|---|---|
| Ink blots, spider cracks, black splotches | Cracked LCD glass | Panel must be replaced — no repair possible |
| Missing rows/columns/segments, works when case is squeezed | Zebra-strip / flex connector contact | Often fixable free: open, clean, reseat |
| Image visible only faintly / at an angle, unit otherwise works | Dead backlight (if it has one) | Cheap fix, replace LED/foil |
| Rainbow/dark stains but glass intact | Damaged polarizer film | Replaceable film, cheap |
| Completely blank, no damage visible | Could be electronics, not the panel | Needs diagnosis before buying anything |

Needed from owner (one batch): photos of the unit powered on showing the fault, the back/bottom label (model + article/EAN numbers), and a note on how it broke (dropped? sat on? just stopped?).

## Options, easiest first

Work down this list; stop at the first one that pans out.

### A. Buy a complete second-hand unit

Swap the whole toy, or transplant its screen (or whole mainboard+screen) into the existing chassis if the original has sentimental value. Sources: Tradera, Blocket, Sellpy, Facebook Marketplace, eBay; buying a *new* unit is the price ceiling if it is still sold. Near-zero tinker time, biggest question is availability. Market scan in progress.

### B. Spare part from Alga/BRIO customer service

Toy makers sometimes ship replacement units or parts cheaply, especially within warranty-friendly Nordic consumer law. One email costs almost nothing. Contact channel being researched. (Sending the email requires owner approval per ground rules.)

### C. Identical replacement LCD module

Open the unit, read every part number (panel glass silkscreen, flex print, mainboard silkscreen, controller ICs), and hunt for the exact module on AliExpress/eBay/LCSC/Taobao. Toy laptops are usually rebadged OEM designs sold under many brands, so the panel may be commodity. Requires one owner teardown session with good photos; soldering may be zero (connector) or moderate (heatseal flex = likely dead end, decided at inspection).

### D. Electrically compatible panel + adaptation

If the exact module is gone but the controller family is identifiable, a same-controller same-resolution panel can work. May require logic-analyzer capture of the panel bus (owner session) to confirm interface and init sequence. Meaningful effort — only if A–C fail and the toy is worth it.

### E. Retrofit / brain transplant

Keep the chassis, replace screen and electronics (e.g. microcontroller or Pi + generic TFT re-implementing some play-and-learn games). Fun project but by far the most owner time; explicitly last resort given the time constraint.

## Decision gates

1. **Triage result** (owner photos): if the fault is contact/backlight/polarizer → fix directly, skip A–E.
2. **Market scan result**: if a used unit exists at a sane price → recommend purchase (owner approves), done on arrival.
3. **Service channel result**: if Alga/BRIO answer with a part or unit → done.
4. **Teardown findings**: panel part number searchable → option C; recognizable controller only → option D; heatseal custom glass, no matches → option E or accept a used-unit-only strategy (watch marketplaces).
