# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A static personal/family website for the Remington family, hosted on GitHub Pages at `www.remingtons.org` (custom domain via `CNAME`). No build step, no package manager, no framework — just HTML, CSS, and JavaScript files served directly.

## Local development

Open any HTML file directly in a browser, or serve locally with:

```bash
python3 -m http.server 8080
```

There are no build, lint, or test commands.

## Deployment

Push to `master` — GitHub Pages serves the site automatically. Changes are live within a minute or two.

## Site structure

**Root `index.html`** — Main family homepage. Uses Bootstrap 3 (vendored in `bootstrap/`), Font Awesome (in `css/` and `fonts/`), jQuery (`js/jquery.js`), and the custom `css/stylish-portfolio.css`. Layout: sidebar nav, full-screen header hero, sections for About, Activities (icon grid), Portfolio (photo grid), footer. All Bootstrap classes and JS-driven sidebar toggle.

**`isaiah/index.html`** — Subpage for Isaiah Remington's handcraft work (stained glass, knifemaking, blacksmithing, swordsmithing). Self-contained: all CSS is inline in `<style>` tags, all JS in `<script>` at the bottom. Custom dark forge aesthetic using CSS variables (`--forge-black`, `--ember`, `--copper`, `--gold`, etc.), Google Fonts (Cinzel + Crimson Pro), Font Awesome icons, and vanilla JS for:
- Auto-advancing carousel with prev/next buttons, dot indicators, keyboard arrows, and touch swipe
- Masonry gallery grid (CSS `column-count`) with hover captions
- Lightbox overlay (click gallery image → full-screen view, Escape or click to close)

## Vendored dependencies

All dependencies are checked in — no CDN for Bootstrap or jQuery:
- `bootstrap/bootstrap.min.css` and `bootstrap.min.js` — Bootstrap 3
- `css/font-awesome.min.css` + `fonts/` — Font Awesome 4
- `js/jquery.js` — jQuery

The Isaiah page also loads Google Fonts and uses Font Awesome from the shared `../css/font-awesome.min.css`.

## Image conventions

Images for the main page go in `images/`. Images for the Isaiah page go in `isaiah/images/`. The Isaiah page references some images by Google Pixel camera filename pattern (`PXL_YYYYMMDD_*.jpg`, `IMG_YYYYMMDD_*.jpg`). When adding new photos, drop the file into the appropriate `images/` directory and reference it with a relative path.
