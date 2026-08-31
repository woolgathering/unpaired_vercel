# Unpaired

Landing page for Unpaired — premium merino/alpaca technical socks for trail, hike, and ski, knit from surplus yarn and sold in sets rather than pairs.

## Structure

```
index.html                          Deployed page (copy of Unpaired.dc.html)
Unpaired.dc.html                    Editable source of the landing page
_drafts/                            Not deployed — WIP / reference only
  Unpaired - Full Homepage.dc.html  Longer marketing homepage (parked)
assets/
  favicon.svg                       Brand mark
  favicon-180.png                   180×180 raster icon (apple-touch-icon)
  fonts/                            Self-hosted webfonts
Email Signup Integration Notes.md   Plan for the email capture backend
```

## Hero background

Solid brand green with a mismatched color strip along the bottom edge — no photography required. The strip's end segments are near-black so the footer text stays readable.

## Fonts

Self-hosted in `assets/fonts/` so they reproduce on any host:

- **Oldburg Display Semibold** — the UNPAIRED wordmark
- **Syne Mono Regular** — all other text (OFL license included)

## Deploying on Vercel

The repo is static — no build step.

1. Import the repo in Vercel. Framework preset: **Other**. Leave build command empty, output directory = repo root.
2. `index.html` is served at the root domain automatically — no rewrite needed. `cleanUrls` is on, so any future pages resolve without the `.html` extension (`about.html` → `/about`).
3. `.vercelignore` excludes `_drafts/` and `uploads/`, so the parked homepage is not deployed and cannot be reached by URL.

**After editing `Unpaired.dc.html`, copy it over `index.html` before deploying** — `index.html` is the file Vercel serves.

## Email capture

Not wired yet. See `Email Signup Integration Notes.md` — plan is a Google Apps Script web app that appends to a Sheet and sends a welcome email.

## Brand colors

| Use | Hex |
| --- | --- |
| Deep green (primary) | `#1f3d2b` |
| Bone (text on dark) | `#f4f2ee` |
| Signal orange (accent) | `#e8542f` |
