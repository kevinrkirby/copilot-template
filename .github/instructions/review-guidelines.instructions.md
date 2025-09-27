---
applyTo: "**/*"
---

# Code Review Lens

- Blockers: security issues, undefined behavior, data races, missing input validation.
- Warnings: performance regressions, untyped boundaries, leaky abstractions.
- Request: suggest concrete diff hunks, not prose; link to docs/specs when recommending changes.
- Style: prefer idiomatic patterns; consistent naming, formatting, and structure.
- Tests: ensure coverage for new code paths; validate edge cases and failure modes.
- Docs: update README snippets, changelogs, and any relevant docs.
- Commits: clear, descriptive messages; follow Conventional Commits.
- PRs: small, focused changes; avoid mixing refactors with feature work.
- Communication: ask clarifying questions; explain reasoning behind suggestions.
- Empathy: respect original author’s intent; consider their perspective and constraints.
- Automation: leverage linters, type checkers, and CI tools to catch common issues.
- Security: ensure no secrets are hardcoded; validate all external inputs.
- Performance: watch for O(n^2) patterns; suggest caching or memoization where applicable.
- Accessibility: ensure UI changes meet a11y standards; use semantic HTML and ARIA roles.
- Privacy: handle PII carefully; follow data minimization principles.
- Compliance: adhere to relevant legal and regulatory requirements (e.g., GDPR, CCPA).
- Observability: ensure sufficient logging and metrics for new features; suggest tracing where relevant.
- UX: consider user experience; ensure intuitive flows and clear error messages.
- Maintainability: favor clear, simple solutions; avoid premature optimization or over-engineering.
- Scalability: consider how changes will perform under load; suggest improvements for bottlenecks.
