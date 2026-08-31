# Prompt 11 — Final QA & Deployment

Paste everything below the line into your coding agent.

---

This is the final phase. Read `CLAUDE.md`'s quality bar one more time.

1. Run a full build and fix any build/type errors.
2. Run through the site end-to-end as a visitor would: Home → Work → a Case Study → back to Work with filters retained if applicable → Services → About → Contact form submission. Fix any broken link, dead route, or console error found.
3. Remove the `/dev/style-guide` route from the production build (or gate it behind a dev-only check) — it was for internal review in Phase 03, not for visitors.
4. Run (or simulate, describing expected results if Lighthouse isn't directly runnable in this environment) a Lighthouse pass on Home, Work, and a Case Study page; report Performance, Accessibility, SEO, and Best Practices scores and fix anything below the 95+ target set in `CLAUDE.md`.
5. Set up deployment configuration for the hosting target specified in `docs/brief.md` (or a sensible static-hosting default — e.g., Vercel/Netlify config — if the brief didn't specify one).
6. Produce a final `docs/launch-checklist.md` listing: any placeholder content still in place (images, blog posts, unverified metrics) that must be replaced with real assets before going live, and any integration (form backend, analytics, CRM) still using a mock and needing a real key/endpoint.

End with a summary of final scores/status and the launch checklist location.

---

**Final check before calling it done:**
- Walk the whole site yourself, on a phone and a laptop, as a real visitor would — Home → Work → a case study → Contact.
- Open `docs/launch-checklist.md` and treat it as a real to-do list, not a formality — every placeholder/mock item on it needs a real owner before this goes live.
- If anything feels off after all 11 phases, it's worth a targeted follow-up prompt rather than starting over — tell the agent exactly what's wrong and which page.
