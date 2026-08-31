# Skill: React 19 Enterprise Component Architecture (Dashboard Context)

Consult before building or extending any component. The bar: could this compete with a paid dashboard component library (e.g., a commercial admin template or BI tool)?

## Structure

- `src/components/ui/` — headless-first primitives: Button, Input, Select, DatePicker, Checkbox, Switch, Tabs, Chip, Badge, Tooltip, Popover, Modal, Drawer, Toast, Accordion, Skeleton. Own their own accessibility (focus, ARIA, keyboard nav).
- `src/components/` — composed, dashboard-specific components built from `ui/`: `KPICard`, `ChartCard`, `DataTable`, `FilterBar`, `DrillDownBreadcrumb`, `AlertBanner`, `SavedViewMenu`, `ExportMenu`, `FreshnessIndicator`.
- `src/pages/` — route-level compositions only.
- `src/services/` — data access. Components never fetch directly; they call a service function that returns the same shape whether backed by mock or live API.

## React 19 patterns to actually use

- **No `forwardRef` boilerplate** — `ref` is a normal prop now.
- **`use()`** for reading async dashboard data or context (e.g., current org/role context) conditionally.
- **Actions + `useActionState`** for every form: sign-in, filter panels submitted as a batch, onboarding steps, settings forms. Model as an Action with pending/error state built in, not manual `useState` juggling.
- **`useOptimistic`** for instant-feeling toggles: favoriting a metric, saving a view, dismissing an alert — update the UI immediately, reconcile when the request resolves.
- **Document metadata in JSX** (`<title>`, `<meta>`) per page for the marketing/auth pages.

## Component contract (every component in `ui/` and dashboard-specific components)

1. Accepts and merges `className`.
2. Fully keyboard operable; visible focus ring from the design token.
3. Correct ARIA role/state — especially for `DataTable` (grid semantics, sort/filter announcements), `ChartCard` (accessible name + a linked tabular alternative), and `FilterBar` (form semantics, live region for result counts).
4. Respects `prefers-reduced-motion`.
5. Documented prop contract via `prop-types` and/or a JSDoc `@typedef` — no undocumented "magic" props.
6. Handles all data states explicitly as a prop or derived state: `loading`, `empty`, `zero`, `error`, `stale`, `restricted` — never just the populated state.
7. Variants (size, density, tone/status) expressed as a small documented set validated with `prop-types`' `oneOf`.

## Anti-patterns to avoid

- A chart or table component that assumes data is always present and non-empty.
- Fetching inside a `useEffect` in a page component instead of going through `src/services/`.
- Duplicating KPI-card or chart-card markup per dashboard instead of parameterizing the shared component.
- Divs with `onClick` standing in for buttons/links, especially in table rows and chart legends.
- Color as the only signal for status (critical/warning/normal) anywhere.
