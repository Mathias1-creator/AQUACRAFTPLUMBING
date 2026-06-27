# AQUACRAFT PLUMBING INC. — Website

A clean, premium, fully static marketing site for **AQUACRAFT PLUMBING INC.**
Plain HTML, CSS, and vanilla JavaScript — **no framework, no build step, no npm,
no dependencies.** Open `index.html` in a browser and it just works. Deploy by
dragging the folder onto Netlify.

---

## Quick start

- **Run locally:** double-click `index.html` (or open it in any browser).
- **Deploy to Netlify:** drag this entire folder onto the Netlify "Sites" drop
  zone (app.netlify.com → *Add new site* → *Deploy manually*). No build command,
  no settings to configure — it's a flat static folder.

### Preview on GitHub Pages (one-time setup)

GitHub Pages must be turned on once by the repo owner (the GitHub token can't
enable it automatically). Then it auto-updates on every push:

1. Repo → **Settings** → **Pages**.
2. **Build and deployment → Source:** choose **Deploy from a branch**.
3. **Branch:** pick `claude/aquacraft-plumbing-site-7kb6ma`, folder **/ (root)**,
   then **Save**.
4. Wait ~1 minute. The site goes live at:
   **https://mathias1-creator.github.io/AQUACRAFTPLUMBING/**

(The `.nojekyll` file makes Pages serve the files exactly as-is. All links are
relative, so the site works correctly under the `/AQUACRAFTPLUMBING/` subpath.)

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | Home — hero, services overview, why-choose, service area, reviews, CTA |
| `services.html` | Detailed services + 24/7 emergency callout |
| `about.html` | Company story + credentials |
| `contact.html` | Large Call / Text blocks, hours, service area, social links |
| `styles.css` | All styling (mobile-first, responsive to 375px) |
| `main.js` | Mobile menu toggle + dynamic footer year (the only JS) |
| `AQUA_logo.jpg` | **Your original logo** (retrieved from Google Drive) — kept as the source file |
| `AQUA_logo_horizontal.jpg` | Header lockup (your icon + your wordmark, arranged horizontally) |
| `AQUA_logo_stacked.jpg` | Footer logo (your original, whitespace trimmed for the web) |
| `robots.txt`, `sitemap.xml` | Basic SEO helpers (contain the placeholder domain) |

---

## About the logo

Your real logo came in as `AQUA logo.jpg` from your Google Drive — that exact
file is in this folder as **`AQUA_logo.jpg`** (it's the canonical source and is
also used as the favicon and social-share image).

Two display versions are derived **entirely from your real artwork** so the logo
looks great in every spot:

- **`AQUA_logo_horizontal.jpg`** (header) — your original is a tall, stacked
  lockup. At the height of a top navigation bar a stacked wordmark becomes
  unreadable, so the header uses a horizontal lockup made by placing **your
  exact icon** next to **your exact wordmark**. Nothing was redrawn.
- **`AQUA_logo_stacked.jpg`** (footer) — your original logo with the large
  surrounding whitespace trimmed so it sits tight in the footer.

### Updating the logo later
- To swap in a **new** logo, replace `AQUA_logo_horizontal.jpg` (header) and/or
  `AQUA_logo_stacked.jpg` (footer) with files of the same names — no code change
  needed.
- **One recommended upgrade:** the logo is a JPG on a solid **white** background,
  so the header and footer are intentionally kept white/light (a JPG on a dark
  background would show an ugly white box). If you ever get a **transparent-PNG**
  version of the logo, that's the single upgrade that would let the logo sit on
  dark/navy sections too. Save it as `AQUA_logo_horizontal.png` /
  `AQUA_logo_stacked.png` and update the `<img src>` references.

---

## Swapping in your real domain (1 place to change)

Everything uses the placeholder **`EXAMPLE-DOMAIN.com`**. Once you have your real
domain, find-and-replace `EXAMPLE-DOMAIN.com` with it across these files:

- `index.html`, `services.html`, `about.html`, `contact.html`
  — `<link rel="canonical">`, the `og:` meta tags, and the `url` / `image`
  fields inside the **JSON-LD** `<script type="application/ld+json">` block.
- `robots.txt` — the `Sitemap:` line.
- `sitemap.xml` — every `<loc>`.

On macOS/Linux you can do it in one command from inside the folder:

```bash
grep -rl 'EXAMPLE-DOMAIN.com' . | xargs sed -i '' 's/EXAMPLE-DOMAIN\.com/yourdomain.com/g'   # macOS
# Linux: drop the '' after -i
```

(Each spot is also marked with an HTML comment so it's easy to find by hand.)

---

## Contact mechanics

- Every **Call** link is `tel:7077573838`; every **Text** link is `sms:7077573838`
  (digits only, which is what phones expect). Displayed everywhere as
  **707-757-3838**.
- A **sticky Call / Text bar** is fixed to the bottom on phones (≤768px) and
  hidden on desktop.
- **No contact form and no email address** appear anywhere on the site, by design.

---

## Assumptions & design decisions

- **Header vs. footer logo** — explained above (horizontal lockup in the header,
  trimmed stacked logo in the footer), both built from your real artwork for
  legibility.
- **Hero is light, not dark.** A soft white→off-white gradient keeps the look
  clean/premium and lets the primary buttons stay **navy with a red hover**
  exactly as specified. The dark navy contrast accent appears in the CTA bands
  and the emergency callout instead.
- **Buttons** follow the brand rule: primary = **navy**, hover/active = **red**.
  On the dark navy bands the primary button inverts to white (→ red on hover) for
  contrast. The mobile sticky bar's "Text Us" button uses the brand **blue** to
  distinguish it from the navy "Call Now" button (both go red on press).
- **Star glyphs** in the rating/reviews are shown in a conventional review
  **gold** (`#F4B400`). This is the only off-palette color and is used only for
  star icons, since gold stars are the universally understood rating convention.
- **Google reviews link** points to a Google search for the business
  (`google.com/search?q=Aquacraft+Plumbing+Inc+reviews`) because no direct Google
  Business profile URL was provided. Swap it for the direct profile/reviews URL
  when you have it (it's marked with a comment in `index.html` and `contact.html`).
- **First names only** are shown on testimonials (e.g. "Sonya — Google review"),
  using the four real reviews verbatim. No reviews were invented.
- **No photos/gallery.** All imagery is the logo plus CSS gradients and inline
  SVG icons, so there are no external image dependencies and nothing can appear
  broken on launch.
- Company facts (3rd-generation, 15 years combined experience, locally born and
  raised, established January 2026, licensed & bonded, backflow certified in
  CA & NV, 5.0★ on Google with 7 reviews, Sonoma/Napa/Marin service area) are
  used exactly as provided — nothing was added or embellished.

---

## Acceptance checklist

- [x] All `tel:` links = `tel:7077573838`, all `sms:` links = `sms:7077573838`
- [x] No email address anywhere on the site
- [x] No contact form anywhere
- [x] Sticky Call/Text bar shows on mobile, hidden on desktop
- [x] No lorem ipsum / placeholder copy / visible TODOs
- [x] No fake reviews, no fake portfolio/gallery, no invented business facts
- [x] Logo only ever sits on white/light backgrounds
- [x] Renders cleanly at 375px wide and scales up to desktop
- [x] Runs by opening `index.html` — no build step, no dependencies
- [x] Deploys as a flat folder (all files + the logo images) for a Netlify drop
- [x] `LocalBusiness` (Plumber) JSON-LD with name, phone, area served, 24/7 hours
