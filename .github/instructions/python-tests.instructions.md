---
applyTo: "apps/api/tests/**/*.py"
---

# Python Test Rules (Pytest)

- Structure: Arrange–Act–Assert; one behavior per test.
- Use fixtures for setup; parametrize common cases.
- Mock external IO (DB, HTTP, filesystem).
- Cover failures and edge cases, not just happy paths.
- Prefer `pytest.raises` with explicit message checks.
- Use `pytest-mock` for mocking; avoid `unittest.mock` directly.
- Test async code with `pytest-asyncio`.
- Run tests with `uv run pytest -v --cov=.`; aim for 90%+ coverage.
