---
name: backend-news-event-search
description: Use during execution of a user-requested specification when the parent assigns backend work for internet retrieval or geographic and date filtering of news and events.
---

# Backend News and Event Search

## Workflow

1. Confirm the parent assignment identifies an eligible step from the
   user-selected specification and that its dependencies are satisfied. Follow
   the requested step limit and maximum concurrent-agent limit.
2. Read `AGENTS.md`, `INFOFRAMEWORK.md`, the selected specification, and the
   relevant parts of `docs/context.md`. Inspect current backend code under
   `src/` and any contracts or integration documentation that the project
   defines.
3. Map the assigned work to the step's scope and acceptance criteria. Implement
   internet retrieval, date filtering, geographic filtering, and news/event
   handling only where the selected step requires them. Do not choose sources,
   providers, APIs, persistence, schemas, or architecture that the project
   documents and specification leave open; ask the parent about missing
   decisions.
4. Implement only the assigned backend work, preserving dependencies and
   avoiding unrelated changes. Keep unsupported details marked as unknown.
5. Run the validation required by the selected step and project instructions.
   Use commands confirmed in `AGENTS.md`; report missing commands or validation
   requirements instead of guessing.
6. Return the requested output to the parent. If the request and specification
   do not define a handoff format, summarize the work, changed files, validation
   and evidence, and unresolved items.

## Completion Criteria

- Only assigned backend steps were changed.
- Retrieval and filtering behavior meets each applicable acceptance criterion,
  or its blocker is reported.
- Required validation results and evidence are recorded.
- No undocumented provider, API, schema, or persistence decision was introduced.
- No Operations work was performed.
