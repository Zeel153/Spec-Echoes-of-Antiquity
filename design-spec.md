# Design Spec — Echoes of Antiquity

## Status: Active | Version: 1.0

---

## Purpose

This document is the single source of truth for all visual decisions in the
Echoes of Antiquity museum website. Every CSS value, font choice, spacing unit,
and color token derives from this document.

If a visual decision is not recorded here, it is not yet decided.
No sprint may introduce a new visual element without first recording it here.

---

## Design Philosophy

The visual system uses **Bauhaus** as its governing tradition.

Bauhaus was founded in 1919 on the principle that form follows function — that
beauty emerges from discipline, not decoration. For a digital museum, this
creates a productive tension: the restraint of the design *frames* the richness
of the content. The artifacts speak. The design listens.

Key Bauhaus principles applied here:

- **Grid over decoration** — layout is structural, not aesthetic
- **Type as architecture** — typography carries hierarchy, not ornament
- **Restricted palette** — fewer colors, used with more intention
- **Whitespace as content** — generous margins signal importance and respect for the visitor

---

## Color Tokens

These are the only colors used on the site. All CSS must reference these
custom properties, never raw hex values.

```css
:root {
  --color-background:  #F5F0E8;   /* Warm parchment — the site's ground */
  --color-surface:     #FFFFFF;   /* Card and panel backgrounds */
  --color-primary:     #1A1A1A;   /* Primary text — near black */
  --color-secondary:   #5C4B32;   /* Secondary text, captions — warm brown */
  --color-accent:      #8B1A1A;   /* Accent — deep museum red, used sparingly */
  --color-rule:        #C9B99A;   /* Horizontal rules, borders — sand */
  --color-muted:       #6B6B6B;   /* Meta text, provenance labels */
}
```

### Color Usage Rules

| Token | Permitted Uses | Forbidden Uses |
|-------|---------------|----------------|
| `--color-background` | Page background only | Text, borders |
| `--color-surface` | Cards, panels, nav | Background |
| `--color-primary` | Headings, body text | Decorative elements |
| `--color-secondary` | Captions, subheadings, Wing intro | Headings |
| `--color-accent` | One highlight per page max, CTAs, hover states | Body text, backgrounds |
| `--color-rule` | `<hr>`, card borders, dividers | Text |
| `--color-muted` | Provenance data, dates, labels | Headings |

---

## Typography

### Typeface Selections

Two typefaces are used. No others are permitted.

```css
/* Load via Google Fonts in <head> */
/* @import or <link> for: Oswald (headings) + Lora (body) */
```

| Role | Typeface | Weight | Notes |
|------|----------|--------|-------|
| Display / Hero headings | `Oswald` | 700 | All-caps, letter-spacing: 0.05em |
| Section headings (h2) | `Oswald` | 600 | Normal case |
| Subheadings (h3) | `Oswald` | 400 | Normal case |
| Body copy | `Lora` | 400 | Serif, high legibility |
| Body bold | `Lora` | 700 | For emphasis within copy |
| Labels / meta | `Oswald` | 300 | Small, muted color, all-caps |

### Type Scale

```css
:root {
  --text-xs:   0.75rem;   /* 12px — meta labels */
  --text-sm:   0.875rem;  /* 14px — captions */
  --text-base: 1rem;      /* 16px — body */
  --text-lg:   1.25rem;   /* 20px — large body / intro */
  --text-xl:   1.5rem;    /* 24px — h3 */
  --text-2xl:  2rem;      /* 32px — h2 */
  --text-3xl:  3rem;      /* 48px — h1 */
  --text-hero: 5rem;      /* 80px — hero display */
}
```

### Line Height

```css
:root {
  --leading-tight:  1.1;   /* Hero headlines */
  --leading-snug:   1.3;   /* Section headings */
  --leading-normal: 1.6;   /* Body copy */
  --leading-loose:  1.8;   /* Long-form text */
}
```

---

## Spacing System

All spacing derives from a base unit of `8px`. Only multiples of this unit
are permitted.

```css
:root {
  --space-1:   0.5rem;    /* 8px */
  --space-2:   1rem;      /* 16px */
  --space-3:   1.5rem;    /* 24px */
  --space-4:   2rem;      /* 32px */
  --space-6:   3rem;      /* 48px */
  --space-8:   4rem;      /* 64px */
  --space-12:  6rem;      /* 96px */
  --space-16:  8rem;      /* 128px */
}
```

