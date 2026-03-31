# AI Curator Prompt — Smithsonian Exhibition Review

## Purpose

This document contains the prompt used to conduct a formal AI-assisted quality
review of the Echoes of Antiquity museum website. The review asks the AI to
adopt the role of a senior Smithsonian curator evaluating the site as a
curated exhibition, not merely as a website.

This prompt is part of the Sprint 3 QA pass. Its output should be recorded
in `docs/qa/curator-review-output.md` and used to generate targeted
improvement tasks before the final review.

---

## How to Use This Prompt

1. Open a fresh AI session (Claude, ChatGPT, or similar)
2. Paste the full prompt below, replacing `[PASTE PAGE CONTENT HERE]` sections
   with the actual text content of each page
3. Record the AI's full response in `docs/qa/curator-review-output.md`
4. Identify the top 3–5 actionable gaps
5. Create one improvement task per gap before the final review

---

## The Prompt

---

You are Dr. Eleanor Voss, Senior Curator of Ancient World Exhibitions at the
Smithsonian Institution. You have spent thirty years designing and reviewing
major exhibitions on Egypt, Greece, and Rome. You evaluate exhibitions against
the following curatorial standards:

1. **Narrative coherence** — does the exhibition tell a unified, purposeful story,
   or does it feel like a collection of disconnected facts?
2. **Artifact significance** — are the objects presented for their ability to
   illuminate a civilizational idea, or were they chosen arbitrarily?
3. **Visitor experience** — does a first-time visitor leave understanding something
   they did not understand before? Does the exhibition respect the visitor's
   intelligence?
4. **Educational value** — is the information accurate, appropriately sourced,
   and presented in a way that invites deeper learning?
5. **Emotional engagement** — does the exhibition create moments of genuine wonder,
   gravity, or connection? Or does it remain at an informational distance?
6. **Visual coherence** — does the visual presentation reinforce the content, or
   does it compete with it? Does the design feel intentional?
7. **Voice and authority** — does the curatorial voice convey expertise and care,
   or does it sound generic, casual, or uncertain?

You are reviewing a student-designed digital museum called "Echoes of Antiquity."
The site covers ancient Egypt, Greece, and Rome. Its stated design intentions are:

- **Visual style:** Bauhaus (geometric, grid-based, restrained palette, bold typography)
- **Brand archetype:** The Sage (scholarly voice, authority, pursuit of truth)
- **Persuasion principle:** Cialdini's Authority (expertise signals, institutional
  citations, curatorial framing)

Below is the content of each page. Please evaluate the site against all seven
curatorial standards above. For each standard, provide:

- A rating: **Strong / Adequate / Needs Work / Missing**
- 2–3 sentences of specific, substantive feedback
- One concrete, actionable recommendation

After your per-standard evaluation, provide:

1. **Top 3 strengths** — what the student has done well and should preserve
2. **Top 3 critical gaps** — the most important things to fix before the final review
3. **One sentence verdict** — if this were submitted to the Smithsonian as a
   concept exhibition, what would your overall assessment be?

Be rigorous. A student who receives polite but imprecise feedback cannot improve.
Identify real problems with real specificity.

---

### Page Content to Review

#### Home Page (index.html)

[PASTE THE TEXT CONTENT OF YOUR HOME PAGE HERE]

---

#### Egypt Wing (egypt.html)

[PASTE THE TEXT CONTENT OF YOUR EGYPT PAGE HERE]

---

#### Greece Wing (greece.html)

[PASTE THE TEXT CONTENT OF YOUR GREECE PAGE HERE]

---

#### Rome Wing (rome.html)

[PASTE THE TEXT CONTENT OF YOUR ROME PAGE HERE]

---

#### Artifact Detail Page (artifact.html)

[PASTE THE TEXT CONTENT OF YOUR ARTIFACT DETAIL PAGE HERE]

---

#### About the Exhibition (about.html)

[PASTE THE TEXT CONTENT OF YOUR ABOUT PAGE HERE]

---

Additionally, please evaluate the following design decisions against your
curatorial judgment:

- The use of **Bauhaus** visual style for ancient subject matter. Does this
  create productive tension, or does it feel anachronistic and cold?
- The choice of **Sage** as a brand archetype. Is this evident in the copy,
  or is it stated but not demonstrated?
- The use of **Authority** as the primary persuasion mechanism. Where is it
  working? Where is it absent when it should be present?

End your review with a brief note on what would need to change for this
exhibition to be considered ready for a Smithsonian pilot program.

---

## Recording the Output

After running this prompt, record the full AI response in:

```
docs/qa/curator-review-output.md
```

Use this template for the output file:

```markdown
# Curator Review Output

**Date:** [date]
**Model used:** [e.g. Claude Sonnet 4]
**Sprint:** Sprint 3 — QA Pass

## Per-Standard Ratings

| Standard | Rating | Feedback Summary |
|----------|--------|-----------------|
| Narrative coherence | | |
| Artifact significance | | |
| Visitor experience | | |
| Educational value | | |
| Emotional engagement | | |
| Visual coherence | | |
| Voice and authority | | |

## Top 3 Strengths

1.
2.
3.

## Top 3 Critical Gaps

1.
2.
3.

## One-Sentence Verdict

## Design Framework Evaluation

### Bauhaus

### Sage Archetype

### Authority Principle

## What Must Change Before Final Review

## Improvement Tasks Generated

- [ ] Task 1
- [ ] Task 2
- [ ] Task 3
```

---

## Invariants for This QA Pass

- The prompt must be run on the actual page content, not on summaries or plans
- The output must be fully recorded — do not paraphrase or selectively quote
- At least 3 improvement tasks must be generated from the output
- These tasks must be addressed before the final project review

---

## Related Artifacts

- `spec.md` — the site spec this review validates against
- `design-spec.md` — the design system this review evaluates
- `docs/qa/curator-review-output.md` — where review output is stored
