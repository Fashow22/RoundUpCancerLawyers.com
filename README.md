# Round-Up Website

Targeted website for The Alvarez Law Firm's Roundup cancer litigation practice. Features both Alex Alvarez and Herb Borroto, M.D., J.D. The site's distinguishing angle is **strict product liability** against Monsanto/Bayer — the same defective-product framework the firm has used to recover over $100 million from Big Tobacco — rather than the standard failure-to-warn approach used by most Roundup firms.

## Site Identity

- **Canonical domain:** `https://roundupcancerlawyers.com/` — used in all canonicals, schema `url` properties, sitemap, robots, llms.txt
- **Alias domains (configure as 301 → canonical):**
  - `monsantorounduplawyer.com`
  - `monsantotriallawyer.com`
  - `rounduptriallawyer.com`

  These are redirect-only. Do **not** add to sitemap, llms.txt, schema `sameAs`, or canonicals. In Netlify, set each to redirect (301) to `https://roundupcancerlawyers.com/`. Auto-provision SSL on each so the redirect doesn't trigger a browser warning.
- **Site code (for intake email subject line):** `ROUNDUPLAWYER`
- **Primary defendants:** Monsanto Company; Bayer AG; Bayer CropScience
- **Active product:** Roundup (glyphosate-based herbicide)
- **Geographic scope:** Nationwide (federal Roundup MDL 2741, N.D. Cal., plus state courts)

## Pages Built

| File | Purpose |
|---|---|
| `index.html` | Homepage. Strict liability differentiator, $100M+ tobacco track record, all qualifying cancers, Monsanto/Bayer responsibility, qualification, team bios, process, FAQ, GEO content. |
| `non-hodgkin-lymphoma-lawsuit.html` | Primary practice area — the cancer most strongly tied to Roundup. Covers all NHL subtypes. |
| `b-cell-lymphoma-lawsuit.html` | DLBCL, Follicular, Marginal Zone, Mantle Cell, Burkitt, Lymphoplasmacytic / Waldenström, SLL, Hairy Cell. |
| `leukemia-lawsuit.html` | CLL, SLL, Hairy Cell Leukemia. |
| `multiple-myeloma-lawsuit.html` | Plasma cell cancers — strong link in the agricultural worker literature. |
| `disclaimer.html` | Full legal disclaimer with Roundup-specific language. |
| `privacy-policy.html` | Standard privacy policy, lightly customized for the Roundup practice. |
| `robots.txt` | Standard, points to sitemap. |
| `sitemap.xml` | All seven HTML pages listed. |
| `llms.txt` | LLM-readable site index for AI search citation. |
| `assets/css/styles.css` | Copied from `_TALF-Website-Template`. Shared across all sites. |
| `assets/js/main.js` | Copied from `_TALF-Website-Template`. Shared across all sites. |
| `talf-final-logo-2022-01.png` | TALF logo. |
| `package.json` | npm manifest — Tailwind CLI as devDependency, `build:css` script. |
| `tailwind.config.js` | Tailwind v3 config — custom navy/gold/teal palette + Cormorant/DM Sans/Libre Caslon fonts. |
| `src/input.css` | Tailwind source (base + components + utilities). |
| `netlify.toml` | Netlify build config — runs `npm install && npm run build:css` on every deploy; long-cache headers on `/assets/*`. |

## What Makes This Site Different (And Why)

The Tobacco Website was the natural model — same trial team, same firm, same defective-product story. But the Roundup site has a sharper edge:

1. **Hero leads with strict liability**, not symptoms or sympathy. The headline is *"Monsanto Built A Defective Product. We Know How To Make Them Pay."*
2. **A dedicated "Our Edge" section (`#strict-liability`)** contrasts the standard failure-to-warn approach (most Roundup firms) with strict product liability (TALF). This is the central differentiator and why the firm wins these cases.
3. **The $100M+ tobacco recoveries are positioned as direct proof** that the firm knows how to win on the defective-product framework — not as unrelated trophy stats.
4. **Herb Borroto's medical role is reframed for hematologic cancers** — pathology slides, immunohistochemistry, bone marrow biopsies, M-protein studies — instead of generic medical record review.

## Critical Reminders for Anyone Editing

- **Herb Borroto's title:** Always `Herb Borroto, M.D., J.D.` Never `Dr. Borroto` and never `Physician-Attorney`. Describe him as "holds both a medical degree and a law degree" or "medical-legal expert."
- **Alex Alvarez's title:** Always `Board Certified Civil Trial Lawyer` (NBTA — National Board of Trial Advocacy).
- **The $100M+ figure:** Tied specifically to the firm's tobacco recoveries. It is the credibility anchor for the strict-liability claim — keep it accurate and connected to that context.
- **No specific Roundup verdict claims:** The site references Bayer's $10.9B settlement fund and the MDL, but does not claim specific Roundup verdicts for the firm. Do not add unverified verdict claims.
- **Form embed URL is wired in.** The production Microsoft Forms embed URL is live on all 5 pages. Setup instructions below are kept for reference / future template re-use.

