# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Jekyll-based personal blog hosted on GitHub Pages. The site uses the `jekyll/minima` remote theme (pinned to a specific commit) with a custom `bttf` skin.

## Commands

```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve

# Build the site
bundle exec jekyll build
```

The built site outputs to `_site/`.

## Architecture

- **Theme**: `jekyll/minima` via `jekyll-remote-theme`, pinned to a specific commit SHA in `_config.yml` — the `master` branch is under active v3 development and can have breaking changes, so the pin must be updated deliberately
- **Skin**: Custom `bttf` skin at `_sass/minima/skins/bttf.scss` (Back to the Future-inspired dark theme). Additional style overrides in `_sass/minima/custom-styles.scss`
- **Social links**: Uses minima v3 format — each entry needs `title`, `icon` (Font Awesome brand ID), and `url`. The old v2 `platform`/`user_url` format no longer works
- **`show_excerpts`**: Top-level key in `_config.yml` (not under `minima:`), because `_layouts/home.html` reads `site.show_excerpts` directly
- **`_layouts/home.html`**: Overrides the minima home layout; renders post excerpts as truncated plain text with a "read more" link
- **`_includes/custom-head.html`**: Conditionally loads Leaflet.js (CSS + JS) when a post sets `mapid` in its front matter; also loads `/css/{{ mapid }}.css` for map-specific styles
- **Posts**: Live in `_posts/` using `YYYY-MM-DD-title.md` (or `.html`) naming; support standard Jekyll front matter
- **Map posts**: Set `mapid: <name>` in front matter to load Leaflet; place corresponding CSS at `/css/<name>.css`
- **Plugins**: `jekyll-sitemap` (auto-generates sitemap) and `jekyll-remote-theme`
- **`atom.xml`**: Manually maintained Atom feed at the repo root

## Deployment

Pushing to the `master` branch triggers GitHub Pages to build and deploy automatically. The custom domain is set via `CNAME`.
