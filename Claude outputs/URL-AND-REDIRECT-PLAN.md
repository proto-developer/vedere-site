# Vedere — URLs, routing and 301 redirects

**Date:** 19 September 2026. Written in response to the pre-launch SEO review.

> **STATUS: IMPLEMENTED.** Both decisions were approved and applied on 19 September 2026:
> evergreen URLs for annual events, and the routing config activated as `vercel.json` in the repo
> root. What changed:
> - **33 event URLs lost their year** (24 F1 races, the four tennis slams, the Masters, The Open,
>   Phoenix Open). Five stay dated on purpose: Euro 2028, Rugby World Cup 2027, Ryder Cup 2027,
>   The Ashes 2027, England's tour of South Africa 2026/27.
> - **Years remain in the H1, titles, descriptions, copy and structured data** — only the URL is
>   evergreen, so each page is re-used and updated season to season.
> - **22,021 internal links** repointed to canonical paths; zero `.html` links remain anywhere.
> - **Pages now live in the folder their URL names** (`formula-one/monaco-grand-prix/index.html`),
>   and every asset reference is root-relative (`/assets/…`). The site therefore works on any static
>   server, including local preview, with no rewrites. *(An earlier version relied on Vercel rewrites
>   to flat files; that broke local preview and would have broken every image on nested URLs,
>   because relative `assets/…` paths resolved under the page's folder. Fixed the same day.)*
> - **`vercel.json`**: **241 permanent 301s** — every old `.html` form, bare slug and dated URL
>   folds into the evergreen canonical. No rewrites are needed.
> - **Sitemap and the site search index** regenerated against the new URLs.
> - Verified: 107/107 canonicals correct, no links to unknown paths, no redirect/rewrite conflicts,
>   no rewrite pointing at a missing file.

---

## 1. The launch blocker nobody has hit yet

The pages declare canonical URLs that **do not currently exist as routes**.

| What | Value |
|---|---|
| File in the repo | `/monaco-grand-prix-2027.html` |
| Canonical tag on that page | `https://vederetravel.com/formula-one/monaco-grand-prix-2027` |
| Sitemap entry | `https://vederetravel.com/formula-one/monaco-grand-prix-2027` |
| Internal links | `href="monaco-grand-prix-2027.html"` |

**99 of 107 pages** are in this state. There is no `vercel.json`, `.htaccess`, `_redirects` or other
routing configuration anywhere in the repo, so on a plain static deploy the canonical URLs and every
sitemap entry would 404 while the real pages sit at `/monaco-grand-prix-2027.html`.

This must be fixed at launch regardless of any other decision below.

## 2. Fix: routing config (ready to apply)

`vercel.json.proposed` (in this folder) is generated from the pages' own canonical tags:

- `cleanUrls: true`, `trailingSlash: false`
- **100 rewrites** — canonical path → the actual file, e.g.
  `/formula-one/monaco-grand-prix-2027` → `/monaco-grand-prix-2027.html`.
  Rewrites serve the file at the canonical URL without a redirect hop.
- **206 permanent (301) redirects** — every legacy form folds into the canonical URL:
  `/monaco-grand-prix-2027.html` → `/formula-one/monaco-grand-prix-2027`
  `/monaco-grand-prix-2027` → `/formula-one/monaco-grand-prix-2027`

It is **not** activated: to use it, move it to the repo root as `vercel.json`. I have left it staged
because it changes production routing and should be reviewed first. If the site ends up on a host
other than Vercel, the same map converts directly to Apache/Nginx/Cloudflare rules — the source data
is the canonical tag on each page.

**Also needed once routing is live:** internal links should point at the canonical URLs rather than
`.html`, so crawlers don't take a redirect hop on every link (roughly 100 links per page). That is a
scripted change I can run as soon as the routing approach is agreed.

## 3. The reviewer's point: dated URLs vs evergreen

They are right, and it matters more than it looks.

**Current:** `/formula-one/monaco-grand-prix-2027` — the year is in the URL, the `<title>` and the
meta description. When the 2028 race is announced, either the page is rewritten (and every backlink
points at a URL describing the wrong year) or a new page is created (and authority is split).

**Recommended:** `/formula-one/monaco-grand-prix` — evergreen URL, with the year carried in the H1,
the copy, the dates panel, the structured data and the metadata, all updated each season. Backlinks,
rankings and internal links then accumulate on one URL, year after year.

Applies to 24 F1 race pages and the dated event pages (`wimbledon-2027`, `us-masters-2027`,
`the-ashes-2027`, `euro-2028`, `rugby-world-cup-2027`, `ryder-cup-2027`, and so on).

**Two sensible exceptions:**
- **Genuinely one-off events** — a World Cup or a Euros belongs to its year and can keep it
  (`/football/euro-2028`), because it isn't an annual fixture.
- **Completed 2026 races** kept as archive (Dutch, Italian, Spanish) — leave them on their dated URLs
  and 301 them to the evergreen page once one exists, so the history folds into the live page.

**If adopted**, the work is: rename the canonical on each page → regenerate the sitemap → update
internal links → add 301s from every dated URL to its evergreen equivalent → update the search index.
About an hour's work, all scripted, and best done **before** launch so no external links are ever
built to the dated URLs.

## 4. Redirect inventory to confirm before go-live

I can only see this repo, so two things need answers from whoever owns the current live site:

1. **Is there an existing live site at vederetravel.com with URLs that will change?** If so I need its
   URL list (a crawl export or the current sitemap) to build old → new 301s. The map above only
   covers this repo's own internal forms, not any legacy live URLs.
2. **Is `vedere-site.vercel.app` going to remain reachable?** If so it should be `noindex` or
   301'd wholesale to the production domain, or it will compete with it.

## 5. The rest of the review — status

| Point | Status |
|---|---|
| Homepage title/description too broad | **Done** — now "Luxury Sports Travel \| F1, Tennis, Golf & Football \| Vedere", description sports-first |
| Clickable images on category cards | **Done** — 57 event/region/promo card images now link to the card's destination; plus featured hotel cards now link through to the hotel |
| Competing homepage CTAs | **Done** — "Plan Your Trip" is now the solid primary, "Explore Sports Journeys" the secondary |
| One colour reserved for CTAs | **Not done — needs a design decision.** Gold is currently used for CTAs *and* eyebrows, rules, prices and accents. Reserving it for CTAs alone is a brand-level change across 107 pages |
| More internal linking | **Partly done** (card images, featured hotels, hotel search deep links). More contextual in-copy links are worth a dedicated pass |
| FAQs — keep and expand | Kept throughout; expansion needs keyword research and client answers |
| Blog | **There is no blog.** No editorial or guide templates exist in the repo |
