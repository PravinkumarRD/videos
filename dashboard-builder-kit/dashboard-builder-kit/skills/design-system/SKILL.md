# Skill: Design System Foundation (Dashboard Context)

Consult before touching colors, type, spacing, or layout. This is an enterprise product — benchmark against Linear, Stripe Dashboard, Notion, and modern BI tools, not generic admin templates.

## Tokens (define once, in `tailwind.config.js` theme extension + `src/styles/tokens.css`)

Use machine-friendly, layered names, e.g.:

```
color.brand.primary
color.surface.default / color.surface.raised
color.text.primary / color.text.secondary / color.text.disabled
color.status.critical / color.status.warning / color.status.success / color.status.info
color.chart.categorical-1 ... categorical-8
space.100, space.200, ...
radius.small / radius.medium / radius.large
elevation.raised / elevation.overlay
```

- **Color** — brand primary + neutral surface/text scale + semantic status colors (critical/warning/success/info, each meeting AA contrast on their surface) + a categorical chart palette (6–8 colorblind-safe hues) + a sequential palette for heatmaps/intensity. **Both light and dark token sets required.**
- **Typography** — one type scale used everywhere: display/heading sizes for page titles, a body size for content, a smaller "data" size for table cells and axis labels, and a numeric/tabular-figure variant for KPI values and table numbers (so digits align).
- **Spacing** — 4px or 8px base scale, used consistently for card padding, gaps, and section rhythm.
- **Density** — define at least "comfortable" and "compact" density variants (padding/row-height tokens) since dashboards often need to show more data in less space.
- **Radius/elevation** — a small deliberate set; use elevation to distinguish overlays (modals, popovers) from static surfaces (cards), not for decoration.
- **Motion tokens** — duration/easing constants shared with `skills/data-visualization/SKILL.md` for consistent chart transitions.

## Layout philosophy

- Information density over whitespace-heavy marketing aesthetics — but never so dense that touch targets or text fall below accessible minimums.
- Consistent page anatomy: header → global/local filters → KPI row → chart/table grid → detail area. Reuse this skeleton across every dashboard page.
- Card-based composition: KPI cards and chart cards share the same container component so spacing/radius/elevation stay consistent site-wide.

## Component system rules

- Every visual pattern used more than once becomes a token or shared component.
- Status colors are always paired with an icon or text label, never color alone.
- Chart colors come only from the categorical/sequential chart tokens — never ad hoc hex values per chart.

## Anti-patterns to avoid

- Rainbow/unlimited chart color palettes.
- More than 2 typefaces (prefer 1 with multiple weights).
- Light-mode-only design that gets awkwardly inverted for dark mode later — build both token sets from the start.
