---
name: spec-acceptance-validation
description: Use during execution of a user-requested specification when the parent assigns QA or validation work for acceptance criteria.
---

# Specification Acceptance Validation

## Workflow

1. Confirm the parent assignment identifies an eligible step from the
   user-selected specification and that its dependencies are satisfied. Follow
   the requested step limit and maximum concurrent-agent limit.
2. Read `AGENTS.md`, `INFOFRAMEWORK.md`, the selected specification, and the
   relevant parts of `docs/context.md`. Inspect the implementation and existing
   tests relevant to the assigned acceptance criteria.
3. Turn each assigned acceptance criterion into a check using only the expected
   behavior stated by the user, specification, or project documentation. Include
   geographic levels, dates, and news versus events only when they are in scope.
   Report missing expected behavior to the parent rather than inventing it.
4. Run the validation listed by the selected step and project instructions,
   using commands confirmed in `AGENTS.md`. Add or modify tests only when that
   work is included in the assignment. Do not broaden validation to unrelated
   features.
5. Record each criterion as passed, failed, or blocked. For failures, provide
   reproducible steps, observed behavior, and relevant file or command evidence.
6. Return the requested output to the parent. If no format is specified, provide
   a concise results summary, evidence, changed test files if any, and unresolved
   items.

## Completion Criteria

- Every assigned acceptance criterion has a pass, fail, or blocked result.
- Required validation was run, or the reason it could not run is documented.
- Findings include enough evidence for the parent to reproduce or review them.
- No out-of-scope implementation work or Operations work was performed.
