# Prompt 03 — Design System Implementation

Paste everything below the line into your coding agent.

---

Read `skills/design-system/SKILL.md` and `skills/react19-component-architecture/SKILL.md` in full before starting. Also read `docs/strategy.md` for brand personality/voice to inform visual direction.

1. Fill in the design token structure created in Phase 01 (`tailwind.config.js` theme + `src/styles/tokens.css`) with real values: color palette (primary, accent, neutral scale, semantic colors), a type scale using a display + body typeface pairing appropriate to the brand personality from `docs/strategy.md`, spacing scale, radius scale, shadow/elevation scale, and grid/breakpoint definitions. Justify the typeface and color choices in one paragraph against the brand personality/voice.
2. Build the core `src/components/ui/` primitive library to the contract defined in `skills/react19-component-architecture/SKILL.md`: Button, Card, Badge/Tag, Tabs, Accordion, Dialog/Modal, Tooltip, Input/Textarea/Field (for later forms), FilterPill, Avatar, and a basic Skeleton loader. Each with typed variant props, full keyboard support, and correct ARIA.
3. Build a small style-guide route at `/dev/style-guide` (not linked in navigation) rendering every primitive and its variants, so the design system can be visually reviewed before it's used across real pages.

Do not build page layouts yet. End with a summary of the palette/type choices and a note on any primitive you deferred (and why).

---

**Before moving to Prompt 04, check:**
- Open `/dev/style-guide` — does the palette/type actually look like the brand personality from `docs/strategy.md`, or does it default to generic Tailwind blue/gray?
- Tab through the primitives with your keyboard only — focus states should be clearly visible.
- If anything here feels off, fix it now — every later phase builds on these tokens and components.
