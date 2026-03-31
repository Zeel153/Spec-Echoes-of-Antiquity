# Agent Instructions — Echoes of Antiquity

## Purpose

This file tells an AI agent how to work on this project. It is the equivalent
of a project brief handed to a contractor. Every sprint pass begins by reading
this file. No agent should proceed without it.

---

## Project Summary

**Site name:** Echoes of Antiquity
**Type:** Digital museum exhibition
**Stack:** Plain HTML, CSS, JavaScript (no frameworks)
**Governing spec:** `spec.md`
**Design system:** `design-spec.md`

**Three design frameworks (non-negotiable):**
1. Bauhaus visual style — all visual decisions derive from `design-spec.md`
2. Sage brand archetype — all copy must reflect this voice
3. Cialdini Authority — persuasion signals must be present on every page

---

## Invariants — Never Violate These

These rules apply across all sprints and all roles:

- Do not introduce changes outside the scope of the current sprint
- Do not use raw hex values in CSS — all colors use `--color-*` tokens
- Do not use any typeface other than Oswald and Lora
- Do not use informal register in any copy — the Sage voice is required
- Do not invent artifact facts — all information must be historically accurate
- Do not add decorative elements not specified in `design-spec.md`
- Do not treat the work as done until the acceptance criteria in `spec.md` are checked

---

## Sprint Role Instructions

### Role: Implementer

Use this role for Sprint 0 (scaffold), Sprint 1 (CSS), and Sprint 2 (content).

**Prompt pattern:**
```
You are implementing [Sprint N] of the Echoes of Antiquity project.

Your role: Implementer
Your scope: [list exact files you are allowed to create or modify]
Your invariants: [paste the invariants section above]

The governing spec is spec.md. The design system is design-spec.md.

Sprint goal: [state the sprint goal]

Tasks:
1. [Task 1]
2. [Task 2]
...

Acceptance criteria for this sprint:
- [ ] Criterion 1
- [ ] Criterion 2

Do not modify any file outside your listed scope.
Do not declare the sprint complete until all criteria are checkable.
```

---

### Role: Auditor

Use this role before any sprint begins, to QA the sprint plan against the spec.

**Prompt pattern:**
```
You are auditing Sprint [N] of the Echoes of Antiquity project before
implementation begins.

Your role: Auditor
Your task: Identify gaps, contradictions, or missing criteria in the sprint plan.

Read the following:
1. spec.md [paste or reference]
2. design-spec.md [paste or reference]
3. The sprint plan for Sprint N [paste]

Answer these questions:
- Does the sprint plan contradict the spec in any way?
- Are there missing acceptance criteria that should be added?
- Are there any tasks that are out of scope for this sprint?
- Is anything ambiguous that would cause drift during implementation?

Return a numbered list of issues. If there are no issues, state that clearly.
```

---

### Role: Reviewer

Use this role after each sprint implementation, to QA the output.

**Prompt pattern:**
```
You are reviewing the Sprint [N] implementation of the Echoes of Antiquity
project.

Your role: Reviewer
Your task: Check the implementation against the sprint acceptance criteria
and the governing spec.

Read the following:
1. The sprint acceptance criteria [paste]
2. The relevant sections of spec.md [paste]
3. The implementation output [paste file content]

For each acceptance criterion, state:
- PASS — criterion is satisfied
- FAIL — criterion is not satisfied, with specific evidence
- PARTIAL — criterion is partly satisfied, with what remains

Then list any drift (changes made outside the sprint scope).
Then state your overall verdict: ACCEPTED or REJECTED.
```

---

### Role: Smithsonian Curator

Use this role for Sprint 3 QA. Full prompt is in `ai-curator-prompt.md`.

This role evaluates the site not as code, but as an exhibition. It uses seven
curatorial standards. Its output must be recorded in `docs/qa/curator-review-output.md`.

---

## Session Startup Procedure

At the start of every AI session working on this project:

1. Read this file (`agent.md`) in full
2. Read the governing `spec.md`
3. Read `design-spec.md` if the session involves any visual or CSS work
4. Identify the current sprint from the Sprint Log in `README.md`
5. State your role and scope out loud before beginning

This procedure prevents context loss between sessions.

---

## What Good Prompting Looks Like

Good prompts on this project:
- Name the sprint number and role explicitly
- List the files in scope
- Paste or reference the relevant acceptance criteria
- State what must not be touched

Vague prompts that will cause drift:
- "Improve the site"
- "Make it look better"
- "Fix the copy"
- "Add more content"

If you catch yourself writing a vague prompt, stop and convert it into a
bounded sprint instruction using the patterns above.

---

## Related Artifacts

- `spec.md` — the site-level contract
- `design-spec.md` — the visual design system
- `ai-curator-prompt.md` — the Sprint 3 QA prompt
- `README.md` — the project overview and sprint log
- `docs/qa/curator-review-output.md` — the recorded curator review output
