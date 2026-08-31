# Prompt 06 — Case Study Template

Paste everything below the line into your coding agent.

---

Read `skills/case-study-builder/SKILL.md` in full, plus `src/content/brief.js` for the actual project/case-study/testimonial data.

Build the dynamic case study page (`src/pages/CaseStudy.jsx`, route `/work/:slug`) implementing the narrative structure from `skills/case-study-builder/SKILL.md`:

1. Render each narrative beat (Overview, Challenge, Research where applicable, Strategy, Process, Execution, Results, Client Feedback, Next Project) as its own section component in `src/components/case-study/`.
2. Pull section content dynamically from the project's data in `src/content/brief.js` — omit any beat the data doesn't support for that project, per the skill's content rules.
3. Build a before/after comparison component (draggable slider, keyboard-operable with arrow keys, accessible label) and use it wherever a project's data indicates a visual transformation; otherwise omit it for that project.
4. Add a "next project" navigation at the end linking to another item from the portfolio list.
5. Layout should read as chapters with clear visual separation between beats, ready for the scroll-reveal treatment in Phase 08 (structure sections so each can be independently targeted by a reveal wrapper later).

Keep this fully responsive and keyboard-navigable now. End with a summary of which projects got the full beat set vs. a reduced set, and why.

---

**Before moving to Prompt 07, check:**
- Open a case study for a project with thin data — does it gracefully skip missing beats, or does it show empty/awkward sections?
- Operate the before/after slider with keyboard arrows only, not just a mouse drag.
- The "next project" link at the end actually goes somewhere real.
