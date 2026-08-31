# Prompt 01 — Project Scaffold

Paste everything below the line into your coding agent.

---

Read `CLAUDE.md`, `docs/brief.md`, and every file in `skills/` before starting.

Scaffold a new React 19 + JavaScript + Vite project in this folder:

1. Initialize Vite with the plain `react` template (JavaScript, not `-ts`), upgrade React and react-dom to 19, and add: React Router (data router), Tailwind CSS, Motion, Recharts, TanStack Table, and `prop-types`.
2. Set up the folder structure from `CLAUDE.md`: `src/components/ui/`, `src/components/`, `src/pages/`, `src/services/mock/`, `src/services/api/`, `src/content/`, `src/styles/`. All source files are `.jsx`/`.js`.
3. Configure `tailwind.config.js` with an empty-but-structured theme extension (color, spacing, typography, radius, elevation, density keys ready to be filled in Phase 04) — structure only, no final values yet.
4. Set up React Router with placeholder routes for: marketing landing (`/`), sign-in (`/sign-in`), onboarding (`/onboarding`), executive dashboard (`/app/overview`), operational dashboard (`/app/operations`), data explorer (`/app/explore`), reports (`/app/reports`), alerts (`/app/alerts`), settings (`/app/settings`), and a role-based route guard wrapper (even if it's a stub for now — real RBAC logic comes in Phase 09/11).
5. Create `src/services/mock/index.js` as the single entry point for all mock data access, and `src/services/api/index.js` as a stub with the same function signatures so the two are visibly swappable later. Don't populate real data yet — just the interface shape as a placeholder, since the real schema comes in Phase 03.
6. Add ESLint + Prettier with `eslint-plugin-react-hooks` and `eslint-plugin-jsx-a11y`.
7. Verify the project builds and the dev server runs cleanly.

Do not design or style anything yet, and do not build real mock data yet — this phase is scaffolding only. End with a short summary of what was created and any brief fields that were missing or ambiguous.

---

**Before moving to Prompt 02, check:**
- `npm run dev` starts cleanly and every placeholder route (including `/app/*` routes) loads without errors.
- The folder structure matches `CLAUDE.md`, including separate `src/services/mock/` and `src/services/api/` folders.
- Nothing in the scaffold references real data yet — that's intentional, confirm it stayed that way.
