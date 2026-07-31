# Plan: Alga Play & Learn Laptop — screen replacement

## Goal

The Alga (Swedish toy brand, BRIO group) "Play & Learn" kids laptop has a broken ~6" LCD. Get the toy working again with a functioning screen, by whatever route is cheapest in owner time. Owner time is the scarce resource; money and elegance are secondary.

## Ground rules

- No purchases and no online posts (forum asks, marketplace bids, support tickets) without explicit owner approval.
- Owner does physical tasks (photos, teardown, probing) in batched sessions — collect everything needed per session up front so each session counts.
- Every decision goes in [LOG.md](LOG.md).

## Status

- 2026-07-31: Repair-landscape research done → [research/lcd-replacement-landscape.md](research/lcd-replacement-landscape.md). Product candidate: **"Alga Laptop SE/FI"** (ages 3–6, "6″ LCD-skärm med bakgrundsbelysning", 45 activities, 3×AAA — [babyland.se](https://www.babyland.se/alga_laptop_sefi)); owner to confirm against the unit's label. Screen is *likely* mono passive-matrix from an anonymous OEM (inference from power budget and price class, unverified). Key consequence for us: with cracked glass, everything hinges on whether the teardown reveals a swappable module with a searchable part number (→ option C) or custom glass driven raw by a blob ASIC (→ options collapse to A/B or E; D only works if a discrete controller protocol exists on a flex). No Alga-specific teardown exists online.
- 2026-07-31: Triage resolved by owner: cracked glass from a drop/impact. The panel must be replaced (or the whole unit); no cheap contact/backlight fix applies. Gate 1 passed, working options A–E.
- 2026-07-31: Project started. Three research tracks running: product identification (exact model, OEM origin, screen tech, teardowns, spare-part channels), Swedish second-hand market scan (Tradera/Blocket/Sellpy/eBay + new-unit price), and generic toy-LCD repair/replacement landscape. Awaiting results and first info from owner.

## Step 0 — Triage — RESOLVED 2026-07-31: cracked glass (drop/impact), panel replacement required

"Broken LCD" covers several different failures, and some of them do not need a new panel at all:

| Symptom | Likely fault | Fix difficulty |
|---|---|---|
| Ink blots, spider cracks, black splotches | Cracked LCD glass | Panel must be replaced — no repair possible |
| Missing rows/columns/segments, works when case is squeezed | Zebra-strip / flex connector contact | Often fixable free: open, clean, reseat |
| Image visible only faintly / at an angle, unit otherwise works | Dead backlight (if it has one) | Cheap fix, replace LED/foil |
| Rainbow/dark stains but glass intact | Damaged polarizer film | Replaceable film, cheap |
| Completely blank, no damage visible | Could be electronics, not the panel | Needs diagnosis before buying anything |

Owner confirmed 2026-07-31: cracked glass / ink blots after a drop or impact. Rows 2–5 of the table are ruled out. Still needed from owner (one batch): photo of the back/bottom label (model name + article/EAN numbers) for product identification, and a photo of the open unit showing the screen.

## Options, easiest first

Work down this list; stop at the first one that pans out.

### A. Buy a complete second-hand unit

Swap the whole toy, or transplant its screen (or whole mainboard+screen) into the existing chassis if the original has sentimental value. Sources: Tradera, Blocket, Sellpy, Facebook Marketplace, eBay; buying a *new* unit is the price ceiling if it is still sold. Near-zero tinker time, biggest question is availability. Market scan in progress.

### B. Spare part from Alga/BRIO customer service

Toy makers sometimes ship replacement units or parts cheaply, especially within warranty-friendly Nordic consumer law. One email costs almost nothing. Contact channel being researched. (Sending the email requires owner approval per ground rules.)

### C. Identical replacement LCD module

Open the unit, read every part number (panel glass silkscreen, flex print, mainboard silkscreen, controller ICs), and hunt for the exact module on AliExpress/eBay/Taobao (LCSC is a long shot for mono modules; panelook only if it turns out to be a branded module or TFT). Toy laptops are usually rebadged OEM designs sold under many brands, so the panel may be commodity; even an internal-looking number on the glass is worth searching verbatim. Requires one owner teardown session with good photos; soldering may be zero (connector) or moderate. Heatseal-flex-bonded or blob-driven raw glass = this option dies at inspection (ACF re-bonding is specialist territory).

### D. Electrically compatible panel + adaptation

Only possible if the mainboard talks a *controller protocol* to the panel (some toy laptops do, e.g. VTech PreComputer 2000 uses an HD44780); if the blob ASIC drives raw glass with multiplexed waveforms there is nothing to adapt to and this option is dead. Confirming which case applies needs a logic-analyzer capture on the panel connection (owner session, sigrok/PulseView). Precedent exists for protocol-bridging to a modern panel via a microcontroller (Kerry Wong's Uniden LCD reverse-engineering). Meaningful effort — only if A–C fail and the toy is worth it. Generic ~6″ mono modules do exist if the protocol matches (5.7″ 320×240 RA8835 class; a 6″ 320×240 NT7086 module at displaymodule.com is dimensionally closest).

### E. Retrofit / brain transplant

Keep the chassis and keyboard, replace screen and electronics (e.g. Pi + generic 5″ HDMI touchscreen re-implementing some play-and-learn games; the original educational firmware is lost). Well-trodden path — see the PinkPad VTech conversion and similar builds linked in the research notes. Fun project but by far the most owner time; explicitly last resort given the time constraint.

## Decision gates

1. **Triage result** (owner photos): if the fault is contact/backlight/polarizer → fix directly, skip A–E.
2. **Market scan result**: if a used unit exists at a sane price → recommend purchase (owner approves), done on arrival.
3. **Service channel result**: if Alga/BRIO answer with a part or unit → done.
4. **Teardown findings**: panel part number searchable → option C; recognizable controller only → option D; heatseal custom glass, no matches → option E or accept a used-unit-only strategy (watch marketplaces).
