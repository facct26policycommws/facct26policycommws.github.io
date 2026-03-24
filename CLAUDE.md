# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Static Jekyll site for a FAccT 2026 conference workshop website.

## Commands

```bash
# Install dependencies
bundle install

# Serve locally with live reload
bundle exec jekyll serve --livereload

# Build for production
bundle exec jekyll build

# Build and serve (no live reload)
bundle exec jekyll serve
```

Output is generated into `_site/` (gitignored).

## Architecture

Standard Jekyll structure:

- `_config.yml` — site-wide configuration (title, baseurl, plugins, collections)
- `_layouts/` — base HTML templates (e.g. `default.html`, `page.html`)
- `_includes/` — reusable partials (nav, footer, head)
- `_data/` — YAML/JSON data files (speakers, schedule, organizers)
- `_posts/` — dated content (if used for news/updates)
- `assets/` — CSS, JS, images
- Top-level `.md` / `.html` files — individual pages (index, schedule, speakers, cfp, etc.)

Pages use front matter to specify layout and metadata:
```yaml
---
layout: page
title: Call for Papers
---
```

Data-driven sections (e.g. speaker bios, schedule) should live in `_data/` and be rendered via Liquid templates rather than hardcoded in pages.
