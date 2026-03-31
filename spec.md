# Site Spec — Echoes of Antiquity

## Status: Active | Version: 1.0

---

## Why This Document Exists

This spec is the governing contract for the Echoes of Antiquity museum website.
It defines the problem, the design goals, the page architecture, the content
model, and the acceptance criteria.

No sprint work begins without this document. No implementation is accepted
unless it satisfies the criteria recorded here.

---

## Problem Statement

The deliverable is a digital museum website covering three ancient civilizations:
Egypt, Greece, and Rome. The site must function not merely as a collection of
pages, but as a curated exhibition — one with narrative flow, a consistent
visual identity, and an intentional visitor experience.

The site must demonstrate three overlapping design frameworks:

1. **Bauhaus design style** — the visual and layout system
2. **The Sage brand archetype** — the psychological identity and voice
3. **Cialdini's Authority principle** — the persuasion mechanism driving engagement

These are not decorative choices. Each must be traceable in the final HTML and
CSS and defensible in a 5-minute in-class presentation.

---

## Design Framework

### 1. Bauhaus Style

Bauhaus grounds the visual system. Its rules for this project:

- Grid-first layout: all page structures derive from a consistent column grid
- Primary typeface: bold, geometric sans-serif for headings (e.g. `Oswald`, `Bebas Neue`, or similar)
- Secondary typeface: humanist serif for body copy (e.g. `Lora`, `Playfair Display`)
- Color palette: restricted to 4–5 tokens (see `design-spec.md`)
- Whitespace is a design element, not empty space — generous margins are required
- Decorative elements are geometric only: horizontal rules, rectangles, grids
- No ornamental fonts, gradients, or shadows except where structurally justified

### 2. The Sage Archetype

The Sage drives the site's voice and tone. Its rules for this project:

- Copy speaks with authority, precision, and scholarly care
- Vocabulary draws on discovery, knowledge, and enlightenment: "uncover," "witness," "illuminate," "endures"
- Emotional register is reverential, not sensational
- The visitor is addressed as an intelligent adult, not a tourist
- Every artifact description explains not just what the object is, but why it matters

### 3. Cialdini — Authority

Authority is the site's primary persuasion mechanism. Its rules for this project:

- All artifact entries cite real historical sources or scholarly context
- Curatorial voice frames sections ("Curated by the Exhibition Team")
- Provenance details appear on artifact cards (period, material, origin, current holding institution)
- Section introductions cite historical consensus or documented scholarly debate
- Visual hierarchy signals expertise: structured layout, restrained color, precise typography

---

## Page Architecture

The site has six pages. Each maps to a physical analog in a real museum.

| Page | File | Museum Analog |
|------|------|---------------|
| Home | `index.html` | Museum Entrance / Grand Foyer |
| Egypt Wing | `egypt.html` | Gallery Wing A |
| Greece Wing | `greece.html` | Gallery Wing B |
| Rome Wing | `rome.html` | Gallery Wing C |
| Artifact Detail | `artifact.html` | Object Study Room |
| About the Exhibition | `about.html` | Curator's Statement |

### Page: Home (`index.html`)

**Purpose:** Orient the visitor, establish the Sage voice, and draw them into the exhibition.

**Required sections:**
1. Hero — full-width, bold Bauhaus typographic statement. Headline: *"Three Civilizations. One Human Story."*
2. Exhibition Introduction — 2–3 paragraphs in Sage voice explaining the curatorial approach
3. Wing Navigation — three card-panels linking to Egypt, Greece, Rome wings
4. Curator's Note — Authority signal: a short attributed statement from "the curatorial team"
5. Footer — site name, navigation links, brief scholarly disclaimer

**Cialdini signal:** Curator's Note + scholarly framing in the intro establishes Authority on first contact.

---

### Page: Egypt Wing (`egypt.html`)

**Purpose:** Present Egypt as a coherent civilizational narrative, not a list of facts.

