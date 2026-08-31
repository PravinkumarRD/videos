# Prompt 05 — Core Dashboard Components

Paste everything below the line into your coding agent.

---

Read `skills/data-visualization/SKILL.md` and `skills/dashboard-ux-patterns/SKILL.md` in full. Use the `ui/` primitives from Phase 04 and the data shapes from Phase 03 — do not invent new data shapes here.

Build the shared dashboard component layer in `src/components/`:

1. **`KPICard`** — implementing the full KPI card standard from `skills/dashboard-ux-patterns/SKILL.md` (label, value, unit, comparison, variance, trend, target, sparkline, tooltip, freshness, accessible text, restricted-state variant). Must handle loading/empty/zero/error/stale/restricted states as props.
2. **`ChartCard`** — a wrapper around Recharts chart types (line, area, bar, combo, pie/donut) that enforces the per-chart specification from `skills/data-visualization/SKILL.md`: title, freshness, accessible name, a "view as table" toggle to a linked accessible table, and consistent loading/empty/no-results/error/stale states.
3. **`DataTable`** — built on TanStack Table plus `ui/` primitives, implementing the full table standard from `skills/dashboard-ux-patterns/SKILL.md` (sort, filter, search, pagination, column visibility/resize, sticky header, row expansion, export action, and its own mobile card-list transformation).
4. **`FilterBar`** — global filters (date range, comparison period, segment) and a slot for page-local filters, using an Action + `useActionState` submission model, with an "applied filters" summary and one-click clear, and syncing filter state to the URL.
5. **`AlertBanner`**, **`FreshnessIndicator`**, **`ExportMenu`**, **`SavedViewMenu`** — smaller shared components per their definitions in `skills/dashboard-ux-patterns/SKILL.md`.

Build a `/dev/component-gallery` route showing each of these components in every state (loading/empty/zero/error/stale/restricted/populated) using the mock service from Phase 03, for review before they're wired into real pages. End with a summary of any state a component couldn't yet demonstrate due to a gap in the mock data.

---

**Before moving to Prompt 06, check:**
- Open `/dev/component-gallery` and actually look at every state for `KPICard`, `ChartCard`, and `DataTable` — a bad empty/error state here will be copied onto every dashboard page next.
- Click the "view as table" toggle on a sample chart — does the linked table make sense on its own?
- If any state is missing or looks unfinished, fix it now — it's much cheaper here than after 3 dashboard pages use it.
