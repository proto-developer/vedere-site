# Vedere Travel — Image Tracker v38
**Delivery:** vedere-site_41-destination-images.zip · 2026-09-03
**Scope:** Image Collection batch placed across 19 luxury destination pages, and all hotel cards with a full exterior + interior pair converted to the Dubai / Abu Dhabi image-card structure.

## Summary
- 302 files received in `Image Collection` · **292 placed** · 8 rejected · 2 rejected after placement (Mandarina badges).
- Pages updated: greece, italy, spain, portugal, france, montenegro, croatia, turkey, finland, nordics, barbados, st-lucia, antigua, grenada, british-virgin-islands, mexico, maldives, mauritius, seychelles.
- Hotel cards now in the Dubai image layout: **112** (Greece 22, Italy 14, Spain 9, Portugal 7, France 4, Montenegro 3, Croatia 4, Turkey 5, Finland 3, Nordics 4, Barbados 4, St Lucia 6, Antigua 3, Grenada 2, BVI 3, Mexico 3, Maldives 9, Mauritius 7, Seychelles 6).
- Cards still text-led (missing imagery): Barbados — coral-reef (no ext), sandpiper (no int), cobblers-cove (no int), colony-club (no ext); Grenada — calabash (no usable ext); Mexico — mandarina (badged photos rejected).
- Hero/about/band swapped to the new destination files on every page where supplied. Kept the existing asset where the slot was short (see below) — no empty slots anywhere.

## Rejected files (do not use)
1. `Grenada/ternate-dan-tidore-…webp` — Ternate & Tidore, **Indonesia**. Wrong country.
2. `Grenada/TAL-best-shopping-CALABASHNC0725…jpg` — Calabash, **North Carolina, USA** (a town, not the hotel).
3. `Barbados/Caribbean-Sunset-in-Excellence-Punta-Cana.jpg` — Excellence Punta Cana, **Dominican Republic**.
4. `Barbados/IMG_3959_resize.jpg` — a **New York City** brick mansion.
5. `Barbados/f4d30e9a-….jpg` — WindMark Beach, **Port St. Joe, Florida** (water-tower branding visible).
6. `Barbados/expedia_group-649867-….jpg` — unidentified rocky-coast property; matches no hotel in the Barbados collection.
7. `Mauritius/mauritius-helicopter-view-of-le-morne-…AMF08446.jpg` — **WESTEND61 watermark** baked across the image (stock comp).
8. `Mexico/oomandarina14…` & `oomandarina53…` — One&Only **logo plates baked into the image** ("14 / 53 One&Only Mandarina"); cannot be cropped out. Request clean press versions.
9. `Grenada/Penthouse+Living+Room-2.jpg` — good Calabash-style interior, but unused: no matching exterior, so the Calabash card stays text-led. Held for when an exterior arrives.

## Slots still needed (12)
- `nordics-band-01` (northern landscape dusk, 1600×900)
- `mauritius-hero-01` (Le Morne peninsula aerial — clean/licensed, 1600×900)
- `barbados-about-01`, `barbados-band-01`
- `barbados-coral-reef-ext-01`, `barbados-sandpiper-int-01`, `barbados-cobblers-cove-int-01`, `barbados-colony-club-ext-01`
- `grenada-band-01`, `grenada-calabash-ext-01`
- `mexico-mandarina-ext-01`, `mexico-mandarina-int-01` (clean, no logo plate)
- Plus the 13 destinations still to come: sri-lanka, south-africa, kenya, botswana, thailand, japan, bali, vietnam, new-york, california, florida, arizona, new-england (manifest lines 306–468).

## Quality / licence flags (usable, but replace when convenient)
- `finland-arctic-treehouse-ext-01` — source was a 739×415 thumbnail (1.77× upscale). Soft. Replace with the official Studio Puisto press exterior when possible.
- `seychelles-band-01` — 1024×682 source (1.56× upscale). Sits under the quote scrim, acceptable.
- `turkey-band-01` (Cappadocia) — 960×720 source (1.67× upscale). Acceptable under scrim.
- `british-virgin-islands-about-01` (The Baths) — sourced from an Imgur rip (`undefined - Imgur.jpg`). Correct location, but **licence unverified** — please confirm rights or replace with a BVI Tourist Board image.
- `maldives-hero-01` — the supplied aerial is Furaveri island; used as a generic Maldivian island aerial with a generic alt. Swap for a tourism-board atoll aerial if preferred.
- `mauritius-anahita-ext-01` — from a YouTube thumbnail (maxresdefault, clean image of the Anahita pool). Replace with press original when possible.
- Low-confidence hotel IDs (image looks right for the property but source filename was generic — please confirm): maldives soneva-jani-int, maldives reethi-rah-int, maldives waldorf-ithaafushi-int, mauritius royal-palm-int, mauritius dinarobin-int, mauritius touessrok-ext, seychelles north-island-int, barbados sandpiper-ext (garden pool — could be Coral Reef Club; the two are sister hotels).

## What changed in the HTML (for the WordPress developer)
Only the 19 destination pages listed above changed. In each:
1. **Head:** `<link rel="preload" as="image" …>` now points at the new `<slug>-hero-01.jpg` (where supplied).
2. **Hero:** the `<img class="hero-still" …>` src/alt/width/height (now 1600×900).
3. **About:** the `<figure><img …>` inside `<section id="about">` (now 1100×733), plus 7 figcaptions rewritten to match the new imagery.
4. **Band:** the `<section class="band"><img …>` src/alt (now 1600×900).
5. **Hotel cards:** `<article class="ht ht--text" id="X"><div class="ht-body">` became
   `<article class="ht" id="X"><div class="ht-imgs"><div class="ht-img"><img …ext-01.jpg…></div><div class="ht-img"><img …int-01.jpg…></div></div><div class="ht-body">`
   — identical to the Dubai/Abu Dhabi card markup. No CSS changes were needed (`.ht` grid styles already ship on every destination page).
All new assets live under `assets/img/luxury/<region>/<slug>/` with globally unique basenames, JPEG q74 progressive, exact slot dimensions.
