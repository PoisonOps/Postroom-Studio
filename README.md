# Postroom Studio

> Full brand identity and marketing site for a video-editing studio — designed, written, and shipped solo. Twice.

**Live → [postroom-studio.vercel.app](https://postroom-studio.vercel.app)**

---

## What It Is

Postroom Studio is a video-editing studio's complete online presence: brand identity system, marketing site, and portfolio showcase. Every pixel designed and every line written by one person, deployed as a zero-dependency vanilla HTML/CSS/JS site.

The project was designed and shipped twice — two complete iterations from scratch — each time improving the visual system and motion design.

---

## What Was Built

- **Brand identity** — color system, typography, logo mark, design tokens
- **Marketing site** — hero, services, work showcase, contact
- **Custom cursor** — smooth `requestAnimationFrame` lerp cursor with hover states
- **Motion system** — `IntersectionObserver`-driven scroll reveals throughout
- **Performance** — single HTML file, no dependencies, sub-second load

---

## Technical Highlights

| Feature | Implementation |
|---|---|
| Custom cursor | `requestAnimationFrame` lerp loop — dot + ring, 0.12 easing |
| Scroll reveals | `IntersectionObserver` — stagger on entry, `once: true` |
| Design tokens | CSS custom properties — one source of truth for all color/spacing |
| Fonts | Google Fonts via preconnect — DM Serif Display + Inter |
| Zero JS overhead | No framework, no bundler, no npm — open in browser directly |

---

## Running Locally

```bash
# No install needed — just open the file
open index.html

# Or serve it
npx serve .
```

---

## Design System

Built entirely with CSS custom properties:

```css
:root {
  --bg:      #0A080C;
  --surface: #110F14;
  --text:    #E8DCC0;
  --accent:  #E8820C;
}
```

Typography: **DM Serif Display** for headlines · **Inter** for body · **JetBrains Mono** for labels

---

Built by [Sahil Solankey](https://sahilsolankey.vercel.app)
