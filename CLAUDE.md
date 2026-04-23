# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal portfolio/photography website for Jimmy Tsai, built with **Hugo** (static site generator) and a locally customized **Paige** theme. Deployed to GitHub Pages at `https://jimbo-tsai.github.io/`.

## Build & Development Commands

All Hugo commands must be run from the `site/` directory:

```bash
# Local development server
cd site && hugo server

# Production build (matches CI)
cd site && hugo --gc --minify --baseURL "https://jimbo-tsai.github.io/"

# Install frontend dependencies (Bootstrap, Bootstrap Icons, KaTeX)
cd paige && npm ci
```

Hugo version: **0.126.0** (extended, with Dart Sass). No test or lint commands exist.

## Architecture

### Two-Layer Module Structure

The repo acts as a **local fork of the Paige theme** consumed by the site via Hugo modules:

- **Root (`/`)** — The Paige theme module (`github.com/willfaught/paige`). Contains theme layouts, partials, shortcodes, and NPM dependencies under `paige/node_modules/`.
- **`site/`** — The actual Hugo site (`github.com/jimbo-tsai/jimbot/site`). Its `go.mod` imports the Paige theme with `replace github.com/willfaught/paige => ../`, pointing to the repo root.

This means edits to theme templates in root `layouts/` immediately affect the site without publishing a module.

### Template Override Hierarchy

Hugo resolves templates in this order (highest priority first):

1. **`site/layouts/`** — Site-specific overrides (home page, gallery list, masonry shortcode, custom CSS)
2. **Root `layouts/`** — Local Paige theme templates (base templates, partials, all paige shortcodes)

Key site overrides in `site/layouts/`:
- `index.html` — Custom hero home page
- `galleries/list.html` — Card-based gallery listing
- `shortcodes/modal-gallery-mason.html` — Masonry gallery with optimized thumbnails
- `partials/paige/style-first.css` — CSS to hide/adjust default theme elements

### Custom Shortcodes

The main custom work lives in two gallery shortcodes (root `layouts/shortcodes/`):
- **`modal-gallery.html`** — Flexible image gallery with Bootstrap modal lightbox
- **`modal-gallery-mason.html`** — Masonry layout variant with lazy-loaded, responsive thumbnails (750px, q30)

These are used in content markdown via `{{< modal-gallery >}}` and `{{< modal-gallery-mason >}}`.

### Content Organization

Content lives in `site/content/` organized by section:
- `galleries/` — Photo galleries (each a Hugo page bundle: `index.md` + image files)
- `films/` — Film project pages
- `drawings/`, `paintings/` — Art sections
- `aboutme/` — About page

### NPM Dependencies via Hugo Module Mounts

Root `hugo.toml` maps `paige/node_modules/` packages into Hugo asset paths:
- **Bootstrap 5.3** — CSS framework and JS bundle
- **Bootstrap Icons** — Icon font
- **KaTeX** — Math typesetting (disabled by default via `math = false`)

### Deployment

GitHub Actions (`.github/workflows/hugo.yml`) builds from `site/` on push to `main` and deploys `site/public/` to GitHub Pages.

### i18n

Translation strings in `i18n/` support English, German, and Chinese. The site currently runs in English only (`languagecode = "en-us"`).
