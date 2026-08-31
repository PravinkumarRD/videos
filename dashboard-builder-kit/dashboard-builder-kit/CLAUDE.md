# CLAUDE.md — Project Standing Instructions

Read automatically at the start of every session. Applies to every prompt in `prompts/` — individual prompts won't repeat these rules.

## What this project is

A SaaS-style analytics dashboard product: marketing landing, authentication, onboarding, multiple role-aware dashboards, a data explorer, reports/alerts, and org/user settings — built on realistic synthetic mock data designed to be swapped for live APIs later without rewriting pages.

## Tech stack (non-negotiable unless `docs/brief.md` says otherwise)

- **React 19**, **JavaScript** (ES2022+), not TypeScript. Use JSDoc (`@typedef`, `@param`) for non-trivial function/data shapes and `prop-types` on components whose props aren't obvious from usage.
- **Vite** as the build tool.
- **React Router** (data router) for routing, including role-based route guards.
- **Tailwind CSS**, driven entirely by design tokens (see `skills/design-system/SKILL.md`) — no magic numbers.
- **Motion** (successor to Framer Motion) for the limited, purposeful animation a dashboard needs (state transitions, not decoration).
- **Recharts** as the single charting library, and **TanStack Table** as the single table/grid library. Do not add a second overlapping charting or table library — see `skills/data-visualization/SKILL.md` before touching either.
- Use React 19 primitives where they genuinely fit: `use()` for reading async data/context, Actions + `useActionState` for every form (sign-in, onboarding steps, filters-as-forms, settings), `useOptimistic` for saved-view/favorite toggles, ref-as-prop instead of `forwardRef`.

## Mock data & API-readiness (critical, applies to every phase)

- All data is **synthetic**. Never use real people, real customers, real employees, real patient/financial data, or anything resembling it. Label mock data as mock in code comments and in any UI that displays "data as of" / freshness info.
- Every data access goes through a **service/adapter layer** (`src/services/`), never fetched directly inside components. A mock adapter today must be swappable for a live API adapter later by changing configuration, not by rewriting pages.
- Design every dataset and component to handle: normal, warning, critical, anomalous, missing, delayed, empty, restricted (no permission), and large-dataset states — not just the "happy path" populated state.

## Before writing code in any phase

1. Read `docs/brief.md` for real product/industry/user/KPI content. Never invent conflicting facts; label placeholders clearly where the brief is silent.
2. Read the relevant file(s) in `skills/` for the phase.
3. Read what already exists in the repo — extend established tokens, adapters, and components rather than duplicating patterns per page.

## Quality bar every phase must hold to

- Mobile-first, fully responsive across small mobile → wide desktop.
- WCAG 2.2 AA: semantic structure, landmarks, correct heading order, full keyboard access, visible focus, accessible chart alternatives (tabular data alongside every chart), non-color status indicators, reduced-motion support.
- Target Lighthouse 95+ on Performance, Accessibility, SEO, Best Practices for the marketing/auth pages; dashboard pages prioritize interaction responsiveness and accessible data over raw Lighthouse score.
- No vanity metrics without decision value; no misleading axes, unlabeled units, or unsupported causal claims in any chart or copy.
- Every KPI's calculation must stay consistent everywhere it appears.

## Working style

- Build incrementally, one phase at a time — don't build later-phase features while executing an earlier phase; flag it instead if a prompt seems to need something not yet built.
- After each phase, briefly summarize what was created/changed and flag assumptions made due to gaps in `docs/brief.md`.
- Folder conventions: `src/components/ui/` (primitives), `src/components/` (composed, e.g. KPICard, ChartCard, DataTable), `src/pages/`, `src/services/` (data adapters — `mock/` and `api/` subfolders), `src/content/` (brief-derived static content), `src/styles/` (tokens).
