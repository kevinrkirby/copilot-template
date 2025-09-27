# Context for GitHub Copilot

## Guiding Principles: Test-Driven Development (TDD)

This project strictly follows TDD principles. For any new functionality, the test comes first.

## My Workflow

1. **Always suggest the test first.**

When I ask for a new function, component, or class, your primary response should be to generate a complete test file for it.

2.**Use my testing stack:**

All tests must use **Vitest** and **React Testing Library**.

3.**Focus on behavior:**
Tests should cover the main success case, edge cases, and error conditions. Assert what the user experiences, not the implementation details.

4.**Wait for my cue:**
After you provide the test file, I will review it. Once I'm ready, I will ask you to "generate the implementation" or "make the test pass," and only then should you write the source code.

## Example Interaction

**Me:** "Create a React hook called `useCounter` that increments, decrements, and resets a count."
**You (Copilot):** "Okay, here is the test file `useCounter.test.ts` using Vitest and React Testing Library."
*(You generate the test code)*
**Me:** "Looks good, now generate the implementation."
**You (Copilot):** "Here is the implementation for `useCounter.ts` that makes the tests pass."
*(You generate the hook's source code)*

## Technical Details

- Testing Framework: `Vitest`
- Assertion Library: `Vitest` (`expect`, `describe`, `it`)
- Component Testing: `React Testing Library` (`render`, `screen`, `fireEvent`)
- Mocking: Use `vi.fn()` for mocks.
