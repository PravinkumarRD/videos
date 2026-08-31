# Prompt 07 — Secondary Pages

Paste everything below the line into your coding agent.

---

Read `docs/sitemap.md`, `src/content/brief.js`, and reuse existing `ui/` primitives and homepage/case-study section components wherever the pattern fits — don't rebuild things Phase 04–06 already built.

Build out the remaining routes to match `docs/sitemap.md`'s content hierarchy for each:

1. **About** (`src/pages/About.jsx`) — full founder story from the brief, experience/credentials, personality-driven presentation (not a résumé dump), with a CTA toward Work or Contact.
2. **Services** (`src/pages/Services.jsx`) — full service list with descriptions, packages/tiers if present in the brief, specializations, each service linking conceptually to relevant portfolio work, ending in a CTA.
3. **Testimonials** (`src/pages/Testimonials.jsx`) — full testimonial collection from the brief, more complete than the homepage excerpt.
4. **Blog/Insights** (`src/pages/Blog.jsx` + a post template) — if the brief includes content topics, scaffold a simple list + post template with 1–2 placeholder posts clearly marked as placeholders; if the brief has no blog content, build the structure but note it needs real content before launch.
5. **Contact** (`src/pages/Contact.jsx`) — this is the primary conversion page; build the actual form now using a React 19 Action + `useActionState` (per `skills/react19-component-architecture/SKILL.md`), including the preferred contact method and lead magnet (if any) from the brief. Full form validation and accessible error states. This form does not need a real backend yet — wire it to a mock submit handler and note where a real integration (email service, CRM) would plug in.

Keep every page mobile-first and consistent with the established design system. End with a summary of any page where brief content was thin and a placeholder was used.

---

**Before moving to Prompt 08, check:**
- Submit the Contact form with a missing/invalid field — does it show a clear, accessible error rather than failing silently?
- No page feels noticeably thinner or less finished than the others — if one does, that's the brief gap to flag to your client/instructor.
- Every nav link in the header/footer actually points to a working page.
