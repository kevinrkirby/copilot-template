# copilot-template

# Copilot Coding Agent Instructions

## Setup

- Node 20, Python 3.11, pnpm, uv. 
- Install: `pnpm i --frozen-lockfile` (repo root), then `uv sync` in `apps/api/`.

## Task Execution Policy

- Prefer small, incremental PRs with clear titles and Conventional Commit messages.
- Never write secrets; use env vars and update `.env.example` if needed.
- Before opening a PR:
  1) `pnpm lint && pnpm typecheck`
  2) `pnpm -w test --reporter=dot`
  3) `uv run pytest -q`
  4) Run `pnpm --filter @org/web build` and include bundle stats in PR body.

## Validation

- Add/adjust unit tests for all new code paths.
- Update README snippets and any touched package’s changelog.
- If touching HTTP handlers, include a short “risk assessment” section in the PR body.

## Out of Scope

- License changes, dependency major upgrades, infra drift fixes without an issue reference.
