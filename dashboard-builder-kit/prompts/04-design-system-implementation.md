# Prompt 04 — Design System Implementation

Paste everything below the line into your coding agent.

---

Read `skills/design-system/SKILL.md` and `skills/react19-component-architecture/SKILL.md` in full. Also read `docs/strategy.md` for brand attributes and `docs/brief.md` for preferred/avoided colors and theme requirements.

1. Fill in the token structure from Phase 01 (`tailwind.config.js` theme + `src/styles/tokens.css`) with real values: brand/neutral/status/chart-categorical/chart-sequential color tokens (both light and dark sets), a type scale including a tabular-figure numeric style, spacing scale, density variants (comfortable/compact), radius, elevation, and motion tokens. Justify the palette and type choices in one paragraph against the brand attributes.
2. Build the core `src/components/ui/` primitive library per the component contract in `skills/react19-component-architecture/SKILL.md`: Button, Input, Select, DatePicker (range-capable, for the global date filter), Checkbox, Switch, Tabs, Chip, Badge, Tooltip, Popover, Modal, Drawer, Toast, Accordion, Skeleton.
3. Build a `/dev/style-guide` route (not in navigation) rendering every primitive, every variant, and both light/dark themes side by side for review.

Do not build dashboard-specific components (KPI cards, charts, tables) yet — that's Phase 05. End with a summary of palette/type choices and any primitive deferred.

---

**Before moving to Prompt 05, check:**
- Open `/dev/style-guide` and toggle light/dark — both should look intentional, not like one is an inverted afterthought.
- Check the status colors (critical/warning/success) are distinguishable without relying on color alone (icons/labels present).
- Tab through the primitives with your keyboard — focus states should be clearly visible in both themes.
