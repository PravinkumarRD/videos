# Prompt 02 — Product Strategy & Information Architecture

Paste everything below the line into your coding agent.

---

Read `docs/brief.md` and `CLAUDE.md`. This phase produces strategy documents only — no code changes.

Write `docs/strategy.md` covering:

- Product name (3 options if `docs/brief.md` didn't supply one, with a recommended choice and rationale), product category, one-sentence positioning statement
- Mission/vision, core value proposition, differentiators, product principles
- The specific business problem being solved, tied to the industry/users/decisions in the brief — not generic "make better decisions with data" language
- MVP scope vs. later roadmap
- Success/adoption/engagement/business-impact metrics for the product itself (distinct from the KPIs the dashboard displays to its users)

Write `docs/personas.md` with at least 3 personas drawn from the brief's primary/secondary users, each covering: role & responsibilities, technical proficiency, pain points & goals, information needs & most important KPIs, usage frequency & typical tasks, decisions supported, accessibility/environmental considerations, and their definition of success. Include one end-to-end jobs-to-be-done workflow per persona.

Write `docs/sitemap.md` covering: complete sitemap matching the routes scaffolded in Phase 01 (plus any the brief's required pages imply), primary/secondary/utility navigation, breadcrumb rules, role-based route variations (which persona sees which routes), and mobile navigation mapping.

Write `docs/kpi-catalogue.md`: every KPI implied by the brief's data domains and primary KPIs field, each with a name, plain-language definition, calculation logic, unit, good-direction (up/down), typical target-setting approach, and which persona(s) care about it most. Flag any KPI that risks being a "vanity metric" without clear decision value.

Base every claim on `docs/brief.md`; label assumptions explicitly where the brief is silent. End with a summary of the key strategic decisions made.

---

**Before moving to Prompt 03, check:**
- Read `docs/kpi-catalogue.md` — does every KPI have a clear, specific calculation, or are any of them vague ("engagement score") without a real formula?
- The personas in `docs/personas.md` feel like the actual users in your brief, not generic "Sarah, 34, busy professional" filler.
- Flag anything marked as a "vanity metric" now — decide whether to keep, cut, or reframe it before it gets built into a dashboard.
