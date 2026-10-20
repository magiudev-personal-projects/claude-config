---
name: gen-manual-qa
description: "Write a step-by-step manual QA plan (markdown) for a feature — API, frontend, or both — with exact inputs and a progress checklist. Use when the user wants a QA plan file they will follow themselves."
---

# Generate Manual QA Plan

Author a manual QA plan the user will execute themselves. You write it; you do not run the tests.

## Rules

- Simple terms, real examples, brief.
- Detect the project type first (API / frontend / full-stack) and shape the steps to it.
- API steps: method + full URL, headers (auth + CSRF), JSON body, expected status + error code, and
  the response field to check.
- Frontend steps: where to go, what to click/type, and the exact visible result to expect.
- End with a progress checklist (checkboxes) so the user can start/stop sessions freely.

## Workflow

1. Identify the feature and its scope. Read its endpoint docs / ADR / UI code to get the exact
   routes, payloads, auth model, error codes, and screens.
2. State what is in scope and what is out of scope (e.g. "backend only, UI not built yet").
3. Write sections: Prereqs → conventions → test cases (happy path + negative + edge) → automated
   smoke (if any) → checklist.
4. Save to a markdown file. Ask the user where; default to `qa/<feature>.md` in the relevant
   slice.
