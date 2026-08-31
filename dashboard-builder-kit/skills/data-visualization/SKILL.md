# Skill: Data Visualization Strategy

Consult before adding any chart, table, or map. This project uses exactly **one** charting library (Recharts) and **one** table library (TanStack Table) — do not add a second overlapping library.

## Library rules

- **Recharts** — for all standard charts: line, area, bar, stacked bar, combo, scatter, pie/donut (used sparingly), sparkline. Free/open-source (MIT), React-native API, reasonably accessible when wrapped correctly. Not suited to very large (10k+ point) real-time streaming visuals or advanced geo/network diagrams — flag this limitation if the brief needs those, rather than silently degrading quality.
- **TanStack Table** — headless table logic (sort, filter, pagination, column visibility, row selection) paired with our own styled markup from `ui/`. Free/open-source (MIT). For genuinely large datasets, pair with row virtualization; note in code comments when a table needs it.
- Do not silently introduce AG Grid, Chart.js, D3, ECharts, or any other library "just for one chart" — if the brief's requirements genuinely can't be met with Recharts/TanStack Table (e.g., a map is required), name the gap explicitly and propose a single additional free/open-source library (e.g., Leaflet for maps) rather than adding it unannounced.

## Per-chart specification (define this for every chart before building it)

- Business question it answers
- Chart type and why it's the right type for that question
- Fields/encodings (x, y, color, size) and units
- Time grain (if time-series) and comparison period
- Color rule (which status/categorical tokens)
- Tooltip content
- Target/benchmark treatment, if applicable
- Interactions (hover, click-to-drill, legend toggle)
- Loading / empty / error / mobile behavior
- **Accessible alternative** — every chart ships with a linked, visually-hidden-until-toggled data table or a visible "view as table" action. Charts need an accessible name (`aria-label` or `aria-labelledby`) summarizing the finding, not just "chart."

## Rules (non-negotiable)

- No 3D charts, no decorative-only visualizations, no rainbow scales, no excessive pie charts (max one per screen, and only for ≤5 categories), no unjustified dual axes, no color-only status encoding, no truncated/misleading axes, no unlabeled units, no unexplained abbreviations in axis labels or legends.
- Every KPI card and chart must state its freshness ("as of [time]") and, where relevant, whether it's live, near-real-time, or batch data.
- AI-generated insights (forecasts, anomaly flags, natural-language summaries) must be visually labeled as AI-generated, state confidence/uncertainty, and link back to the source metrics and calculation period they're based on.

## States every chart/table component must handle

`loading`, `empty` (no data configured), `zero` (data exists but value is zero — different from empty), `no-results` (filtered to nothing), `stale` (data older than expected refresh interval), `partial` (some series/columns failed to load), `error`, `restricted` (user lacks permission), and `large-dataset` (needs pagination/virtualization, not a silent slowdown).
