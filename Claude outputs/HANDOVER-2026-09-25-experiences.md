# Vedere — Experiences pages (25 September 2026)

Follows `HANDOVER-2026-09-22.md`. Adds the Experiences section requested by the client, built from the
image pack `Vedere-Experiences-Website-Images-Revised` (24 September 2026) and its placement guide.

## 1. What was added

| Item | Detail |
|---|---|
| `/experiences` | Hub page built on the Sports Travel hub template: 3-slide hero (Teatro del Silenzio, Bocelli stage, Glastonbury), intro band, featured journeys, Tuscan band, five experience cards (Andrea Bocelli, Sphere Residencies, Glastonbury, Coachella, Fashion Week), approach, corporate/sports promo, luxury cross-sell, why, reviews, Founders Club, FAQ, enquiry |
| `/experiences/andrea-bocelli-2027` | Event page built on the Austin template, section for section: hero, band, four packages, included, about, venue, ticket guide, four hotels, destination, climate, extensions, why, FAQ, enquiry |
| Navigation | "Experiences" tab between Luxury Travel and About in the desktop mega-menu (drop-down to the five experiences), in the mobile drawer, and as a footer link — on all 109 pages |
| Search | Six entries added to `assets/js/vx-search.js` |
| Sitemap / redirects | Two URLs in `sitemap.xml`; `/xperiences`, `/andrea-bocelli-2027` and `.html` variants 301 in `vercel.json` |
| Images | 20 pack images placed (32 files including hero WebP variants); logged in `IMAGE-PLACEMENT-RECORD.csv` |
| WordPress | `wordpress-build-v1.7.1/` — full theme in part zips, plus an update-only zip for sites already on 1.7.0 |

## 2. Facts to confirm with the client

1. **Bocelli 2027 dates and ticket categories** are not yet published by the organiser. The page says "July 2027 · dates to be confirmed"
   and all four packages are "On application". Ticket category names (Grandstand, Numbered Seat, Premium Seat, Executive Hospitality)
   are descriptive and should be aligned to the organiser's sector names once released.
2. **Hotel details** (room categories quoted, drive times to Lajatico, star ratings) were written from the pack notes and public
   information; the four properties should be checked against contracted rates and room types before quoting.
3. **Flights**: routings are shown as approximate durations, following the Monaco page pattern; no specific timetables.
4. **Glastonbury** copy states plainly that tickets are sold only by the festival and that Vedere holds no allocation.
5. **Executive Hospitality image** (pack slot 15) was not supplied; no hospitality photograph is used.
6. **Contact, ATOL and Booking Conditions** pages have no mobile drawer markup (pre-existing); the Experiences tab is in their desktop
   header and footer only. The Formula One hub footer is a race list with no "Vedere" column, so it carries no footer link.

## 3. Image handling

The Teatro del Silenzio aerial is a 1977px original (no upscaling), so its largest WebP variant is labelled 1977w rather than 2400w.
Castelfalfi's hotel card combines the pack's Tabaccaia bedroom and Giglio Blu pools (captioned as a shared estate amenity) with the borgo photograph.
The gala photograph is captioned as the Andrea Bocelli Foundation gala at Palazzo Vecchio, not as the concert audience, per the pack notes.

## 4. Revisions of 26 September 2026

- Corporate Hospitality / Sports Travel promo pair removed from `/experiences`.
- Homepage hero overlay lightened (bottom 0.96 → 0.86, mid 0.72 → 0.50, top 0.14 → 0.08) so the slides read through while keeping the dark tint.
- WhatsApp header link on all 109 pages now opens +44 7788 157390 (was the office landline).
- `index.html` was found deleted from the working tree after the "Added Experiences page" commit and was restored from that commit before the edits above.
