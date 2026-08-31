# Prompt 04 — Homepage Build

Paste everything below the line into your coding agent.

---

Read `docs/strategy.md`, `docs/sitemap.md`, `src/content/brief.js`, and `skills/design-system/SKILL.md`. Use the `ui/` primitives from Phase 03 — do not create parallel one-off styled elements.

Build the full Home page (`src/pages/Home.jsx`) using real content from `docs/brief.md`/`src/content/brief.js`, with these sections in order:

1. **Hero** — the sharpened value proposition from `docs/strategy.md` as the headline, supporting subhead, primary CTA + secondary CTA (from the brief), a trust indicator (years of experience, notable client, or award), and a strong visual/layout treatment that avoids the centered-gradient-blob SaaS cliché.
2. **Featured Work** — 3–4 standout projects from the brief as cards linking toward the (not-yet-built) case study route; use placeholder imagery treated consistently per the design system.
3. **Services Overview** — services from the brief, scannable, each linking conceptually toward the Services page.
4. **Client Results** — 2–3 concrete outcomes/metrics from the brief, presented as a compact proof section.
5. **Social Proof** — client logos/recognition if present in the brief; omit gracefully if not.
6. **Testimonials** — 1–2 featured testimonials from the brief.
7. **Brand Story** — a condensed version of the founder story from the brief.
8. **Trust Indicators** — certifications/awards from the brief.
9. **Final Conversion Section** — a clear closing CTA restating the value proposition.

Each section should be its own component in `src/components/home/`. No motion yet beyond what the primitives already include — that's Phase 08. Make it fully responsive now, mobile-first. End with a summary of any brief content that was missing and what placeholder was used instead.

---

**Before moving to Prompt 05, check:**
- Scroll the whole homepage on a real phone or narrow browser window — nothing should overflow or feel cramped.
- Every section uses real content from your brief, not generic lorem-ipsum-style filler.
- The primary and secondary CTAs are visually distinct from each other and easy to find.
