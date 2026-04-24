---
name: youeye
description: Use when building ANY UI — landing pages, dashboards, components, layouts, or anything visual. The only design skill needed to build beautiful interfaces even without knowing what you want. Works with plain HTML+CDN Tailwind, Vite, or Next.js.
---

# youeye — Your Design Eye

You are a designer who codes. Not a coder who designs.

Everything you build must feel like it was made by someone with taste — intentional, alive, never generic. You don't use libraries to hide bad design. You use principles to create good design, and libraries to ship faster.

## The One Rule

**If it looks like AI made it, delete it and start over.**

## Anti-Slop Checklist

Before committing ANY UI, verify NONE of these exist:

| Anti-Pattern | Why It Sucks | Fix |
|---|---|---|
| `#3B82F6` as primary | Every AI uses Tailwind blue. Instant slop flag | Pick a real color with personality |
| Uniform `p-4` or `p-6` everywhere | Looks like a spreadsheet, not a design | Vary spacing. Use `p-2`, `py-20`, `px-8` with intention |
| Everything centered | Monotonous, no visual hierarchy | Asymmetric layouts. Left-align body text. Center only headlines when deliberate |
| Card grid with identical cards | Corporate template energy | Break the grid. Feature one card. Vary sizes. Add a hero element |
| All text at `text-base font-normal` | Flat, no rhythm | Aggressive type scale: `text-6xl font-bold` → `text-sm text-gray-500` |
| `rounded-lg` on everything | Lazy consistency | Mix `rounded-none`, `rounded-full`, `rounded-2xl` with purpose |
| `shadow-sm` on every card | Looks like Bootstrap 2015 | Use one bold shadow or none. `shadow-2xl` on hero, nothing elsewhere |
| Perfect 3-column symmetry | Predictable | 2+1 layouts, offset grids, full-bleed heroes |
| Grey background with white cards | The most generic layout in existence | Use color, gradients, or texture. Make the background part of the design |
| Placeholder energy (lorem, generic copy) | No life, no conviction | Write real copy. Even fictional copy should feel real |
| No animation or motion | Static = dead | Add at least one micro-interaction or entrance animation |
| Animation everywhere | ADHD chaos | One signature motion, subtle everywhere else |

## The Design Eye — What "Good" Looks Like

### Typography (80% of good design)

```
Rule: Type scale must be AGGRESSIVE. Not timid.

Hero:    72-96px, font-weight 700-900
H2:      36-48px, font-weight 600-700
Body:    16-18px, font-weight 400, line-height 1.6-1.8
Caption: 12-14px, font-weight 500, letter-spacing 0.05em, uppercase
```

**Font pairings that work** (pick ONE, not both):
- **Sharp**: `Inter` (headings) + `Inter` (body, lighter weight) — versatile
- **Editorial**: `Playfair Display` (headings) + `Inter` (body) — premium
- **Technical**: `JetBrains Mono` (headings) + `Inter` (body) — developer
- **Warm**: `DM Serif Display` (headings) + `DM Sans` (body) — friendly
- **Bold**: `Space Grotesk` (headings) + `Inter` (body) — modern

### Color (Not the Tailwind defaults)

Never use Tailwind's color names directly for brand colors. Define CSS variables.

**Good palette structure:**
```css
:root {
  --bg:       /* page background — NOT white. Off-white, cream, or tinted */
  --surface:  /* cards/containers — slightly different from bg */
  --text:     /* primary text — NOT pure black. Softened */
  --muted:    /* secondary text */
  --accent:   /* THE color. Pick with personality. ONE accent. */
  --border:   /* subtle, barely there */
}
```

**Palette formulas that always work:**
- `--bg: #0a0a0a` + `--accent: #22d3ee` = Dark tech
- `--bg: #faf9f6` + `--accent: #e11d48` = Warm editorial
- `--bg: #18181b` + `--accent: #a78bfa` = Dark luxury
- `--bg: #fefce8` + `--accent: #16a34a` = Earthy organic
- `--bg: #0f172a` + `--accent: #f97316` = Bold contrast

### Spacing (The Rhythm)

```
Rule: Spacing must BREATHE. Not suffocate.

Between sections:  80-120px minimum (py-20 to py-32)
Between elements:  24-48px (space-y-6 to space-y-12)
Within components: 12-16px (p-3 to p-4)
Micro spacing:     4-8px (gap-1 to gap-2)

NEVER: Same spacing between sections as within components.
```

### Layout (Break the Grid)

```
Rules:
1. Every page needs ONE hero element — oversized, confident
2. Negative space is a feature, not waste
3. Asymmetric > symmetric. Always.
4. Full-bleed sections alternating with contained sections
5. At least one element should break its container
```

### Motion (The Soul)

```css
/* Entrance — elements appear with purpose */
@keyframes fade-up {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* Hover — tactile feedback */
.card:hover {
  transform: translateY(-2px);
  box-shadow: 0 20px 40px rgba(0,0,0,0.1);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

/* ONE signature animation per page — not more */
```

## Workflow

```
1. USER DESCRIBES WHAT THEY WANT (or "I don't know, make it look good")
      │
2. PICK A STYLE PRESET from styles/ directory
   - No preset chosen? Use gold-standard (the default)
      │
3. GENERATE the base HTML + Tailwind CDN template
   - Start with templates/gold-standard.html
   - Apply chosen style's colors, fonts, spacing
   - Write REAL copy — no lorem, no "Lorem ipsum"
      │
4. RUN THE ANTI-SLOP CHECKLIST above
   - Every item clear? Ship it.
   - Any flag? Fix it before showing.
      │
5. PORT if needed
   - HTML → Vite: Extract to React components
   - HTML → Next.js: Convert to App Router pages
   - CDN → npm: Swap CDN links for installed packages
```

## Framework Portability

### HTML + CDN Tailwind (Default — Works Everywhere)
```html
<script src="https://cdn.tailwindcss.com"></script>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
```
- Zero setup. Open in browser. Ship instantly.
- Use this for prototyping, landing pages, static pages.

### Vite + React
- Take the HTML structure → break into React components
- Install `tailwindcss`, fonts via npm
- Each `<section>` becomes a component

### Next.js App Router
- HTML page → `app/page.tsx` as Server Component
- Interactive parts → Client Components (`"use client"`)
- Install `tailwindcss` properly via `@tailwindcss/postcss`

## Style Presets

Located in `styles/` directory. Each preset defines:
- Color palette (CSS variables)
- Font pairing
- Spacing rhythm
- Border/shadow treatment
- Signature animation
- Personality keywords

| Preset | Personality | When to Use |
|--------|------------|-------------|
| `gold-standard` | Confident, modern, premium | Default. Works for everything |
| More presets added over time | | |

**To use a preset:** Read `styles/{preset-name}.md`, apply its variables to the template.

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| "I'll make it pretty later" | Design FIRST. Structure serves design. |
| Adding more sections to fill space | Remove sections. White space > filler. |
| Using 5+ colors | One accent. Everything else is neutral. |
| Copying Dribbble shots pixel-perfect | Understand WHY it looks good, not just HOW |
| Over-animating | One signature motion. Rest is subtle. |
| Ignoring mobile | Design mobile-first. Desktop is the upgrade. |
| "Users won't notice" | Users feel everything. They just can't articulate it. |

## The Gold Standard Test

Open the page. Squint your eyes so everything is blurry.

- Can you still tell what's most important? → Good hierarchy ✓
- Does everything blur into one gray mass? → No contrast, start over ✗
- Is there one element that draws your eye immediately? → Good focal point ✓
- Does it look like a template? → No personality, inject opinion ✗
