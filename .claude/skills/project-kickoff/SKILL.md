---
name: project-kickoff
description: Use when starting a new project to fill the minimum docs through a structured interview before any implementation.
---

# Project Kickoff

## Goal
Guide the user through filling the minimum required docs before any code is written.
Ask one question at a time. Wait for the answer. Fill the file. Move to the next.

## Rules
- Never ask more than one question at a time
- Never skip a required field
- After each answer, immediately write it into the relevant doc file
- If the user says "skip" or "not sure", write a placeholder and continue
- Do not suggest implementation until the interview is complete

## Interview sequence

### Step 1 — CLAUDE.md (Project-specific inputs)
Ask:
> "What's the name of your project?"

Write into `CLAUDE.md` → `Project name`.

---

Ask:
> "In one sentence, what does the app do?"

Write into `CLAUDE.md` → `Concept` and `docs/00_overview.md` → `One-line description`.

---

Ask:
> "Who are the target users? (be specific — role, context, pain)"

Write into `CLAUDE.md` → `Target users` and `docs/01_product_vision.md` → `Target users`.

---

Ask:
> "What is the core problem you're solving for them?"

Write into `CLAUDE.md` → `Core problem` and `docs/01_product_vision.md` → `Problem`.

---

### Step 2 — MVP scope (docs/02_mvp_features.md)
Ask:
> "List the 3 to 5 features that must be in the MVP. One per line."

Write into `docs/02_mvp_features.md` → `Must-have`.
Write summary into `CLAUDE.md` → `MVP scope`.

---

Ask:
> "What are you explicitly leaving out of the MVP? (features you will NOT build now)"

Write into `docs/02_mvp_features.md` → `Explicitly not in MVP`.

---

### Step 3 — Architecture (docs/04_tech_architecture.md)
Ask:
> "Any changes to the default stack? (Next.js / Express / PostgreSQL / JWT / Zustand). Say 'default' to keep it as-is."

If changes: write into `docs/04_tech_architecture.md` and update `CLAUDE.md` → `Default stack`.
If default: write confirmation in `docs/04_tech_architecture.md`.

---

### Step 4 — Scope guard (docs/20_mvp_scope_guard.md)
Ask:
> "What must stay small and simple in this MVP, no matter what? (e.g. no payment, no admin panel, no real-time)"

Write into `docs/20_mvp_scope_guard.md` → `What must stay small` and `What to reject in MVP`.

---

### Step 5 — Value proposition (docs/00_overview.md)
Ask:
> "Why should this app exist? What's the value proposition in 1-2 sentences?"

Write into `docs/00_overview.md` → `Value proposition` and `Why this app should exist`.

---

## After the interview

When all required fields are filled, output this summary:

```
Kickoff complete.

Project: [name]
Concept: [one-liner]
Users: [target users]
MVP: [list of must-haves]
Out of MVP: [exclusions]
Stack: [confirmed or custom]
Scope guard: [key constraints]

Docs filled: CLAUDE.md, 00_overview, 01_product_vision, 02_mvp_features, 04_tech_architecture, 20_mvp_scope_guard

Suggested next step:
> Now refine docs/09_api_routes_spec.md and docs/10_models_spec.md.
> Keep the MVP tight and consistent with docs/02_mvp_features.md.
```

Do not start building until the user gives the go.