**Rule:** No padding, margin, or gap value may appear as a raw pixel value
in CSS. All spacing must use a `--space-*` token.

---

## Grid System

The layout uses a 12-column CSS Grid at the page level.

```css
.container {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  column-gap: var(--space-3);
  max-width: 1200px;
  margin-inline: auto;
  padding-inline: var(--space-4);
}
```

### Column Assignments by Component

| Component | Columns (desktop) | Columns (mobile) |
|-----------|-------------------|------------------|
| Hero text block | 1–8 | 1–12 |
| Wing nav cards | each spans 4 | each spans 12 |
| Artifact cards | each spans 4 | each spans 12 |
| Body copy block | 2–9 (centered) | 1–12 |
| Provenance block | 1–5 | 1–12 |
| Artifact description | 6–12 | 1–12 |

---

## Component Specs

### Hero Section

```
Background: --color-background
Padding top: --space-16
Padding bottom: --space-12
Border bottom: 2px solid --color-accent

Headline: Oswald 700, --text-hero, --leading-tight, --color-primary
Subhead: Lora 400 italic, --text-lg, --color-secondary
```

### Navigation Bar

```
Background: --color-primary
Height: 64px
Padding: 0 --space-4
Link color: --color-background
Link font: Oswald 400, --text-sm, letter-spacing: 0.1em, all-caps
Active link: --color-accent underline
```

### Artifact Card

```
Background: --color-surface
Border: 1px solid --color-rule
Padding: --space-4
No border-radius (Bauhaus — geometric, not soft)

Image area: 100% width, aspect-ratio 4/3, background: --color-rule
Artifact name: Oswald 600, --text-xl, --color-primary
Period label: Oswald 300, --text-xs, --color-muted, all-caps
Material + Origin: Lora 400, --text-sm, --color-secondary
Description: Lora 400, --text-base, --color-primary, --leading-normal
Institution: Oswald 300, --text-xs, --color-muted — prefixed "Collection:"
```

### Wing Hero Banner

```
Background: --color-primary
Padding: --space-12 --space-4
Civilization name: Oswald 700, --text-3xl, --color-background, all-caps
Date range: Oswald 300, --text-sm, --color-rule, letter-spacing: 0.2em
Thesis line: Lora 400 italic, --text-lg, --color-rule
Left border accent: 4px solid --color-accent
```

### Section Heading

```
Font: Oswald 600, --text-2xl, --color-primary
Margin bottom: --space-2
Border bottom: 2px solid --color-rule
Padding bottom: --space-1
```

### Horizontal Rule

```css
hr {
  border: none;
  border-top: 1px solid var(--color-rule);
  margin-block: var(--space-6);
}
```

### Curator's Note / Pull Quote

```
Border left: 4px solid --color-accent
Padding left: --space-4
Font: Lora 400 italic, --text-lg, --color-secondary
Attribution: Oswald 300, --text-sm, --color-muted, all-caps
```

---

## Responsive Breakpoints

```css
/* Mobile first */

/* Tablet */
@media (min-width: 640px) { ... }

/* Desktop */
@media (min-width: 1024px) { ... }

/* Wide */
@media (min-width: 1280px) { ... }
```

At mobile breakpoints:
- All multi-column grids collapse to single column
- `--text-hero` reduces to `--text-3xl`
- Navigation collapses to stacked links or hamburger pattern

---

## Invariants

These rules must not be violated in any sprint:

- No raw hex color values in any CSS file
- No typeface other than Oswald and Lora
- No `border-radius` greater than `2px` on structural elements
- No gradients
- No box shadows on cards (use border instead)
- No decorative icons or emoji in body copy
- Spacing values must use `--space-*` tokens only

---

## QA Checklist for Design Sprint

- [ ] All CSS custom properties defined in `:root`
- [ ] No raw hex values anywhere in CSS
- [ ] Oswald and Lora loaded correctly via Google Fonts
- [ ] 12-column grid applied to `.container`
- [ ] Artifact cards contain all required fields with correct typography
- [ ] Color accent used no more than once per page
- [ ] Mobile layout collapses correctly at 640px
- [ ] Hero section padding and type scale render correctly
- [ ] No border-radius violations
- [ ] All spacing uses `--space-*` tokens

---

## Related Artifacts

- `spec.md` — the governing site spec this design system serves
- `index.html` and wing pages — where these tokens are applied
- `css/styles.css` — the single CSS file consuming all tokens defined here