**Required sections:**
1. Wing Hero — civilization name, date range, one-line Sage thesis ("The civilization that measured eternity in stone")
2. Narrative Introduction — 2 paragraphs: what Egypt was, why it endures
3. Artifact Gallery — 3 artifact cards (see Artifact Card spec below)
4. Key Concepts — 2–3 concepts explained in Sage voice (e.g. Ma'at, hieroglyphs, dynastic succession)
5. Cross-Wing Connector — brief teaser linking Egypt's influence forward to Greece

**Artifact Cards (×3):**
- The Rosetta Stone
- The Mask of Tutankhamun
- The Book of the Dead

---

### Page: Greece Wing (`greece.html`)

**Purpose:** Present Greece as the philosophical and democratic pivot of Western civilization.

**Required sections:**
1. Wing Hero — civilization name, date range, Sage thesis ("Where reason first questioned the gods")
2. Narrative Introduction — 2 paragraphs
3. Artifact Gallery — 3 artifact cards
4. Key Concepts — 2–3 concepts (e.g. the polis, logos, the Olympic tradition)
5. Cross-Wing Connector — teaser linking Greece's legacy into Rome

**Artifact Cards (×3):**
- The Elgin Marbles (Parthenon Frieze)
- The Antikythera Mechanism
- The Discus Thrower (Discobolus)

---

### Page: Rome Wing (`rome.html`)

**Purpose:** Present Rome as the administrative and cultural synthesis of the ancient world.

**Required sections:**
1. Wing Hero — civilization name, date range, Sage thesis ("The empire that became the template for civilization")
2. Narrative Introduction — 2 paragraphs
3. Artifact Gallery — 3 artifact cards
4. Key Concepts — 2–3 concepts (e.g. Roman law, the aqueduct, Pax Romana)
5. Closing Reflection — brief epilogue: how these three civilizations together form a single arc

**Artifact Cards (×3):**
- The Colosseum (architectural model)
- Caesar's Commentarii de Bello Gallico
- The Augustus of Prima Porta

---

### Artifact Card Component Spec

Each artifact card must contain:

| Field | Required | Notes |
|-------|----------|-------|
| Artifact name | Yes | Bold, prominent |
| Date / Period | Yes | e.g. "circa 196 BCE" |
| Material | Yes | e.g. "Granodiorite" |
| Origin | Yes | e.g. "Memphis, Egypt" |
| Current holding | Yes | Authority signal — real institution name |
| Description | Yes | 2–3 sentences in Sage voice |
| Image placeholder | Yes | Styled `div` or `img` with descriptive `alt` |

---

### Page: Artifact Detail (`artifact.html`)

**Purpose:** A deeper look at a single artifact. Used as a template — content can be for any one artifact.

**Required sections:**
1. Artifact Hero — large image area + artifact name + period
2. Full Description — 3–4 paragraphs in Sage voice
3. Provenance Block — structured data: origin, material, date, institution, acquisition notes
4. Significance — why this object matters to the civilizational story
5. Related Artifacts — links or teasers to 2 other artifacts

---

### Page: About the Exhibition (`about.html`)

**Purpose:** Establish curatorial Authority. This page is the Cialdini centerpiece.

**Required sections:**
1. Exhibition Statement — mission and curatorial philosophy in Sage voice
2. Methodology — how artifacts were selected and why
3. Design Statement — brief explanation of the Bauhaus approach and why it serves the content
4. Scholarly Acknowledgment — citation of reference frameworks (e.g. Smithsonian curatorial standards)
5. Contact / Feedback (optional) — simple text invitation

---

## Content Invariants

These rules must not be violated in any sprint:

- All artifact descriptions must be factually accurate
- All holding institutions cited must be real (British Museum, Cairo Museum, Vatican Museums, etc.)
- No artifact claims should be invented or sensationalized
- The Sage voice must be consistent across all pages — no casual or informal copy
- Authority signals must appear on every page, not only the About page

---

## Acceptance Criteria

The spec is satisfied when all of the following are true:

- [ ] Six HTML pages exist and are valid, navigable, and link-consistent
- [ ] Bauhaus design system is applied consistently (grid, type, color, spacing)
- [ ] Sage voice is present in all body copy — no informal register
- [ ] Authority signals appear on every page
- [ ] Every artifact card contains all required fields
- [ ] The site reads as a curated exhibition, not a report or Wikipedia summary
- [ ] Navigation is clear and all inter-page links resolve
- [ ] The site passes a manual Smithsonian curator review (see `ai-curator-prompt.md`)

---

## Sprints Governed by This Spec

| Sprint | Goal |
|--------|------|
| Sprint 0 | HTML scaffold — all six pages with correct structure and navigation |
| Sprint 1 | CSS design system — Bauhaus tokens, typography, grid, color |
| Sprint 2 | Content pass — all copy, artifact cards, Sage voice, Authority signals |
| Sprint 3 | QA pass — AI curator review, gap identification, targeted fixes |

---

## Related Artifacts

- `design-spec.md` — design tokens, typography, color palette, spacing system
- `agent.md` — AI orchestration instructions for all sprint passes
- `ai-curator-prompt.md` — the Smithsonian curator QA prompt
- `README.md` — project overview, workflow explanation, submission link
