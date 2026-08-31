# Universal Analytics Dashboard — Vibe Coding Kit

This turns the RTCFCT dashboard meta-prompt into a **buildable sequence** instead of a prompt that generates another prompt. Students paste one prompt per phase into a coding agent (Claude Code, Cursor, Windsurf) and watch a real React 19 SaaS-style analytics dashboard grow — mock data first, API-ready by design.

## How students use this

1. Copy this whole folder as the project root (or point Claude Code at it).
2. Open `docs/BRIEF-TEMPLATE.md`, fill in the placeholders (industry, users, KPIs, data domains, required pages, etc.), save as `docs/brief.md`. This is the only manual step.
3. Start the coding agent in this folder.
4. Read `prompts/00-fill-brief-instructions.md` first (checklist, not a paste-in prompt).
5. From `prompts/01-project-scaffold.md` onward, **paste one file at a time, in numeric order**, letting each phase finish and get reviewed before pasting the next.
6. `CLAUDE.md` is read automatically every session — it holds the standing stack, mock-data, states, and accessibility rules so prompts don't repeat them.
7. `skills/` holds the reference standards (component architecture, design tokens, chart/table library rules, dashboard UX patterns) every prompt tells the agent to consult first.

## Sequence

| # | Phase | Produces |
|---|-------|----------|
| 00 | Brief checklist | `docs/brief.md` |
| 01 | Scaffold | Vite + React 19 + JS + Tailwind project, routing skeleton |
| 02 | Product strategy & IA | `docs/strategy.md`, `docs/sitemap.md`, personas |
| 03 | Mock data & schema | Synthetic data model + API-shaped adapters |
| 04 | Design system | Tokens (light/dark) + base component library |
| 05 | Core dashboard components | KPI cards, chart wrappers, table, filter bar |
| 06 | Executive dashboard page | First full dashboard screen |
| 07 | Operational dashboard & explorer | Second dashboard + ad hoc data explorer |
| 08 | Reports, alerts, saved views | Scheduled reports, alerting, saved views |
| 09 | Auth, onboarding, settings | Sign-in, onboarding flow, org/user/role settings |
| 10 | Responsive, states & accessibility | All breakpoints, loading/empty/error/stale/restricted states, WCAG 2.2 AA |
| 11 | Security, privacy & responsible AI | RBAC enforcement, safe exports, AI-insight labeling |
| 12 | Testing & final QA | Acceptance tests, Lighthouse pass, launch checklist |

## Scope note

This kit builds the **responsive web application** (marketing landing + auth + onboarding + dashboards + reports + settings) as one React app — it does not build a separate native mobile app or a full CMS-driven marketing site. If your students need those, treat them as extensions after Phase 12, following the same "read the brief, read the skills, build one phase" pattern.
