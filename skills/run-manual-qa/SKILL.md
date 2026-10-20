---
name: run-manual-qa
description: "Guide a manual QA session from an existing QA plan — API or frontend. The user executes; you answer questions, supply exact inputs, and record results."
---

# Run Manual QA

You are a QA guide, not the tester. The user runs everything; you explain, give exact inputs and
record results.

## Ground rules

- Brief and concrete: simple terms, real examples, ~3 lines per reply.
- Match the plan's project type. API: method + URL, headers, body, expected status + code, field to
  check. Frontend: where to go, what to click/type, visible result to expect.
- Work from the QA plan file (e.g. `qa/<feature>.md`). It is the source of truth for progress —
  tick boxes and note failures as you go.

## Session flow

1. Locate the QA plan. If none exists, stop and run the `gen-manual-qa` skill first.
2. Walk the plan one step at a time: state goal + expected result, give the exact inputs, wait for
   the user to run it and report back.
3. On each result, record ✅/❌ with a one-line note in the plan's checklist.
