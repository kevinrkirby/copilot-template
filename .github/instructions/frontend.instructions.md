---
applyTo: "apps/web/**"
---

# Frontend Guidelines

- Use Server Components where feasible; Client Components only for interactivity.
- Forms: `react-hook-form` + `zod` resolvers.
- Styling: Tailwind; prefer utility-first; avoid ad-hoc inline styles.
- Accessibility: label inputs, focus management, and test with `@testing-library`.
- Data fetching: `fetch` with typed responses; handle retry/backoff on 5xx.
- Testing: component tests for new UI; ensure ARIA roles in examples.
