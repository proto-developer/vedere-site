# Vedere Travel — WordPress build · install guide

**What this is:** a custom WordPress theme, `vedere`, that serves the approved 94-page site through WordPress with pixel-identical markup, imagery, SEO meta, structured data and URLs. Nothing is re-templated, so the site cannot drift from the approved build.

## What's in the package
- `vedere-wp-theme-part1of9.zip … part9of9.zip` — together they contain one folder: `vedere/`
  - `style.css`, `functions.php`, `index.php`, `router.php`, `manifest.json` — the theme itself
  - `pages/` — all 94 pages (asset paths pre-rewritten to the theme directory)
  - `assets/` — the full image library (~150MB)
  - `sitemap.xml`, `robots.txt`

## Install (10 minutes)
1. **Get the `vedere` folder onto the server.** The theme is ~160MB (imagery), which is beyond most WP admin upload limits, so use FTP/SFTP or your host's file manager: extract **all nine zips into `wp-content/themes/`** — they merge into a single `wp-content/themes/vedere/` folder. (Extract locally first and upload the merged folder if that's easier.)
2. **Activate:** WP Admin → Appearance → Themes → *Vedere Travel* → Activate.
3. **Permalinks:** Settings → Permalinks → choose **Post name** → Save. (This enables the clean URLs; the theme's router does the rest.)
4. Done. Visit `/`, `/greece`, `/formula-one/monaco-grand-prix-2027`, `/sitemap.xml` to confirm.

## How it works
- The theme intercepts every request before WordPress builds a query and serves the matching pre-built page from `pages/` (see `router.php`). URLs match the canonical structure exactly — `/greece`, `/luxury-travel/europe/italy`, `/formula-one/…` — and legacy `.html` URLs are also accepted.
- `/sitemap.xml` and `/robots.txt` are served from the theme; WordPress's own sitemap is disabled so there is exactly one.
- Legacy `/assets/…` URLs (e.g. old og:image shares) are transparently served from the theme's asset folder with long-cache headers.
- Any URL the site doesn't own (including the intentionally-unbuilt `/atol`, `/booking-conditions`, `/contact`, `/vedere-circle`) falls through to a branded 404.
- Posts, plugins and the WP admin all keep working — the theme only claims the site's own URLs.

## Things to know
1. **Enquiry forms are front-end only** (as in the static build): they fire the `enquiry_submit` dataLayer event and confirm to the user, but nothing is emailed or stored yet. When you're ready, wire the form to a handler (WPForms/Gravity/`admin-post.php`) — happy to build that next.
2. **Editing content:** pages live as HTML files in `wp-content/themes/vedere/pages/` — edit there (or send changes to me/your developer). They are deliberately not WP posts, so the approved build can't be accidentally reformatted in the block editor.
3. **Caching/CDN:** the pages are static files read from disk — they're extremely fast as-is, and safe behind any full-page cache or CDN.
4. **HTTPS + domain:** all canonicals and schema point at `https://vederetravel.com` — install on that domain (or ask me to re-point the canonicals if staging under another URL first).
