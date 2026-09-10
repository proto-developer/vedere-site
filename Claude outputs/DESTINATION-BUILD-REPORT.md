# Vedere Travel — Luxury Destination Build (Master Inventory v5)

**Build `vedere-site_39` · 3 September 2026.** 32 destination pages added; site is now 93 pages.

## What was built

Every destination in the Master Inventory now has a dedicated page on the Dubai master template
— same section order (hero → about → editorial band → when-to-travel months table → hotels →
itineraries → getting there → combinations → why Vedere → FAQ → enquire), same components,
same enquiry form.

| Region | Pages |
|---|---|
| Europe (10) | greece · italy · spain · portugal · france · montenegro · croatia · turkey · finland · nordics |
| Caribbean (6) | barbados · st-lucia · antigua · grenada · british-virgin-islands · mexico |
| Indian Ocean (4) | maldives · mauritius · seychelles · sri-lanka |
| Africa (3) | south-africa · kenya · botswana |
| Asia (4) | thailand · japan · bali · vietnam |
| North America (5) | new-york · california · florida · arizona · new-england |

**Hotels:** all 154 approved hotels are on their pages with location, positioning line and
"Why we selected it" — as **untiered text-led cards**, per two rules that bind together: the
inventory's "do not assign tiers yourself" and "hotel imagery from press offices only". Each
hotels section carries a one-line note that tiering and property photography follow with the
region pack. When each pack arrives, I drop the images in and group the tiers — no rebuild.

**Structure notes honoured:** Greece, Portugal and South Africa carry the area-tab bar
(sticky jump strip built from the existing signed-off strip component — flagging that the
bespoke tabs design remains a sign-off item); the three Africa pages carry the
"Suggested Safari Routes" block; Nordics covers Iceland/Norway/Sweden with Finland separate;
Mexico sits under the Caribbean; France is summer-only; Montenegro's optional extensions and
Mandarin Oriental Bodrum are noted as pending sign-off in page copy; Burj Al Arab is not listed.

**Cross-links built:** Italy ⇄ European Football Breaks (Como 1907) · France ⇄ Roland-Garros ·
New York ⇄ US Open & US Sports · Arizona ⇄ WM Phoenix Open · South Africa & Kenya ⇄ England
Cricket Tour. Dubai's Maldives/Seychelles combination cards now reach real pages (two of the
old intentional 404s retired).

**Navigation rewired site-wide (all 93 pages):** 2,760 mega-menu destination buttons now open
their destination page directly; 9,282 mega-menu hotel links deep-link to that hotel's card
(e.g. Amanzoe → greece.html#amanzoe); region-page destination cards now read "Explore Greece"
and link through (33 cards); 21 featured-hotel cards deep-link to their hotel entries.
Sitemap extended to 93 URLs.

**Imagery:** built entirely from photography already on the site — each hero is that
destination's existing approved frame; no AI imagery, no new demands, no empty slots,
no placeholders. Pages average 4 images (hero, about, band + region texture) by design until
press-office packs arrive; the image-per-page count then rises with the packs.

## Verified

0 missing images · 0 unresolved anchors (all 9,282 hotel deep-links resolve) · 0 placeholders ·
0 horizontal scroll at 1440/390 · mega menus, drawers, FAQ accordions and forms pass on all 32
new pages · SEO head standard passes 93/93 (titles 50–60, descriptions 140–160, canonical
`/luxury-travel/<region>/<slug>`, OG/Twitter, hero preload) · schema per page type
(TouristDestination + BreadcrumbList + FAQPage + TravelAgency, FAQ matching visible questions)
· no pricing on any luxury destination page · analytics label = page slug on every new page.

## Open (needs Vedere, unchanged from inventory)

Tier assignments per hotel · region packs with press-office photography · area-tabs and
safari-route bespoke designs · Montenegro extensions and MO Bodrum include/hold ·
North America commercial pass · the non-destination pages (Tickets & Concierge, Honeymoons,
Why Vedere, Vedere Circle, Team Travel, thank-you/404/legal).
