# Echoes of Antiquity

A curated digital museum exhibition exploring the civilizations of ancient Egypt,
Greece, and Rome. Built using plain HTML, CSS, and JavaScript as part of a
spec-driven AI-orchestrated development process.

**Live site:** [GitHub Pages link — add after deployment]

---

## The Exhibition

Echoes of Antiquity presents three civilizations not as isolated historical
chapters, but as a single, unfolding human conversation — one whose ideas in
law, philosophy, art, and governance still shape the world we inhabit.

Each gallery wing presents curated artifacts alongside narrative copy designed
to illuminate civilizational ideas, not merely catalog objects.

---

## Design Framework

### Visual Style — Bauhaus

The site uses Bauhaus as its governing visual tradition. Bauhaus principles
applied here: grid-first layout, restricted 5-token color palette, two-typeface
system (Oswald for headings, Lora for body), geometric spacing tokens, and
generous whitespace. The restraint of the design frames the richness of the
content — the artifacts speak, the design listens.

All design decisions are recorded in `design-spec.md`.

### Brand Archetype — The Sage

The Sage archetype drives the site's voice, vocabulary, and emotional character.
The curatorial voice is scholarly, precise, and reverential. Visitors are
addressed as intelligent adults. Every artifact description explains not just
what an object is, but why it matters to the civilizational story.

### Persuasion Principle — Cialdini's Authority

Authority is the primary persuasion mechanism. Signals include: institutional
citations (British Museum, Egyptian Museum Cairo, Vatican Museums), artifact
provenance data, curatorial voice framing, and scholarly disclaimers.
Authority signals appear on every page, not only the About page.

---

## Agentic Orchestration Process

This project was built using a spec-driven AI orchestration workflow adapted
from the reference repository at:

> https://github.com/kaw393939/nextjs_ai_orchestration_spec_sprint_process

### Core Principle

High-quality AI-assisted work requires structured constraints. The process
prevents drift (AI changing things outside the requested scope), context loss
(decisions falling out of the working session), and ambiguous completion
(output that looks done but hasn't been verified).

### Workflow

```
Spec → QA → Sprint → QA → Implement → QA
```

All work flows through this loop. No sprint begins without a governing spec.
No implementation is accepted without a QA pass.

### Artifacts

| Artifact | Purpose |
|----------|---------|
| `spec.md` | The site-level contract: pages, content model, acceptance criteria |
| `design-spec.md` | Design tokens, typography, spacing, component rules |
| `ai-curator-prompt.md` | Smithsonian curator QA prompt used in Sprint 3 |
| `agent.md` | AI agent instructions for each sprint role |
| `docs/qa/curator-review-output.md` | Recorded output of the curator QA review |

### Sprint Log

| Sprint | Goal | Status |
|--------|------|--------|
| Sprint 0 | HTML scaffold — all six pages, correct structure, navigation | Complete |
| Sprint 1 | CSS design system — Bauhaus tokens, typography, grid, color | Complete |
| Sprint 2 | Content pass — all copy, artifact cards, Sage voice, Authority signals | Complete |
| Sprint 3 | QA pass — AI curator review, gap identification, targeted fixes | In Progress |

### Why The Process Exists

Without this structure, four problems recur in AI-assisted work:

1. **Drift** — the AI changes adjacent files that were not in scope
2. **Context loss** — decisions made in one session fall out of the next
3. **Ambiguous completion** — work feels done before it is actually verified
4. **Weak accountability** — without artifacts, decisions are not auditable

Specs, sprint docs, QA passes, and the curator review are the answers to
those four problems.

---

## How AI Was Used

### As an Implementer (Sprints 0–2)
AI was prompted with bounded sprint contracts specifying exact files to create,
exact design tokens to apply, and exact acceptance criteria to satisfy.
Each prompt included role framing ("You are implementing Sprint 1 of the
Echoes of Antiquity project"), scope definition (which files were in bounds),
and invariants (which rules could not be violated).

### As a Smithsonian Curator (Sprint 3)
AI was prompted as Dr. Eleanor Voss, a senior Smithsonian curator, to evaluate
the site against seven curatorial standards: narrative coherence, artifact
significance, visitor experience, educational value, emotional engagement,
visual coherence, and voice/authority. The full prompt is in
`ai-curator-prompt.md`. The full output is in `docs/qa/curator-review-output.md`.

### What the Curator Review Found
[Add summary of top findings after running Sprint 3]

---

## File Structure

```
.
├── index.html          # Home — Museum Entrance
├── egypt.html          # Wing A — Egypt
├── greece.html         # Wing B — Greece
├── rome.html           # Wing C — Rome
├── artifact.html       # Object Study Room
├── about.html          # Curator's Statement
├── css/
│   └── styles.css      # Bauhaus design system
├── spec.md             # Site-level governing spec
├── design-spec.md      # Design token reference
├── ai-curator-prompt.md # Sprint 3 QA prompt
├── agent.md            # AI orchestration instructions
└── docs/
    └── qa/
        └── curator-review-output.md
```

---

## QA Checklist

Before submission, verify:

- [ ] All six pages load without errors
- [ ] All internal navigation links resolve
- [ ] Design tokens are applied consistently — no raw hex values in CSS
- [ ] Artifact cards contain all required fields (name, period, material, origin, institution, description)
- [ ] Sage voice is consistent across all body copy
- [ ] Authority signals appear on every page
- [ ] Mobile layout works at 640px breakpoint
- [ ] Curator review has been run and output recorded
- [ ] At least 3 improvements from the curator review have been implemented
