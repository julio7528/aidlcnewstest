---
name: frontend-spec-implementation
description: Use during execution of a user-requested specification when the parent assigns frontend work for geographic or date selection, or news and event result presentation.
---

# Frontend Specification Implementation

## Workflow

1. Confirm the parent assignment identifies an eligible step from the
   user-selected specification and that its dependencies are satisfied. Follow
   the requested step limit and maximum concurrent-agent limit.
2. Read `AGENTS.md`, `INFOFRAMEWORK.md`, the selected specification, and the
   relevant parts of `docs/context.md`. Inspect existing frontend code under
   `src/` and follow established patterns where they exist.
3. Map the assigned work to the step's scope and acceptance criteria. Work with
   geographic levels, date selection, and news or event results only where the
   selected step includes them. Ask the parent about missing behavior or
   conflicting requirements instead of inventing UI behavior or data shapes.
4. Implement only the assigned frontend work, preserving dependencies and
   avoiding unrelated changes. Use APIs and contracts only when defined by the
   selected specification or project documentation.
5. Run the validation required by the selected step and project instructions.
   Use commands confirmed in `AGENTS.md`; report missing commands or validation
   requirements instead of guessing.
6. Return the requested output to the parent. If the request and specification
   do not define a handoff format, summarize the work, changed files, validation
   and evidence, and unresolved items.

## Completion Criteria

- Only assigned frontend steps were changed.
- Each applicable frontend acceptance criterion is met or its blocker is
  reported.
- Required validation results and evidence are recorded.
- No Operations work was performed.