## Intake Form Setup

Follows the standard pattern from `_TALF-Website-Template/README.md`. Summary:

1. Create a Microsoft Form at [forms.office.com](https://forms.office.com) with the standard fields plus a Roundup-specific "Type of Case" dropdown:
   - Non-Hodgkin Lymphoma
   - B-cell Lymphoma (DLBCL, Follicular, Mantle Cell, Marginal Zone, etc.)
   - Chronic Lymphocytic Leukemia (CLL) / SLL
   - Hairy Cell Leukemia
   - Multiple Myeloma
   - Other / Not Sure
2. Title: `Free Roundup Case Review`
3. Description: `Tell us about your Roundup exposure and diagnosis. Your information is confidential. A member of our team will respond within 24 hours. There is no fee unless we win your case.`
4. Theme color: `#0A2540`
5. Get the embed URL and replace `{{MICROSOFT_FORMS_URL}}` everywhere in the site (5 places — one per HTML page that has the form).
6. Set up the Power Automate flow per the template README. Use subject line: `ROUNDUPLAWYER-INTAKE - [Last Name], [First Name]`
7. Send to: `intake@integrityforjustice.com`

## Photos To Add

Drop into the existing folders. Until then, the existing `<img src="...">` references will 404 in the browser:

- `Photos/Team pics/Alex and Herb (cropped).jpg` — hero image (homepage)
- `Photos/Alex Alvarez/Alex5.jpg` — Alex bio (homepage `#your-team`)
- `Photos/Herb Borroto/Herb1.jpg` — Herb bio (homepage `#your-team`)
- `Photos/Herb Borroto/Herb and client.jpg` — contact form background (every page)

The cross-link cards on the homepage use Unsplash CDN URLs as placeholders — fine for launch, replace with locally-hosted Roundup-relevant images when convenient (a farmer with a sprayer, agricultural worker, etc.).

## Deployment Checklist

- [x] Replace all `{{MICROSOFT_FORMS_URL}}` placeholders (5 pages) — done
- [ ] Add team and stock photos to the `Photos/` subfolders
- [x] Domain confirmed and applied — canonical is `https://roundupcancerlawyers.com/`; aliases (monsantorounduplawyer.com, monsantotriallawyer.com, rounduptriallawyer.com) configured as 301 → canonical at the host layer
- [ ] Verify each alias 301s to `https://roundupcancerlawyers.com/` (single-hop, not chained) and serves valid SSL before the redirect
- [ ] **Tailwind compile & swap before first production deploy:**
  1. Local one-time: `npm install --no-audit --no-fund && npm run build:css` — produces `assets/css/tailwind.min.css`.
  2. Find/replace across all 7 HTML files: replace `<script src="https://cdn.tailwindcss.com"></script>` and the inline `<script>tailwind.config = {...}</script>` block with `<link rel="stylesheet" href="/assets/css/tailwind.min.css">`. Custom theme moves into `tailwind.config.js` (already done).
  3. Netlify will then auto-rebuild the CSS on every deploy via `netlify.toml`.
- [ ] Validate one disease page through [Google Rich Results Test](https://search.google.com/test/rich-results) — expect FAQPage + Article/WebPage rich-results eligible, BreadcrumbList rendered, Organization & Person entities resolved.
- [ ] Microsoft Form created, styled `#0A2540`, embedded
- [ ] Power Automate flow set up — uses "Send an email (V2)", NOT V3
- [ ] Test form submission end-to-end (submit → flow → email received at intake@integrityforjustice.com)
- [ ] GitHub repo created, code pushed
- [ ] Netlify connected to repo
- [ ] Domain purchased and nameservers pointed to Netlify
- [ ] SSL provisioned
- [ ] Smoke-test all internal links and the floating phone CTA on mobile
- [ ] Compliance review by Alex / Herb on the strict-liability framing and the $100M+ statement

## Optional Future Additions

- Blog directory at `/blog/` (the homepage already has nav links anticipating it)
- Additional disease pages (e.g., dedicated DLBCL or Follicular Lymphoma standalone pages, dedicated Hairy Cell Leukemia page, dedicated MGUS/Smoldering Myeloma page)
- A standalone "Monsanto Papers" deep-dive page
- A dedicated "MDL 2741 Explained" page
- Spanish-language version (`/es/`) given firm's South Florida base

## Reference Files In Sister Sites

- `_TALF-Website-Template/README.md` — master deployment instructions and Microsoft Forms / Power Automate setup
- `_TALF-Website-Template/Photos/TALF-Style-Guide.md` — brand voice and style guidance
- `Tobacco Website/` — the closest precedent for tone, structure, and technical implementation; reference when extending this site
