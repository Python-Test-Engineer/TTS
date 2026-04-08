# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

Static single-page website for Craig West, a sole-trader plumber in Brighton specialising in Saniflo macerator repairs, toilet repairs and tap repairs.

No build system, no package manager, no dependencies. Everything is plain HTML, CSS and vanilla JS.

## Files

- `index.html` — the entire site; one long page with anchor-linked sections
- `styles.css` — all styles; mobile-first with a single breakpoint at 800px
- `craig-west.jpg` — headshot used in the bio section
- `llms.txt` — AI-agent-friendly plain-text summary of the business (llmstxt.org format)
- `sitemap.xml` — single-URL sitemap
- `robots.txt` — open to all crawlers

## Architecture

Single-page layout. Navigation links (`#home`, `#hours`, `#about`, `#services`, `#saniflo-guide`, `#contact`) scroll to named sections within `index.html`. The sticky header offset is controlled by `--header-offset: 88px` in CSS and matched by `scroll-padding-top` on `<html>` and `scroll-margin-top` on each section.

The only JavaScript is an inline hamburger-menu toggle at the bottom of `<body>` — no frameworks, no modules.

Structured data is embedded as a `<script type="application/ld+json">` block in `<head>` containing a `Plumber` and `FAQPage` schema graph.

## Design tokens (CSS custom properties)

```
--brand: #6495ed      (cornflower blue — primary colour)
--accent: #ffa500     (orange — hover/focus state)
--ink: #1d2935        (body text)
--muted: #64748b
--surface: #ffffff
--bg: #f3f5f6
--line: #dbe2ea
```

## Content and business facts

When editing content, keep these facts consistent across `index.html`, the JSON-LD block, and `llms.txt`:

- Phone: 07415 619 793 / +44 7415 619793
- Email: iwswordpress@gmail.com
- Address: 37C New England Road, Brighton, BN1 4GG
- Hours: Mon–Fri 08:00–17:00
- Pricing: £75 + parts (small jobs), £135 + parts (Saniflo)
- Status: sole trader, NOT VAT registered

## Previewing

Open `index.html` directly in a browser. There is no local server required.
