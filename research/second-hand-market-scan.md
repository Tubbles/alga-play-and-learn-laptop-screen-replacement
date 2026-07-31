# Research: second-hand availability and pricing

Web research performed by a Claude research agent 2026-07-31, followed by an orchestrator verification pass the same day (see corrections at the end). Claims cite URLs; marketplaces behind logins/JS could not be checked and are listed as such.

## Product identification (as used for searching)

- Official name: **"Alga Play & Learn Laptop"** (also listed as "Barndator (svenska och finska)", "Alga Laptop SE/FI", "Lärdator"). Brand Alga is part of BRIO AB.
- 45 activities, 6" backlit LCD, SE/FI keyboard, external mouse, 3×AAA, ages 4+. EAN 7070398092652 (per Babyland).
- Official manual PDF: <https://algaspel.se/wp-content/uploads/2024/09/Play_and_learn_manualalga_SE.pdf>
- Webhallen article number 140561.

## New-purchase availability (price ceiling reference)

**The product appears discontinued at every Swedish retailer checked. No confirmed source sells it new today.**

| Retailer | Accessible | Status | Price |
|---|---|---|---|
| Webhallen | Yes (via JSON API `https://www.webhallen.com/api/product/140561`; the HTML page is JS-only) | `discontinued: 1`, cannot be ordered, stock empty | Last listed price 399.00 SEK |
| Babyland | Yes — <https://www.babyland.se/alga_laptop_sefi> | "Produkten har utgått ur sortimentet" (discontinued) | 499 kr (historic page price) |
| Shopping4net | Yes — <https://www.shopping4net.se/Leksaker/Lek-Laer/Barn-PC/Alga-Play-Learn-Laptop.htm> | "Produkten har utgått", no price shown | — |
| CDON | Yes — brand page <https://cdon.se/varumarke/alga/> (125 Alga products, static HTML) | Not in assortment (board games only, no laptop) | — |
| Amazon.se | Search-index only | No Alga laptop found; only VTech/Lexibook equivalents (e.g. VTech Genio barndator) | — |
| Hinta.fi (FI price comparison) | Partially — <https://hinta.fi/747396/alga-play-learn-laptop> loads but shop/price data requires JS | Product page exists; no shops/prices retrievable | — |

Ceiling reference: **399–499 SEK was the retail price when in stock; it can no longer be bought new** from any verified source.

## Second-hand marketplaces

### Tradera — accessible: partially (item pages server-render; search pages are JS-only, see corrections)

- Known listings (all ended):
  1. **"Alga Play & Learn interaktiv laptop för barn"** — <https://www.tradera.com/item/340795/727111328/alga-play-learn-interaktiv-laptop-for-barn> (canonical item ID after redirect: 737847343) — auction, opening bid **110 SEK** (+49 SEK shipping), condition "Gott använt skick" (good used, minor wear), SE/FI keyboard + external mouse, seller **"Sayma"** (5.0 rating) in **Uppsala**. **Ended 2026-07-02 15:52 CEST with no bids** — did not sell at 110 kr.
  2. **"Barn dator Alga play & Learn"** — <https://www.tradera.com/item/340795/414400942/barn-dator-alga-play-learn> — expired; no price/condition recoverable.
  3. **"ALGA Play & Learn Lärdator"** — <https://www.tradera.com/item/340812/670943621/alga-play-learn-lardator> — expired; no details recoverable.
- The research agent additionally reported historic listings in the 75–390 SEK range (search-index evidence, not individually verifiable).

### Blocket — accessible: NO

Direct fetch refused and `site:blocket.se` returns nothing useful (Blocket is poorly search-indexed). **Presence or absence of listings unknown — needs a manual browser check.**

### Sellpy — accessible: NO (JS-only SPA)

Empty page body on fetch; nothing via search index. **Not verifiable without a browser.**

### Plick — accessible: search-index only

Only an Alga board game found; fashion-focused site, low prior for this item.

### Facebook Marketplace — accessible: NO (login wall)

Unchecked; likely worth a manual look given the item class.

### eBay — accessible: NO (fetch timeouts)

One possibly relevant hit (<https://www.ebay.com/itm/267400924478>) timed out on all fetch attempts and has no search snippet — **unverified, could be anything**. General searches return only unrelated generic kids' laptops.

### FINN.no (Norway) — accessible: title only (JS-blocked)

**"Alga Play & Learn Pc | FINN-torget"** — <https://www.finn.no/recommerce/forsale/item/467379146> — a listing for this product exists on the Norwegian marketplace; price/condition/status not retrievable without JS. Caveat from the product-identification research: the Norwegian unit may be a different language variant (the Swedish unit is bilingual SE/FI) — fine as a screen donor, but as a whole-unit swap it might not speak Swedish.

## Frequency assessment

**Rare-to-occasional.** Only 3 Tradera listings surfaced in total (all ended, none live as of 2026-07-31), 1 FINN.no listing, nothing confirmable elsewhere. Not an item with constant second-hand flow like Lexibook/VTech laptops — expect to wait or set a saved search. Demand is also low: the one fully documented listing ended at 110 kr with zero bids, so when a unit appears, expect roughly **100–200 SEK** (well under the 399–499 SEK former retail price).

## Orchestrator verification pass (2026-07-31, curl on the live Tradera pages)

- The old listing URL (727111328) 301-redirects to canonical item **737847343**, which is the same auction: og-title "Alga Play & Learn interaktiv laptop för barn", "Utropspris: 110 kr. Typ: Auktion. Slutar: 2026-07-02 15:52", schema.org offer **OutOfStock**, server JSON `isActive: false`, `openingBid: 110`, `visits: 93`, seller Sayma, Uppsala. Confirms: **ended 2026-07-02, unsold, no relist live**.
- A JSON block on that page that initially looked like an active relist (`isActive: true`, ends 2026-08-08, 6500 kr) is in fact a *different* item by the same seller ("Barnrumsmöbler med biltema", item 735604947) from the "more from this seller" carousel. Useful side-fact: **seller Sayma is still active on Tradera** and very likely still has the unsold laptop.
- Tradera search pages are client-side rendered — a curl of `/search?q=alga laptop` contains no result items, so "0 live listings" rests on the research agent's fetch, not on my curl.

## Practical takeaways

- Used is clearly the cheap path (~110 kr + ~49 kr shipping vs. discontinued retail), but **no unit is purchasable right now** on any fetchable marketplace.
- Best concrete lead: Tradera seller **Sayma (Uppsala)**, whose 110 kr auction ended 2026-07-02 with no bids — likely still owns the unit. Tradera supports following sellers and asking questions (requires an account; contacting them = outbound message, needs owner approval per ground rules).
- Owner-side manual checks this research could not perform (login/JS walls): Tradera saved search "alga laptop" / "alga lärdator", Blocket, Sellpy, Facebook Marketplace, and opening the FINN.no listing.
