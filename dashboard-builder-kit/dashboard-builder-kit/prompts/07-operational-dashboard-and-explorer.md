# Prompt 07 — Operational Dashboard & Data Explorer

Paste everything below the line into your coding agent.

---

Read `docs/personas.md` (the operational/analyst persona), `docs/kpi-catalogue.md`, and reuse every component from Phase 05 and the page pattern established in Phase 06 — don't rebuild the anatomy from scratch.

1. Build the operational dashboard (`src/pages/app/Operations.jsx`, route `/app/operations`) for the day-to-day operator persona: more granular KPIs than the executive view, a drill-down path from summary → detail (URL-reflected, per `skills/dashboard-ux-patterns/SKILL.md`), and at least one alert-triggering condition surfaced via `AlertBanner` tied to a real threshold on the mock data.
2. Build the ad hoc data explorer (`src/pages/app/Explore.jsx`, route `/app/explore`) letting the analyst persona freely choose dimensions/measures and a chart or table view of the result, using `DataTable` and `ChartCard` in a more flexible, user-driven configuration rather than a fixed dashboard layout. Support saving the current exploration as a saved view via `SavedViewMenu`.
3. Both pages must support cross-filtering (a filter or drill-down set on one widget narrows the others on the same page) and a reset-to-default action.

Verify both pages handle all required data states and are keyboard/screen-reader navigable through their filter and drill-down interactions. End with a summary of the drill-down paths implemented and any explorer capability deferred due to Recharts/TanStack Table limitations (flag per `skills/data-visualization/SKILL.md` rather than silently degrading).

---

**Before moving to Prompt 08, check:**
- Drill into a summary metric, then use the browser back button — does it correctly return to the parent view instead of leaving the app?
- Copy the URL after drilling/filtering, paste it in a new tab — does it reproduce the same view?
- If the agent flagged a capability it couldn't build with Recharts/TanStack Table, decide now whether that gap matters for your students or can be left as a known limitation.
