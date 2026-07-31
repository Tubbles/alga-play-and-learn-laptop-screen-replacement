# Plan: Alga Play & Learn Laptop — screen replacement

## Goal

The Alga (Swedish toy brand, BRIO group) "Play & Learn" kids laptop has a broken ~6" LCD. Get the toy working again with a functioning screen, by whatever route is cheapest in owner time. Owner time is the scarce resource; money and elegance are secondary.

## Ground rules

- No purchases and no online posts (forum asks, marketplace bids, support tickets) without explicit owner approval.
- Owner does physical tasks (photos, teardown, probing) in batched sessions — collect everything needed per session up front so each session counts.
- Every decision goes in [LOG.md](LOG.md).

## Status (2026-07-31 — research phase complete)

All three research tracks are done: [product identification](research/product-identification.md), [second-hand market scan](research/second-hand-market-scan.md), [LCD repair landscape](research/lcd-replacement-landscape.md). Where we stand:

- **Product identified: ALGA Play & Learn Laptop** ("Alga Laptop SE/FI", article 38114300, model TA006-1-XX, EAN 7070398092652, released 2011, bilingual SE/FI, 3×AAA). Discontinued at every retailer (last price 399–499 SEK). Owner's label photo will confirm the variant.
- **Screen: monochrome passive-matrix dot-matrix LCD with switchable backlight** (per the official manual: contrast trim, backlight toggle key, 1-bit activity graphics). Resolution, active area, construction, and part numbers unknown — no public teardown exists; ours will be the first.
- **Triage (owner): cracked glass from a drop** — panel or whole unit must be replaced.
- **Option A lead:** one Tradera auction (seller "Sayma", Uppsala) ended 2026-07-02 **unsold at 110 kr opening bid**; the seller is still active on Tradera and likely still has the unit. Item appears second-hand only rarely; expected price 100–200 kr. Blocket/Sellpy/Facebook Marketplace are login-walled — owner check needed. A Norwegian FINN.no listing exists (possibly a non-Swedish language variant — fine as screen donor, not as whole-unit swap).
- **Option B weakened:** manufacturer-of-record Scanditoy AB was liquidated in 2014; BRIO officially sells no spare parts. Only a long-shot ask via Alga's contact form remains.
- **OEM unidentified** despite fingerprint searches — no known rebadge to source parts from until the teardown yields part numbers.

## Next actions

1. **Owner (one ~2 min session):** photo of the back/bottom label and of the open unit showing the screen — confirms variant, ends speculation about the screen window vs. active area.
2. **Owner decision:** hunt a donor unit now? Concretely: set a Tradera saved search ("alga laptop", "alga lärdator"), optionally message seller Sayma about the unsold 110 kr unit, and glance at Blocket/Sellpy/FB Marketplace (all need your logins; messaging the seller needs your explicit go-ahead per ground rules).
3. **Owner (one longer session, ~20–30 min, whenever it suits):** teardown — open the unit, photograph mainboard, panel front/back, every silkscreen/flex/glass marking. This decides options C/D/E definitively and is worth doing even if a donor shows up (documents the repair for the next person; ours would be the first public teardown of this toy).
4. **Claude:** on teardown photos — hunt part numbers; on donor decision — prep a saved-search/contact text for approval.

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

### A. Buy a complete second-hand unit — CURRENT FRONT-RUNNER

Swap the whole toy, or transplant its screen into the existing chassis. Scan result: discontinued new (no price ceiling to buy at), rare second-hand, expected 100–200 kr when one appears. Concrete lead: Tradera seller **Sayma (Uppsala)**, auction ended 2026-07-02 unsold at 110 kr + 49 kr shipping, "gott använt skick", seller still active on Tradera. Plus one FINN.no listing (language variant unconfirmed). Blocket, Sellpy, and Facebook Marketplace are unchecked (login walls) — owner glance needed. Strategy: saved search + optionally message the Uppsala seller (owner approval required for any contact/purchase).

### B. Spare part from Alga/BRIO customer service — LONG SHOT

Research result: manufacturer-of-record Scanditoy AB liquidated 2014; BRIO's official policy is no spare parts, warranty via retailer. Alga still hosts the product's manual (re-uploaded Sept 2024), so a polite ask via [algaspel.se/kundservice](https://algaspel.se/kundservice/) costs five minutes and might reach someone with a warehouse remnant — but expect nothing. (Sending requires owner approval per ground rules.)

### C. Identical replacement LCD module

Open the unit, read every part number (panel glass silkscreen, flex print, mainboard silkscreen, controller ICs), and hunt for the exact module on AliExpress/eBay/Taobao (LCSC is a long shot for mono modules; panelook only if it turns out to be a branded module or TFT). Toy laptops are usually rebadged OEM designs sold under many brands, so the panel may be commodity; even an internal-looking number on the glass is worth searching verbatim. Requires one owner teardown session with good photos; soldering may be zero (connector) or moderate. Heatseal-flex-bonded or blob-driven raw glass = this option dies at inspection (ACF re-bonding is specialist territory).

### D. Electrically compatible panel + adaptation

Only possible if the mainboard talks a *controller protocol* to the panel (some toy laptops do, e.g. VTech PreComputer 2000 uses an HD44780); if the blob ASIC drives raw glass with multiplexed waveforms there is nothing to adapt to and this option is dead. Confirming which case applies needs a logic-analyzer capture on the panel connection (owner session, sigrok/PulseView). Precedent exists for protocol-bridging to a modern panel via a microcontroller (Kerry Wong's Uniden LCD reverse-engineering). Meaningful effort — only if A–C fail and the toy is worth it. Generic ~6″ mono modules do exist if the protocol matches (5.7″ 320×240 RA8835 class; a 6″ 320×240 NT7086 module at displaymodule.com is dimensionally closest).

### E. Retrofit / brain transplant

Keep the chassis and keyboard, replace screen and electronics (e.g. Pi + generic 5″ HDMI touchscreen re-implementing some play-and-learn games; the original educational firmware is lost). Well-trodden path — see the PinkPad VTech conversion and similar builds linked in the research notes. Fun project but by far the most owner time; explicitly last resort given the time constraint.

## Decision gates

1. ~~**Triage result**~~ — PASSED 2026-07-31: cracked glass, panel replacement required.
2. **Donor unit found at sane price** (saved searches, Sayma, login-walled marketplaces): owner approves → buy → done on arrival. No unit purchasable as of 2026-07-31.
3. **Service channel** (only if owner wants to fire off the form): Alga answer with a part or unit → done. Expectation set to "no".
4. **Teardown findings**: panel part number searchable → option C; recognizable controller protocol only → option D; heatseal custom glass or blob-driven raw glass with no matches → option E or accept a donor-only strategy (keep marketplace watches running).
