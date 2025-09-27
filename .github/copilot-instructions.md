# GitHub Copilot Instructions

## Quick Reference

- **Specialized Instructions**: See `.github/instructions/` for domain-specific rules
- **TDD Workflow**: See `custom-instructions.md` for test-first development
- **Review Standards**: See `instructions/review-guidelines.instructions.md`

## General Guidelines

- Follow the repository's existing code style and conventions
- Write clear, maintainable, and well-documented code
- Use meaningful variable and function names
- Include appropriate error handling where necessary
- Follow security best practices and established patterns

## Project Overview

Monorepo with:

- apps/web (Next.js + TypeScript)
- apps/api (FastAPI + Python 3.11+)
- packages/ui (shared React components)
- infra (Terraform)

## Repository Context

- **Architecture**: Event-driven with shared components
- **Database**: [Specify your database setup]
- **Authentication**: [Specify auth strategy]
- **Deployment**: [Specify deployment targets]

## Build / Test / Validate

- Install: `pnpm i --frozen-lockfile`
- Web: `pnpm --filter @org/web dev|build|start`
- API: `uv run fastapi dev` (local); tests via `uv run pytest -q`
- Lint: `pnpm lint` (ESLint, Prettier); Python: `ruff check . && ruff format --check .`
- Typecheck: `pnpm typecheck`
- E2E: `pnpm --filter @org/web test:e2e` (Playwright)

## Code Quality Standards

- Write modular, reusable code components
- Follow the DRY (Don't Repeat Yourself) principle
- Ensure code is readable and follows established patterns
- Add comments for complex logic or algorithms
- TypeScript: strict mode; prefer `zod` for runtime validation; never use `any`
- React: functional components, hooks, server components where possible
- Python: type hints (mypy), dataclasses/pydantic for schemas
- Errors: return typed Results (TS) or raise custom exceptions (Python)
- Commits: Conventional Commits; scope = package name
- Branching: trunk-based; small PRs (<300 LOC preferred)

## Security & Privacy

- Secrets only via env; provide `.env.example` updates.
- Add `OWASP`-style input validation; treat file/URL inputs as untrusted.
- For third-party code, link to license and docs.

## Performance Budgets

- Web: LCP < 2.5s; bundle < 220KB gzipped per route. Suggest code-splitting if exceeded.
- API: P95 latency targets per endpoint; propose caching (ETag/Redis) when relevant.

## Observability

- Web: add `next/headers` and logging hooks where needed.
- API: ensure structured logs and basic metrics stubs.

## Error Handling Patterns

- **TypeScript**: Use Result<T, E> types; avoid throwing in business logic
- **React**: Error boundaries for component failures; graceful degradation
- **Python**: Custom exception hierarchies; structured error responses
- **API**: Consistent error response format with proper HTTP status codes

## Documentation Standards

- Update documentation when making changes
- Include docstrings for functions and classes
- Keep README files up to date
- Document any configuration or setup requirements
- Docs/README snippets updated for any user-visible changes

## Testing Requirements

- Write tests for new code paths and functionality
- Ensure existing tests continue to pass
- Follow test naming conventions and describe what is being tested
- Test edge cases and error conditions
- Types checked & lint clean before submission

## Development Workflow

- **Before coding**: Check existing patterns in codebase first
- **Feature development**: Start with tests (see custom-instructions.md)
- **Code review**: Follow review-guidelines.instructions.md
- **Deployment**: Ensure all checks pass before merge

## AI Assistant Guidelines

- **Code generation**: Always consider existing patterns and conventions
- **Refactoring**: Maintain backward compatibility unless explicitly requested
- **Dependencies**: Prefer existing stack; justify new dependencies
- **Security**: Never hardcode secrets; validate all inputs

## Pull Request Checklist (auto-apply to generated changes)

- [ ] Tests for new code paths
- [ ] Types checked & lint clean
- [ ] Docs/README snippets updated
- [ ] Changelog entry if user-visible

