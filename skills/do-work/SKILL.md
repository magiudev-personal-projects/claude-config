---
name: do-work
description: "Execute a unit of work end-to-end: plan, implement, validate with build and tests, then commit. Use when user wants to do work, build a feature, fix a bug, or implement a phase from a plan."
---

# Do Work

Execute a complete unit of work: plan it, build it, validate it, commit it.

## Workflow

### 1. Understand the task

Read any referenced plan or PRD. Explore the codebase to understand the relevant files, patterns, and conventions. If the task is ambiguous, ask the user to clarify scope before proceeding.

### 2. Plan the implementation (optional)

If the task has not already been planned, create a plan for it.

### 3. Check whether the project has automated tests

Look for a test framework, test files, or a test command (e.g. a `test` script, a `tests/`/`spec/` folder, a test runner config). If a project-specific skill or CLAUDE.md already states this, use that instead of re-checking.

- **Tests exist**: follow the TDD flow below.
- **No tests exist**: skip to step 4 and implement directly, without writing tests.

### 4. Implement

If the project has tests, use red/green/refactor, one test at a time in a tracer-bullet style:

1. Write a single failing test for the smallest vertical slice of behavior
2. Run the test — confirm it fails (red)
3. Write the minimum code to make it pass (green)
4. Repeat from step 1 for the next slice of behavior
5. Refactor if needed while keeping tests green

Each test should target one thin vertical slice through the system. Do not write all tests upfront — write one, make it pass, then move to the next.

If the project has no tests, implement the change directly in thin vertical slices, without adding tests.

### 5. Validate

Run this project's build command. Also run the test command, but only if the project has tests. Fix any issues, repeat until clean.

If a project-specific skill or CLAUDE.md overrides how/where to run these (e.g. a different environment must run them), follow that instead.

### 6. Commit

Once build and tests pass, commit the work.
