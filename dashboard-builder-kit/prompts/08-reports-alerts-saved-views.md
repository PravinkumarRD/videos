# Prompt 08 — Reports, Alerts & Saved Views

Paste everything below the line into your coding agent.

---

Read `docs/brief.md`'s reporting requirements field and `skills/dashboard-ux-patterns/SKILL.md`'s alert standard. Reuse `AlertBanner`, `ExportMenu`, and `SavedViewMenu` from Phase 05.

1. Build a Reports page (`src/pages/app/Reports.jsx`, route `/app/reports`) listing available/scheduled reports (mock data), each with a name, schedule (e.g., weekly/monthly), recipients, last-run status, and a manual "run now" action. Support configuring a new scheduled report via an Action-based form (name, source dashboard/view, schedule, recipients). Exports should be CSV/PDF-labeled mock actions with a note on formula-injection protection for CSV exports (never emit raw user-controlled strings starting with `=`, `+`, `-`, `@` unescaped).
2. Build an Alerts page (`src/pages/app/Alerts.jsx`, route `/app/alerts`) listing active/resolved alerts using the alert standard from `skills/dashboard-ux-patterns/SKILL.md`: severity, plain-language trigger condition, metric + threshold, timestamp, acknowledge/dismiss action, and a required human-acknowledgment step for critical alerts (no silent auto-resolve).
3. Consolidate saved views: ensure `SavedViewMenu` works consistently across Overview, Operations, and Explore (Phases 06–07), storing filter/column/sort state under a user-chosen name with a default/reset view always available.

End with a summary of the report/alert scenarios built and confirm the CSV export sanitization was implemented.

---

**Before moving to Prompt 09, check:**
- Try to acknowledge/dismiss a critical alert — it should require an explicit human action, never auto-resolve.
- Confirm the agent's summary explicitly states the CSV export was sanitized against formula injection — don't take this on faith, ask to see the relevant code if unsure.
- Save a view on one dashboard, navigate away, come back — does the saved view actually persist and reload correctly?
