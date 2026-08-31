# Prompt 01 — Project Scaffold

Paste everything below the line into your coding agent.

---

Read `CLAUDE.md`, `docs/brief.md`, and every file in `skills/` before starting.

Scaffold a new React 19 + JavaScript + Vite project in this folder:

1. Initialize Vite with the react template (plain JavaScript, not the -ts variant), upgrade React and react-dom to 19, and add: React Router (data router), Tailwind CSS, and Motion (the animation library, successor to Framer Motion).
2. Set up the folder structure specified in `CLAUDE.md`: `src/components/ui/`, `src/components/`, `src/pages/`, `src/content/`, `src/styles/`. All source files are `.jsx`/`.js`, not `.tsx`/`.ts`.
3. Configure `tailwind.config.js` with an empty-but-structured theme extension (color, spacing, typography, radius, shadow keys ready to be filled in Phase 03) — don't invent final values yet, just the structure.
4. Set up React Router with placeholder routes for: Home, About, Services, Work (portfolio index), a dynamic Case Study route, Testimonials, Blog/Insights, Contact. Each should render a minimal placeholder page for now.
5. Add ESLint + Prettier with sensible defaults for a React 19 + JavaScript project, plus the `eslint-plugin-react-hooks` and `eslint-plugin-jsx-a11y` rules. Add `prop-types` as a dependency for component prop documentation (per `skills/react19-component-architecture/SKILL.md`).
6. Create a `src/content/brief.js` that imports/exposes the structured content from `docs/brief.md` as plain JS objects/arrays (profession, audience, services, projects, testimonials, CTAs, etc.), with a JSDoc `@typedef` block documenting the shape, so later phases can pull real content instead of re-parsing markdown.
7. Verify the project builds and the dev server runs cleanly.

Do not design or style anything yet — this phase is scaffolding only. End with a short summary of what was created and any brief fields that were missing or ambiguous.

---

**Before moving to Prompt 02, check:**
- `npm run dev` starts cleanly with no errors, and every placeholder route loads.
- The folder structure matches `CLAUDE.md` (`components/ui/`, `pages/`, `content/`, `styles/`).
- `src/content/brief.js` actually reflects what you wrote in `docs/brief.md` — spot-check a few fields.
