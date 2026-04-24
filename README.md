<p align="center">
  <strong>youeye<span style="color:#e11d48">.</span></strong>
</p>

<p align="center">
  The only design skill an AI agent needs to build beautiful interfaces.<br>
  No frameworks. No libraries. Just taste.
</p>

---

## Install

Copy the prompt below and paste it into your AI agent:

```
Clone https://github.com/hangsiahong/youeye and install it as a skill.
Put it in my skills directory (use ~/.agents/skills/youeye or ~/.claude/skills/youeye whichever exists).
Verify the skill is installed by reading the SKILL.md.
```

That's it. Next time you ask the agent to build any UI, youeye activates.

---

## What is this?

AI-generated UI has a smell. Generic blue, uniform padding, centered everything, identical card grids. You know it when you see it.

youeye gives agents a **design eye** — an anti-slop checklist that kills generic patterns, and principles that make interfaces feel alive and intentional.

## What's inside

```
youeye/
├── SKILL.md                  ← The brain: principles, anti-slop checklist, workflow
├── seeds.md                  ← 50 creative prompts for random builds
├── styles/
│   └── gold-standard.md      ← Color palette, typography, spacing, components
├── templates/
│   └── gold-standard.html    ← Full landing page. HTML + CDN Tailwind. Zero deps.
└── README.md
```

## Quick start

Open `templates/gold-standard.html` in a browser. No `npm install`. No build step.

```bash
open templates/gold-standard.html
```

Or tell your agent:

```
Use the youeye skill to build me a landing page for my SaaS product
```

Or just say **"surprise me"** — youeye picks a random creative concept and builds it fresh every time.

## The Anti-Slop Checklist

Before shipping any UI, verify NONE of these exist:

| Anti-Pattern | Why It Sucks |
|---|---|
| `#3B82F6` as primary | Every AI uses Tailwind blue |
| Uniform `p-4` everywhere | Looks like a spreadsheet |
| Everything centered | No visual hierarchy |
| Card grid with identical cards | Corporate template energy |
| All text at `text-base` | Flat, no rhythm |
| `rounded-lg` on everything | Lazy consistency |
| Grey background + white cards | Most generic layout in existence |
| No animation | Static = dead |
| Animation everywhere | ADHD chaos |

## Style Presets

| Preset | Personality | Status |
|--------|------------|--------|
| `gold-standard` | Confident, modern, premium | ✅ Available |
| `dark-luxury` | Rich, immersive, cinematic | Coming soon |
| `warm-minimal` | Soft, approachable, organic | Coming soon |
| `brutalist` | Raw, bold, unapologetic | Coming soon |
| `editorial` | Serif-driven, sophisticated | Coming soon |

## Framework Portability

**HTML + CDN Tailwind** (default) → works everywhere, zero setup

Port to any framework:
- **Vite + React** — extract sections into components, install tailwindcss via npm
- **Next.js** — convert to App Router pages, Server Components by default
- **Astro, Svelte, Vue** — same HTML structure, framework syntax

## The Gold Standard Test

Open the page. Squint your eyes so everything is blurry.

- Can you still tell what's most important? → Good hierarchy ✓
- Does everything blur into one gray mass? → No contrast, start over ✗
- Is there one element that draws your eye immediately? → Good focal point ✓
- Does it look like a template? → No personality, inject opinion ✗

## Philosophy

> If it looks like AI made it, delete it and start over.

- Design FIRST, structure serves design
- One accent color. Everything else is neutral.
- White space is a feature, not waste.
- Asymmetric > symmetric. Always.
- Users feel everything. They just can't articulate it.

## License

MIT
