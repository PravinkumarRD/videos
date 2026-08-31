# Prompt 05 — Portfolio Showcase

Paste everything below the line into your coding agent.

---

Read `src/content/brief.js` for the full project list and `skills/design-system/SKILL.md`. Build on the Home page's Featured Work component pattern — don't duplicate its card design from scratch.

Build the Work/portfolio index page (`src/pages/Work.jsx`) as an interactive discovery experience, not a static grid:

1. **Filter system** — filter projects by whatever facets are present in the brief data (industry, service, project type, discipline). Use the FilterPill primitive. Filtering should re-flow the grid, not reload the page.
2. **Project cards** — consistent card treatment (image, title, one-line result, tags) with a hover preview state (e.g., reveal a secondary detail or crossfade to a second image on hover).
3. **Progressive loading** — if the project count is large, paginate or lazy-load; for a small brief-driven list, at minimum structure the code so it scales (don't hardcode "load all 6").
4. **Empty state** — a sensible message if a filter combination returns nothing.
5. Each card should link to `/work/:slug` (the case study route scaffolded in Phase 01), passing the correct project identifier.

No case study page content yet — that's Phase 06, so the destination route can still be a placeholder that now at least receives the right slug. No scroll animation yet — that's Phase 08. End with a summary of which filter facets were used, based on what the brief actually provided.

---

**Before moving to Prompt 06, check:**
- Click through every filter combination — does the grid update correctly, including an empty-state message when nothing matches?
- Click a project card and confirm the URL lands on `/work/:slug` with the right project's slug.
- Hover previews work with a mouse and are still usable (not broken) on a touch device.
