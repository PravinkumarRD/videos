# Prompt 08 — Motion & Interaction System

Paste everything below the line into your coding agent.

---

Read `skills/motion-system/SKILL.md` in full. This phase adds motion across the whole site built in Phases 03–07 — it does not add new pages or content.

1. Build the shared motion utilities described in the skill: a `<Reveal>` scroll-entrance wrapper, shared easing/duration constants, a hover-lift/scale utility, and a page-transition wrapper for route changes. All must respect `prefers-reduced-motion` by design, not as an afterthought bolted on later.
2. Apply `<Reveal>` to homepage sections (Phase 04), portfolio grid items (Phase 05), and each case study narrative beat (Phase 06) so they animate in on scroll, in the order defined by `skills/case-study-builder/SKILL.md` for case studies.
3. Apply the hover utility consistently to interactive cards (project cards, service cards, testimonial cards) — one consistent feel across the whole site, not per-component variation.
4. Wire the page-transition wrapper into the router so navigating between pages feels considered rather than an instant hard cut.
5. Add appropriate loading states (using the Skeleton primitive from Phase 03) anywhere content could visibly pop in (project images, blog posts).
6. Verify nothing here blocks interaction — a user must be able to click through a CTA immediately, not wait out an animation.

End with a summary of where motion was applied and confirm reduced-motion behavior was tested (describe how).

---

**Before moving to Prompt 09, check:**
- Turn on "reduce motion" in your OS settings and reload the site — animations should stop or simplify, not break the layout.
- Click a CTA immediately as a section animates in — it should respond instantly, never wait for the animation to finish.
- Navigate between pages a few times — the transition should feel smooth, not jarring or slow.
