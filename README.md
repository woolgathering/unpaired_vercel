# Unpaired

Landing page for Unpaired — premium merino/alpaca technical socks for trail, hike, and ski, knit from surplus yarn and sold in sets rather than pairs.

## Structure

```
Unpaired.dc.html                    Live landing page (the deployed root)
_drafts/                            Not deployed — WIP / reference only
  Unpaired - Full Homepage.dc.html  Longer marketing homepage (parked)
assets/
  favicon.svg                       Brand mark
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
2. `vercel.json` rewrites `/` to `/Unpaired.dc.html`, so the landing page loads at the root domain.
3. `.vercelignore` excludes `_drafts/` and `uploads/`, so the parked homepage is not deployed and cannot be reached by URL.

## Email capture

Not wired yet. See `Email Signup Integration Notes.md` — plan is a Google Apps Script web app that appends to a Sheet and sends a welcome email.

## Brand colors

| Use | Hex |
| --- | --- |
| Deep green (primary) | `#1f3d2b` |
| Bone (text on dark) | `#f4f2ee` |
| Signal orange (accent) | `#e8542f` |
