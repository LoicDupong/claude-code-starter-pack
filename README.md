# Claude Code Starter Pack

A docs-first, MVP-focused starter pack for building SaaS and product apps with Claude Code.

Created by **Loïc Dupong**.

---

## Philosophy

This pack enforces a simple discipline: **write the docs before writing the code.**

Claude Code reads your documentation as its source of truth. The more precise your docs, the more focused and predictable the build. This pack gives you the full document structure, Claude operating rules, reusable skills, and subagent definitions — ready to copy into any new project.

Core principles baked in:
- MVP first, always
- Mobile first by default
- Docs drive decisions, not the other way around
- One bounded step at a time
- No feature creep, no silent scope expansion

---

## What's Included

```
.
├── CLAUDE.md                    # Claude operating rules for your project
├── START_HERE.md                # Quick setup guide
├── docs/
│   ├── 00_overview.md           # Project name, description, value proposition
│   ├── 01_product_vision.md     # Problem, target users, use cases
│   ├── 02_mvp_features.md       # Must-have / explicitly not in MVP / post-MVP
│   ├── 03_ux_ui_direction.md    # UX principles, visual direction, key screens
│   ├── 04_tech_architecture.md  # Frontend, backend, database, high-level flow
│   ├── 05_claude_context_pack.md# Summary for Claude: constraints, priorities
│   ├── 06_database_schema.md    # Tables, key fields, relations
│   ├── 07_user_flows.md         # Main flow, edge cases
│   ├── 08_build_prompt.md       # Current implementation prompt block
│   ├── 09_api_routes_spec.md    # Public and protected routes, payload rules
│   ├── 10_models_spec.md        # Model list, validations
│   ├── 11_front_structure.md    # App structure, shared components, state
│   ├── 12_ui_pages_map.md       # Pages list, access rules
│   ├── 13_design_system.md      # Colors, typography, spacing, UI components
│   ├── 14_copywriting.md        # Tone, core UI texts, empty/error/success states
│   ├── 15_security_rules.md     # Access control, validation, protections
│   ├── 16_build_order.md        # Ordered implementation steps
│   ├── 17_notifications.md      # Notification events (fill or remove)
│   ├── 18_pwa_setup.md          # Manifest, service worker (fill or remove)
│   ├── 19_env_config.md         # Frontend and backend env variables
│   └── 20_mvp_scope_guard.md    # Scope boundaries, rejection criteria
├── .claude/
│   ├── skills/
│   │   ├── mvp-scope-guard/     # Checks if a feature belongs in MVP
│   │   ├── api-review/          # Reviews API routes for consistency
│   │   ├── ui-consistency/      # Reviews page structure and interaction
│   │   └── bug-triage/          # Diagnoses and prioritizes bugs
│   └── agents/
│       ├── product-strategist.md# MVP decisions and scope review
│       ├── backend-builder.md   # Routes, models, validation, auth
│       ├── frontend-builder.md  # UI structure, components, UX states
│       ├── security-reviewer.md # Route exposure, validation gaps, abuse cases
│       └── qa-reviewer.md       # Alignment checks and regression checklists
```

---

## Default Stack

| Layer      | Technology                     |
|------------|-------------------------------|
| Frontend   | Next.js App Router + SCSS Modules |
| Backend    | Express                       |
| Database   | PostgreSQL + Sequelize        |
| Auth       | JWT + argon2                  |
| State      | Zustand                       |
| API        | REST                          |

---

## How to Use

### 1. Copy into your new repo

```bash
cp -r claude-code-starter-pack/. your-new-project/
```

Copy at minimum:
- `CLAUDE.md`
- `docs/`
- `.claude/skills/`
- `.claude/agents/`
- `START_HERE.md`

### 2. Fill the minimum docs first

Before writing any code, fill at least:

- `docs/00_overview.md`
- `docs/01_product_vision.md`
- `docs/02_mvp_features.md`
- `docs/04_tech_architecture.md`
- `docs/20_mvp_scope_guard.md`

Also update `CLAUDE.md` with your project-specific inputs (name, concept, target users, MVP scope).

### 3. Open Claude Code and start with this prompt

```
Read CLAUDE.md and the docs folder first.
Summarize the project concept, target users, MVP scope, architecture choices, and missing information.
Do not implement anything yet.
```

### 4. Work step by step

Example next prompt:

```
Now refine docs/09_api_routes_spec.md and docs/10_models_spec.md.
Keep the MVP tight and consistent with docs/02_mvp_features.md.
```

### 5. Use subagents for bounded reviews

Delegate only specific, contained tasks:
- backend spec review → `backend-builder`
- frontend structure review → `frontend-builder`
- security pass → `security-reviewer`
- QA consistency → `qa-reviewer`
- scope decisions → `product-strategist`

Do not use subagents to build the entire project in one shot.

---

## Skills

Skills are reusable playbooks invoked by Claude Code during the build.

| Skill | When to use |
|-------|------------|
| `project-kickoff` | At the very start — interviews you question by question to fill the minimum docs before any code |
| `mvp-scope-guard` | Before adding any new feature — checks if it belongs in MVP |
| `api-review` | After drafting API routes — reviews naming, auth, and payload clarity |
| `ui-consistency` | After building screens — checks mobile-first structure and UX coherence |
| `bug-triage` | When a bug appears — diagnoses root cause and scopes the smallest safe fix |

---

## License

Free to use and adapt for any project.

---

*Made by Loïc Dupong — [loic@dgco-it.be](mailto:loic@dgco-it.be)*
