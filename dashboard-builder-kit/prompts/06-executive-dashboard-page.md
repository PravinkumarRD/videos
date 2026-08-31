# Prompt 06 — Executive Dashboard Page

Paste everything below the line into your coding agent.

---

Read `docs/kpi-catalogue.md`, `docs/personas.md` (the executive/decision-maker persona specifically), and `skills/dashboard-ux-patterns/SKILL.md`. Use the components from Phase 05 — do not build new one-off chart/table/KPI markup.

Build the executive overview dashboard (`src/pages/app/Overview.jsx`, route `/app/overview`) as the first fully real dashboard page:

1. Follow the page anatomy standard: header with freshness indicator → global filters (`FilterBar`) → KPI row (`KPICard` × the executive persona's top KPIs from the catalogue) → chart grid (`ChartCard` × 3–5 charts answering the executive persona's key questions, per the per-chart specification) → a summary detail table (`DataTable`) → action area (export, save view).
2. Every chart and KPI card must specify, in its data-fetching call, exactly which business question it answers (comment it inline) — pull this from `docs/kpi-catalogue.md` and the executive persona's jobs-to-be-done in `docs/personas.md`.
3. Wire real interactions: filter changes update KPIs/charts/table together; clicking a KPI card scrolls to or highlights its related chart; the "view as table" toggle works on every chart.
4. Demonstrate at least one AI-labeled insight (e.g., a simple trend/forecast callout) per `skills/data-visualization/SKILL.md`'s AI-insight labeling rule, sourced from the mock data — clearly marked as AI-generated with a confidence/uncertainty note and a link back to the source metric.

Ensure the page works correctly in every data state (loading/empty/error/stale/restricted) by exercising the mock service's scenario data from Phase 03. End with a summary of which KPIs/charts were included and why, tied to the executive persona's needs.

---

**Before moving to Prompt 07, check:**
- Change a filter (date range, segment) and confirm every KPI, chart, and the table actually update together — not just some of them.
- Find the AI-labeled insight — is it obviously marked as AI-generated, with a confidence note and a link back to its source metric?
- Ask: would an actual executive in this industry find this screen useful in 10 seconds, or is it just charts for the sake of charts?
