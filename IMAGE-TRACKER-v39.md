# Vedere Travel — Image Tracker v39 (FINAL destination batch)
**Delivery:** vedere-site_42-final-destinations.zip · 2026-09-03
**Scope:** The `remaining` folder (163 files, 13 destinations) verified, placed, and the pages converted to the Dubai / Abu Dhabi image-card structure. This completes the destination image programme: **all 32 luxury destination pages are now live with photography.**

## Site-wide status after this delivery
- **168 hotel cards** in the full Dubai two-image layout across 32 destination pages.
- **18 cards remain text-led** — every one because a usable exterior or interior was missing or had to be rejected (list below). No page has an empty image slot anywhere.
- This batch: 122 images placed, 41 rejected/held.

## Rejected files — do not use (wrong place, watermark, or not photography)
1. `Japan/360_F_2006250735…jpg` — **AI-generated composite** (Fuji impossibly looming over Tokyo Tower + Skytree; Adobe Stock gen-AI) — violates the no-AI rule.
2. `Florida/16877961233880…jpg` — Estates at Acqualina **CGI rendering**, not photography.
3. `New england/one-dalton-dusk-hero-rendering…webp` — filename says it: a **rendering** of One Dalton.
4. `Kenya/african-sunset-acacia…webp` — **dreamstime watermark** tiled across the image.
5. `Botswana/aerial-view-okavango…260nw…webp` — **shutterstock.com watermark**, 628×280 preview file.
6. `New york/stock-photo-of-the-carlyle…G7GW2J.jpg` — **Alamy watermark** tiled across.
7. `California/pacific-coast-way-itinerary…png` — Magnetic Island, **Queensland, Australia** (left-hand traffic visible), not California.
8. `California/The Beverly Hills Hotel official press.jpg` — actually **The Maybourne Beverly Hills**, not The Beverly Hills Hotel.
9. `California/Meadowood press…interior.jpg` — a mid-market hotel lobby with a "SUITE SHOP" sign; **not Meadowood**.
10. `New york/images.jfif` — a valley city at dusk (looks Japanese); **not New York**.
11. `New england/images (1).jfif` — a tropical neon bay; **not New England**.
12. `Arizona/desert sunset wide.webp` — **camel caravan in the Sahara/Arabia**; wrong continent.
13. `Florida/images (1).jfif` — a freight train in Monument Valley; wrong region and subject.
14. `South Africa/pensione-la-calcina-venice-italy.webp` — **Venice, Italy**.

## Held — real and right, but too small for their slot (all under ~650px for a 1600px hero/band)
- Heroes kept on their existing asset: **south-africa** (Table Mountain cableway shot, 900×500 + cable car dominates), **botswana**, **bali** (rice terraces went to the About slot instead), **new-york**, **florida**, **new-england** (lighthouse 1094×438), **maldives-style band slots** on: kenya, botswana, thailand, japan, bali, new-york, california, florida, arizona, new-england.
- `Botswana/elephants-at-sunset.jpg` (1090×450), `Thailand/istockphoto…612x612` (612×374), `Bali/Uluwatu…avif` (1152×440), `Bali/1755544504703.jpg` (400×225), `NY/midtown…` (623×350), `Florida/images (2)(3)(5)` — all below the size floor for their slots.
- Unpaired hotel images held (card stays text-led until the partner arrives): SA Silo interior (`Suite2-TheSiloHotel…`, needs an exterior; `26e24031.avif` is 578px), SA La Residence exterior (needs an interior), Bali FS Sayan (`images.jfif` aerial + `814bc055…avif`, no interior), NY One Dalton interior (`images (2).jfif`, exterior was a render), NY The Mark (facade 500px + an unidentifiable modern room), Florida Setai/Surf Club interiors and Breakers exteriors (no partners), `Florida/BTS-Nov-2025…` (unidentifiable).

## Cards still text-led (18)
Barbados: coral-reef, sandpiper, cobblers-cove, colony-club · Grenada: calabash · Mexico: mandarina · South Africa: the-silo, la-residence · Bali: fs-sayan · New York: carlyle, the-mark · California: beverly-hills-hotel, meadowood · Florida: setai, surf-club, acqualina, breakers · New England: one-dalton.
**To finish these, send:** clean pairs (ext + int, ≥1100px wide) for each — plus the still-open slots from v38 (nordics/grenada/barbados bands, mauritius & south-africa heroes, Mandarina pair without logo plates) and heroes ≥1600px for botswana, bali, new-york, florida, new-england.

## Quality flags (used, replace when convenient)
- Small-source upscales that display fine at card size but are soft on retina: capella-ubud pair, bulgari-bali ext, aman-ny int, all four New England pairs, xv-beacon ext, kenya segera int & giraffe-manor pair, botswana jao ext & duba-plains int, sri-lanka amanwella ext, delaire-graff int, japan hero (night shot, forgiving), new-england/new-york/florida about images.
- `south-africa-band-01` is a **zebra sunset labelled Botswana** — used with an honest generic alt ("Zebra at sunset in the African bush"); swap for a true Sabi Sand dusk when available.
- Arizona hero was initially placed then **reverted**: the supplied Grand Canyon shot has a tourist crowd filling the frame — off-brand at hero size. Page kept its previous hero; file held.
- `japan-aman-tokyo-ext-01` uses the Aman Tokyo pool (signature view) as no true exterior was supplied.

## HTML changes in this batch (for the WordPress developer)
Same pattern as v38, applied to: sri-lanka, south-africa, kenya, botswana, thailand, japan, bali, vietnam, new-york, california, florida, arizona, new-england — hero/preload swap where a hero was placed (sri-lanka, kenya, thailand, japan, vietnam, california), about + figcaption on all 13, band on sri-lanka, south-africa, vietnam, and text-card → `.ht-imgs` conversion for every hotel with a full pair (50 cards this batch). No CSS changes required.
