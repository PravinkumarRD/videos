# Prompt 12 — Testing, QA & Launch Checklist

Paste everything below the line into your coding agent.

---

This is the final phase. Read `CLAUDE.md`'s quality bar one more time.

1. Run a full build and fix any build/lint errors.
2. Write measurable tests (not subjective criteria like "user-friendly") covering: KPI/chart calculation accuracy against the mock data generators from Phase 03, filter and drill-down behavior, `DataTable` sort/filter/pagination, role-based access control from Phase 11, all required data states from Phase 10, export accuracy (including the CSV formula-injection guard), and the sign-in/onboarding Actions.
3. Walk the app end-to-end as each persona from `docs/personas.md`: sign in → onboarding (first-time) → Overview → Operations → Explore → Reports → Alerts → Settings. Fix any broken link, dead route, or console error.
4. Remove or gate the `/dev/style-guide` and `/dev/component-gallery` routes from the production build (they were for internal review in Phases 04–05).
5. Run (or simulate, describing expected results if Lighthouse isn't directly runnable) a Lighthouse pass on the marketing/sign-in pages; report Performance, Accessibility, SEO, Best Practices and fix anything below the target in `CLAUDE.md`.
6. Produce `docs/launch-checklist.md` listing: every place mock data still stands in for a real integration and what config/adapter change is needed to go live (per the mock/live swap pattern from Phase 03), any compliance item flagged in Phase 11 still needing human/legal review, and any responsive/accessibility item that needs a real design review rather than a code fix.

End with a summary of final test/Lighthouse status and the launch checklist location.

---

**Final check before calling it done:**
- Walk the whole app yourself as each persona: sign in → onboarding → Overview → Operations → Explore → Reports → Alerts → Settings.
- Open `docs/launch-checklist.md` and treat every item as a real to-do, not a formality — each mock/placeholder needs a real owner before going live.
- If something still feels off after all 12 phases, send the agent a targeted follow-up naming the exact page and problem, rather than starting the whole sequence over.
