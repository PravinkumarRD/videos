# Prompt 10 — Technical Requirements: SEO, Accessibility, Performance

Paste everything below the line into your coding agent.

---

Read the quality bar in `CLAUDE.md`. This phase is a technical hardening pass across the entire site built so far — no new visual content.

1. **SEO** — add per-page `<title>` and `<meta name="description">` (via React 19's JSX head hoisting) tailored to each page's real content; add Open Graph and Twitter card tags; add structured data (JSON-LD) for the person/organization on Home and for each case study as a CreativeWork where applicable; generate a sitemap.xml and robots.txt matching the routes in `docs/sitemap.md`.
2. **Accessibility** — run through every page for: semantic landmark structure (header/nav/main/footer), heading hierarchy with no skipped levels, all interactive elements keyboard-reachable with visible focus states, all images with meaningful alt text (or empty alt for decorative ones), color contrast meeting AA against the actual token values from Phase 03, and forms with properly associated labels and error announcements. Fix anything found.
3. **Performance** — audit for: unoptimized images (add responsive/lazy-loaded image handling), unnecessary re-renders in the portfolio filter and any list-heavy component, code-splitting per route, and font-loading strategy (avoid layout shift from web fonts).
4. **Responsive QA** — verify every page built in Phases 04–07 at mobile, tablet, and desktop breakpoints; fix any breakage.

End with a checklist of what was fixed and any remaining known gap that needs a real content asset (e.g., actual optimized images) rather than a code fix.

---

**Before moving to Prompt 11, check:**
- Tab through an entire page using only the keyboard, start to finish — you should never lose track of where focus is.
- Check that page titles in the browser tab actually change per page and describe that page.
- Any remaining gap the agent flagged (e.g., needs real images) is written down so it doesn't get forgotten before launch.
