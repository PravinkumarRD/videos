# Prompt 11 — Security, Privacy & Responsible AI

Paste everything below the line into your coding agent.

---

Read `docs/brief.md`'s compliance requirements field and `CLAUDE.md`'s mock-data rules. This phase hardens the whole app, not just one page.

1. **Access control** — verify least-privilege, role-based visibility is actually enforced (not just visually hidden) at the route and data-service level: a mock non-admin user must be unable to fetch admin-only data even by calling the service function directly, not just by the UI hiding a link.
2. **Sessions & secrets** — confirm no credentials, tokens, or secrets exist in client-side code; add an `.env.example` template with variable names only, no real values; confirm the mock/live API config flag from Phase 03 doesn't leak any real endpoint or key.
3. **Data safety** — re-confirm every mock dataset is synthetic and clearly commented as such; confirm exports (CSV/PDF from Phase 08) are formula-injection-safe; confirm any "restricted" state (Phase 05/10) actually masks or omits the underlying value rather than sending it to the client and hiding it with CSS.
4. **Responsible AI** — audit every AI-labeled insight (from Phase 06 onward): confirm it's visually labeled as AI-generated, states uncertainty/confidence, shows the source metric and calculation period, allows inspecting the supporting data, and that no AI insight triggers an autonomous high-impact action (e.g., auto-resolving a critical alert, per Phase 08) without human review. Add a brief note in `docs/responsible-ai.md` documenting these safeguards.
5. If `docs/brief.md` named specific compliance requirements (e.g., SOC 2, HIPAA, GDPR), write `docs/compliance-notes.md` stating which app behaviors support that requirement and which still need real legal/security review before launch — never claim compliance is achieved by this codebase alone.

End with a summary of what was verified/fixed and what still requires human review before this could handle real data.

---

**Before moving to Prompt 12, check:**
- Open your browser's network tab as a restricted-role mock user and confirm restricted data genuinely isn't sent to the client — not just hidden with CSS.
- Search the codebase for anything that looks like a real API key or secret — there should be none, only `.env.example` placeholders.
- Read `docs/responsible-ai.md` — would you be comfortable explaining these AI safeguards to a real client or stakeholder?
