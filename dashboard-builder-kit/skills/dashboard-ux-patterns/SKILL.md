# Skill: Dashboard UX Patterns

Consult when building any dashboard page (executive, operational, explorer, reports). Every dashboard page shares this anatomy and these standards.

## Page anatomy

Header (page title, freshness indicator, org/role context) → global filters (date range, comparison period, segment) → local filters (page-specific) → KPI row → chart/table grid → detail table or drill-down panel → action area (export, save view, share).

## KPI card standard

Every KPI card includes: label, value, unit, comparison value (vs. prior period/target), variance (absolute + %), trend direction, target/benchmark line if applicable, sparkline, tooltip explaining the calculation, freshness timestamp, an accessible text summary (not just visual), and a restricted-state variant (blurred/locked with an explanation) for users without permission to see that metric.

## Table standard

Every data table supports: column priority (which columns hide first on narrow screens), sort, filter, search, pagination or virtualization (for large datasets), column resize/visibility toggle, sticky header, frozen first column where useful, row expansion for detail, bulk actions where relevant, export, right-aligned numeric columns with consistent decimal places, consistent date formatting, status shown as icon+label (not color alone), and its own mobile transformation (e.g., card list) rather than a horizontally-scrolled shrunken table.

## Filters, drill-down & saved views

- Filters are always visible as an "applied filters" summary with one-click clear.
- Drill-down and drill-through must be reversible (breadcrumb back to the parent view) and must update the URL so a filtered/drilled state is shareable and bookmarkable.
- Saved views persist filter + column + sort state under a name the user chooses; provide a default/reset view always available.

## Required states, designed separately (not just "loading spinner + done")

`loading`, `empty` (nothing configured yet — with guidance on how to configure it), `zero-data` (configured but no data this period), `no-results` (filters too narrow), `stale` (data older than the expected refresh interval, shown with a visible warning), `partial` (some widgets failed, others succeeded), `permission-denied` (restricted, with who to ask), `offline`, and `system-error` (with retry).

## Alerts

Alerts have a severity (info/warning/critical), a clear trigger condition in plain language, the metric and threshold that fired it, a timestamp, an acknowledge/dismiss action, and — for critical alerts — a required human acknowledgment before it's considered resolved (never auto-resolve a critical alert silently).

## Anti-patterns to avoid

- A dashboard page that only renders correctly when every widget has data.
- Filters that reset silently on navigation.
- KPI cards with a number and nothing else (no comparison, no freshness, no accessible text).
- Drill-down that isn't reflected in the URL.
