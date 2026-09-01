# Prompt 09 — Auth, Onboarding & Settings

Paste everything below the line into your coding agent.

---

Read `docs/brief.md`'s authentication requirements, user roles, and integrations fields, and `docs/personas.md`.

1. Build the sign-in page (`src/pages/SignIn.jsx`, route `/sign-in`) with an Action + `useActionState` form (email/password or the method implied by the brief), accessible validation and error states, and a password-recovery entry point. No real authentication backend — wire to a mock auth service in `src/services/mock/auth.js` with the same interface a real one would have, and note where a real provider would plug in.
2. Build an onboarding flow (`src/pages/Onboarding.jsx`, route `/onboarding`, likely as a multi-step wizard) covering: organization setup, role/goal selection, data-source choice (mock-only for now), KPI selection tied to `docs/kpi-catalogue.md`, alert preference defaults, team invitation, and a guided "first insight" step that lands the user on a pre-filtered Overview dashboard. Use progressive disclosure with a visible step indicator and a dismissible checklist pattern, not a single giant form.
3. Build a Settings area (`src/pages/app/Settings.jsx`, route `/app/settings`) with tabs/sections for: profile, organization, user & role management (list users, assign roles from the brief's `user_roles`), and integrations (list, mock connect/disconnect state). Wire the route guard stub from Phase 01 into real role-based visibility: at least one setting or nav item should be visibly restricted for a non-admin mock user.

End with a summary of which roles were implemented and how role-based visibility was demonstrated.

---

**Before moving to Prompt 10, check:**
- Walk through onboarding as a first-time user — does each step make sense on its own, and does "first insight" actually land on real data?
- Log in as (or simulate) a non-admin role — confirm the restricted setting/nav item is genuinely hidden or disabled, not just visually faded while still clickable.
- Try to submit the sign-in form with an invalid input — you should get a clear, accessible error, not a silent failure.
