# Gold Standard — The Default

The "obviously well-designed" preset. Premium without being pretentious. Modern without being trendy.

## Personality

**Keywords:** Confident. Clean. Intentional. Alive.
**Vibe:** A product page from a company that cares deeply about craft.

## Color Palette

```css
:root {
  --bg:       #faf9f6;   /* Warm off-white — NOT pure white */
  --surface:  #ffffff;   /* Cards on top of bg */
  --text:     #1a1a1a;   /* Near-black — NOT pure black */
  --muted:    #6b7280;   /* Secondary text */
  --accent:   #e11d48;   /* Rose red — bold, not generic */
  --accent-soft: #fff1f2; /* Accent tint for backgrounds */
  --border:   #e5e5e5;   /* Barely visible */
}
```

## Dark Mode Variant

```css
.dark {
  --bg:       #0a0a0a;
  --surface:  #171717;
  --text:     #fafafa;
  --muted:    #a3a3a3;
  --accent:   #fb7185;
  --accent-soft: #1c1917;
  --border:   #262626;
}
```

## Typography

```css
--font-heading: 'Inter', sans-serif;
--font-body:    'Inter', sans-serif;

/* Scale */
--text-hero:    80px;   /* font-weight: 800, letter-spacing: -0.03em, line-height: 1 */
--text-h2:      48px;   /* font-weight: 700, letter-spacing: -0.02em, line-height: 1.1 */
--text-h3:      24px;   /* font-weight: 600, line-height: 1.3 */
--text-body:    17px;   /* font-weight: 400, line-height: 1.7 */
--text-caption: 13px;   /* font-weight: 500, letter-spacing: 0.08em, text-transform: uppercase */
```

## Spacing Rhythm

```
Section padding:    py-24 md:py-32
Container max:      max-w-6xl mx-auto px-6
Between blocks:     space-y-20
Between elements:   space-y-4
Inner padding:      p-6 md:p-8
```

## Border & Shadow Treatment

```css
/* Cards — clean, no heavy shadows */
.card {
  border: 1px solid var(--border);
  border-radius: 16px;
  background: var(--surface);
  /* NO box-shadow by default */
}

/* Hover lift — the ONLY shadow */
.card:hover {
  box-shadow: 0 20px 60px -15px rgba(0, 0, 0, 0.08);
  transform: translateY(-2px);
}

/* Accent border — for featured elements */
.featured {
  border-left: 3px solid var(--accent);
}
```

## Signature Animation

```css
/* Staggered fade-up on page load */
@keyframes fade-up {
  from {
    opacity: 0;
    transform: translateY(24px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-up {
  animation: fade-up 0.8s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  opacity: 0;
}

/* Stagger children */
.stagger > *:nth-child(1) { animation-delay: 0ms; }
.stagger > *:nth-child(2) { animation-delay: 80ms; }
.stagger > *:nth-child(3) { animation-delay: 160ms; }
.stagger > *:nth-child(4) { animation-delay: 240ms; }
.stagger > *:nth-child(5) { animation-delay: 320ms; }
.stagger > *:nth-child(6) { animation-delay: 400ms; }
```

## Layout Rules

1. **Hero:** Full viewport height. Massive headline left-aligned. One accent element right.
2. **Content sections:** Alternate between full-bleed (background color change) and contained.
3. **Grid:** NOT uniform. One large + two small. Or feature + list.
4. **Footer:** Minimal. Logo + 2-3 links. Lots of breathing room.

## Components

### Button
```html
<!-- Primary -->
<a href="#" class="inline-flex items-center gap-2 px-6 py-3 bg-[var(--text)] text-[var(--bg)] rounded-full text-sm font-medium hover:opacity-80 transition-opacity">
  Get Started
  <svg class="w-4 h-4" ...>→</svg>
</a>

<!-- Secondary -->
<a href="#" class="inline-flex items-center gap-2 px-6 py-3 border border-[var(--border)] rounded-full text-sm font-medium hover:bg-[var(--surface)] transition-colors">
  Learn More
</a>
```

### Card
```html
<div class="group p-6 border border-[var(--border)] rounded-2xl hover:shadow-lg transition-all duration-300">
  <div class="w-10 h-10 rounded-xl bg-[var(--accent-soft)] flex items-center justify-center mb-4">
    <svg ...>icon</svg>
  </div>
  <h3 class="text-lg font-semibold mb-2">Feature Title</h3>
  <p class="text-[var(--muted)] text-sm leading-relaxed">Real description about what this does and why it matters.</p>
</div>
```

### Section
```html
<section class="py-24 md:py-32">
  <div class="max-w-6xl mx-auto px-6">
    <!-- Section header — left aligned, never centered unless deliberate -->
    <div class="max-w-2xl mb-16">
      <p class="text-[var(--accent)] text-sm font-medium uppercase tracking-wider mb-3">Section Label</p>
      <h2 class="text-4xl md:text-5xl font-bold tracking-tight leading-[1.1] mb-4">
        A headline that makes<br>a clear promise
      </h2>
      <p class="text-[var(--muted)] text-lg leading-relaxed">
        Supporting context that explains the value. Write like a human talking to a human.
      </p>
    </div>
    <!-- Content -->
  </div>
</section>
```
