# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

`postroom-website.html` is the complete Postroom Studio marketing website — a single self-contained HTML file with no build step, no dependencies, and no server. Open it directly in a browser to preview.

## Architecture

Everything lives in one file in this order:
1. **CSS** (`<style>` block) — CSS custom properties at `:root`, then sections: reset, cursor, nav, hero, marquee, reel grid, services, process, niches, pricing, CTA, footer, animations
2. **HTML** — static markup; scroll-target anchors are `#work`, `#services`, `#pricing`, `#contact`
3. **JavaScript** (`<script>` block at end of body) — three behaviours: custom cursor (dot + lagging ring via `requestAnimationFrame`), nav scroll state, and IntersectionObserver scroll-reveal (`.reveal` → `.reveal.visible`)

## Design tokens

All colours and brand values are CSS custom properties on `:root`:

| Token | Value | Role |
|---|---|---|
| `--black` | `#090909` | page background |
| `--white` | `#f5f0e8` | primary text |
| `--cream` | `#e8e0cc` | secondary text |
| `--gold` | `#c9a84c` | accent / brand colour |
| `--gold-dim` | `#8a6c28` | muted gold (tool tags) |
| `--grey` | `#2a2a2a` | reel placeholder bg |
| `--film` | `#1a1510` | dark warm bg (hero, featured card) |

Fonts loaded from Google Fonts: `Playfair Display` (headings/numbers, serif), `DM Mono` (labels/tags/buttons, monospace), `DM Sans` (body copy, sans-serif).

## Key patterns

- **Scroll reveal**: Add class `reveal` to any element; it becomes visible when it enters the viewport. Use `style="transition-delay: Xs"` for staggered siblings.
- **Section label**: `<div class="section-label">Text</div>` renders a gold monospace label with a leading rule line.
- **Custom cursor**: The cursor is hidden (`cursor: none` on `body`); hover states on `<a>` and `<button>` scale both cursor elements. Any new interactive elements need the same `mouseenter`/`mouseleave` listeners or a delegated approach.
- **Pricing & contact CTAs**: Buttons use inline `onclick` to scroll to `#contact`. Keep CTA wiring consistent with this pattern.

## Business context

- **Contact**: Instagram `@postroom.studio`, email `postroom.studio@gmail.com`
- **Pricing**: Starter ₹8,000/mo (4 videos), Growth ₹15,000/mo (8 videos, featured)
- **Reel placeholders**: The three video slots (Showreel, Finance Sample, Coach Reels Sample) are intentionally empty placeholders awaiting real embed URLs.
