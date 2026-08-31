# Prompt 03 — Mock Data & Data Model

Paste everything below the line into your coding agent.

---

Read `docs/kpi-catalogue.md`, `docs/personas.md`, and `docs/brief.md`'s data domains/sources/refresh fields.

1. Write `docs/data-model.md`: a conceptual data model and concise data dictionary covering core entities, relationships, dimensions, measures, granularity, identifiers, timestamps, statuses, categories, geography, currency/units, targets, benchmarks, and audit/quality fields — all synthetic, tied to the brief's data domains and the KPI catalogue.
2. Define suggested JSON structures / API response shapes for each entity in `docs/data-model.md` — these are the shapes both the mock adapter and future live-API adapter must return, so pages never need to change when the backend does.
3. Implement `src/services/mock/` with realistic synthetic generators: at least 12 months of time-series data where relevant, covering normal, warning, critical, anomalous, missing, delayed, empty, restricted, and large-dataset scenarios (per `CLAUDE.md`'s state requirements). Clearly comment that this data is synthetic and does not represent real individuals or organizations.
4. Implement matching function signatures in `src/services/api/` as stubs (not yet calling a real endpoint) so the mock-to-live swap is a configuration change later, per `CLAUDE.md`.
5. Add a `src/services/index.js` that picks mock vs. api based on a single config flag/env variable, so components never import `mock/` or `api/` directly.

Do not build any UI yet. End with a summary of the entities/datasets created and which brief KPIs each one supports.

---

**Before moving to Prompt 04, check:**
- Open `docs/data-model.md` — do the value ranges look realistic for your industry (not obviously random numbers)?
- Confirm every state scenario (empty, error, stale, restricted, large-dataset) actually exists in the generated mock data, not just the normal/populated case.
- Nothing in the mock data resembles a real person, company, or account — spot-check names/emails/IDs.
