# Research: product identification — Alga Play & Learn Laptop

Compiled 2026-07-31 from a Claude research agent's web sweep plus a first-hand read of the official 16-page Swedish manual (downloaded from algaspel.se, local copy in `tmp/alga_play_and_learn_manual_SE.pdf`, not committed). Manual-sourced claims below are first-hand verified; the rest cite URLs.

## Identity (one confirmed model, no evidence of other Alga laptop generations)

| Field | Value | Source |
|---|---|---|
| Product name | ALGA Play & Learn Laptop (retail: "Alga Laptop SE/FI", "Barndator svenska och finska") | [Manual](https://algaspel.se/wp-content/uploads/2024/09/Play_and_learn_manualalga_SE.pdf), [Webhallen](https://www.webhallen.com/se/product/140561-Alga-Play-Learn-Laptop-Barndator-svenska-och-finska), [Babyland](https://www.babyland.se/alga_laptop_sefi) |
| Alga/Scanditoy article no. | 38114300 | [Webhallen API](https://www.webhallen.com/api/product/140561); [Cision press image named 38114300](https://news.cision.com/se/alga/i/38114300,c1229861) |
| Supplier/model code | TA006-1-XX ("XX" looks like a language-variant placeholder) | [Shopping4net](https://www.shopping4net.se/Leksaker/Lek-Laer/Barn-PC/Alga-Play-Learn-Laptop.htm) |
| EAN | 7070398092652 (prefix 7070398 is a GS1 Norway range; holder unconfirmed) | [Babyland](https://www.babyland.se/alga_laptop_sefi), [Icecat](https://icecat.biz/sv/p/alga/laptop/kids-+electronics-7070398092652-play+-+learn+laptop-13535019.html) |
| Released | 2011 (manual PDF authored 2011-04; Webhallen lists release 2011-09-16) | [Webhallen API](https://www.webhallen.com/api/product/140561), PDF metadata |
| Status | Discontinued everywhere; last retail 399–499 SEK | see [second-hand-market-scan.md](second-hand-market-scan.md) |
| Features | 45 activities in 7 categories, ≤3 difficulty levels, SE/FI bilingual (SVE/FIN key), QWERTY with ÅÄÖ, clickable cursor pad + external wired mouse, ages 4+ | Manual (first-hand) |
| Power | 3×AAA alkaline, 4.5 V (manual battery figure shows three 1.5 V AAA; the text's "AAA/LR6" is an internal inconsistency — LR6 is actually AA) | Manual (first-hand) |

## Screen technology (manual evidence, first-hand)

**Monochrome passive-matrix dot-matrix LCD with switchable backlight** — all but confirmed:

- Cover diagram labels: "6″ LCD-skärm med belysning", **"Kontrast +/-"** buttons (contrast trim is characteristic of passive STN-class panels), and a dedicated keyboard key **"Bakgrundsbelysning — Slår På/Av bakgrundsbelysningen"** (user-toggleable backlight, consistent with a battery-budget mono panel, not a TFT).
- Every activity illustration in the manual (activities 01–45) is 1-bit black-on-pale dot-matrix graphics with free text, scrolling letters, and animations — requires a graphic dot matrix, rules out fixed-segment glass.
- No source anywhere describes a color screen.
- Caveat: resolution and active-area dimensions are unknown; the cover art suggests the active area is noticeably smaller than the decorated 6″ screen window. Only the teardown settles this.
- Remaining unknowns for the repair: panel construction (module vs. blob-driven raw glass), connection type, part numbers. No public teardown exists (explicitly searched, English + Swedish: iFixit, YouTube via search, Svenska ElektronikForumet, SweClockers, Swedroid, Familjeliv).

## Manufacturer / OEM

- Manual back page (first-hand): "Manufactured by/Tillverkare: **Scanditoy AB**, Box 305, SE-201 23 Malmö, Sweden, www.scanditoy.com" + "**Made in CHINA**". Scanditoy was the EU manufacturer-of-record, not the factory.
- Scanditoy AB was BRIO's Nordic distribution subsidiary and was **liquidated in 2014** ([BoardGameGeek](https://boardgamegeek.com/boardgamepublisher/33324/scanditoy), [BRIO history](https://www.fundinguniverse.com/company-histories/brio-ab-history/)).
- **The actual Chinese OEM is unidentified** despite targeted searching (model code "TA006", PDF metadata — generic template titled "USER'S MANUAL SUITABLE FOR CHILDREN", author "likih", no company name — and activity-list fingerprint searches in four languages). Lookalike leads that are *not* confirmed rebadges: Winfun "Let's Learn Bilingual Laptop" (different, 30 activities), Tech Kidz / LESHITIAN units (same genre, different firmware), Lexibook JC598 family (not a match).
- Consequence: the "find the same panel under another brand" shortcut has no known entry point until the teardown yields part numbers.

## Spare parts / service channel (option B input)

- Alga is a BRIO AB brand; BRIO owned by Ravensburger since 2015 ([Wikipedia](https://en.wikipedia.org/wiki/Alga_(game_publisher))).
- **BRIO explicitly does not sell spare parts** ("BRIO erbjuder inte reservdelar då leksaker måste följa extremt rigorösa säkerhetsstandarder") and routes warranty via the retailer — [BRIO FAQ](https://www.brio.se/sv-SE/kundservice/faqs) (page partly 403 to fetchers; claim from search snippets of that page).
- Alga customer service: [algaspel.se/kundservice](https://algaspel.se/kundservice/) — contact form; defective products: "take product and receipt to the store". Emails: info@algaspel.se (Alga), info@brio.net (BRIO AB, Skeppsbron 1, Box 305, 211 20 Malmö, tel +46 40 619 40 00).
- Mildly encouraging: Alga re-uploaded the laptop's manual in September 2024 and still lists it on their [manuals page](https://algaspel.se/catalog/), so the brand acknowledges the product — but with the manufacturer-of-record liquidated and BRIO's no-spares policy, option B is a long shot. A polite ask via the contact form costs little (needs owner approval to send).

## Loose ends

- OEM identity / rebadge existence: unconfirmed.
- Panel type, resolution, part numbers: unknown until teardown.
- Norwegian variant details (FINN.no listing) and its firmware language: unconfirmed.
- The "Alga Learning" [YouTube playlist](https://www.youtube.com/playlist?list=PL44059309ABE2EB80) exists but was behind a consent wall — might contain footage of the powered-on screen (resolution clues) if opened in a browser.
