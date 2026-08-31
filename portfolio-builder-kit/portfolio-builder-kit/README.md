# Award-Winning Portfolio — Vibe Coding Kit

This folder turns the original 12-section meta-prompt into a **buildable sequence**. Instead of asking an AI to write one giant prompt, your students run one prompt per phase, in order, inside a real coding agent (Claude Code, Cursor, Windsurf, etc.), and watch an actual React 19 codebase grow.

## How students use this

1. **Unzip/copy this whole folder** as their project root (or point Claude Code at it).
2. Open `docs/BRIEF-TEMPLATE.md` and fill in the placeholders (profession, audience, services, etc.) — save it as `docs/brief.md`. This is the only manual writing step.
3. Open a terminal in the project folder and start Claude Code (`claude`) or their agent of choice.
4. Open `prompts/00-fill-brief-instructions.md` first — it's a checklist, not a prompt.
5. From `prompts/01-project-scaffold.md` onward, **copy the prompt text and paste it into the agent, one file at a time, in numeric order.** Let each phase finish and get reviewed before pasting the next.
6. `CLAUDE.md` is read automatically by Claude Code at the start of every session — it holds the standing rules so students don't have to repeat them in every prompt.
7. The `skills/` folder holds reference standards (design tokens, motion rules, component architecture, case-study structure) that every prompt tells the agent to consult before writing code.

## Why sequencing matters

Each prompt in `prompts/` builds on files the previous prompt created. Skipping ahead means the agent is missing context (design tokens, brief content, component primitives) and will improvise inconsistently. The order is:

| # | Phase | Produces |
|---|-------|----------|
| 00 | Brief checklist | `docs/brief.md` |
| 01 | Scaffold | Vite + React 19 + TS + Tailwind project, folder structure |
| 02 | Positioning & IA | `docs/strategy.md`, `docs/sitemap.md` |
| 03 | Design system | Design tokens + base component library |
| 04 | Homepage | Hero → final CTA, full homepage |
| 05 | Portfolio showcase | Filterable project gallery |
| 06 | Case study template | Dynamic, scroll-driven case study page |
| 07 | Secondary pages | About, Services, Testimonials, Blog, Contact |
| 08 | Motion system | Global scroll/hover/transition layer |
| 09 | Conversion system | CTAs, forms, lead capture, qualification |
| 10 | Technical polish | SEO, a11y, Core Web Vitals |
| 11 | Final QA & deploy | Lighthouse pass, deploy config |

Total: a full multi-page, animated, conversion-oriented portfolio site, built incrementally instead of dumped in one shot.
