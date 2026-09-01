# Prompt 10 — Responsive, States & Accessibility Pass

Paste everything below the line into your coding agent.

---

Read `CLAUDE.md`'s quality bar and `skills/dashboard-ux-patterns/SKILL.md`'s state list. This is a hardening pass across every page built in Phases 04–09 — no new pages.

1. **Responsive** — verify small mobile, large mobile, tablet, small laptop, desktop, and wide desktop behavior for every page: sidebar collapse, filter bar adaptation (likely to a bottom sheet or drawer on mobile), `DataTable`'s card-list mobile transformation, `ChartCard` resizing, KPI row stacking, and modal-to-sheet transitions where appropriate. Prioritize which content matters most at each breakpoint rather than just shrinking the desktop layout.
2. **States** — for every page with data (Overview, Operations, Explore, Reports, Alerts), verify loading, empty, zero-data, no-results, stale, partial, permission-denied, offline, and system-error states all render correctly and distinctly, using the mock service's scenario data from Phase 03. Fix any page that only handles the populated state.
3. **Accessibility** — audit every page for: semantic landmarks and correct heading order, full keyboard operability (including `DataTable` sort/filter, `FilterBar`, chart "view as table" toggles, and the onboarding wizard's step navigation), visible focus states, sufficient color contrast against the actual token values from Phase 04, non-color status indicators, accessible form validation and live-region announcements (e.g., filter result counts, alert acknowledgments), touch target sizing, zoom/reflow up to 200%, and reduced-motion support everywhere Motion is used.

End with a checklist of what was fixed per page and any remaining gap that needs a real asset (e.g., a professionally reviewed color pairing) rather than a code fix.

---

**Before moving to Prompt 11, check:**
- Shrink your browser to phone width on Overview and Operations — do the tables genuinely transform into something usable, or just shrink and become unreadable?
- Pick one dashboard page and try to operate it entirely with the keyboard (filters, sort, drill-down, chart-to-table toggle) — note anything you get stuck on.
- Force a "stale" and a "permission-denied" state (via the mock scenarios) and confirm they look clearly different from a normal loading state.
