# Phase Specifications

- Create one specification file for each phase listed in `../docs/project-roadmap.md`.
- Exception for Phase 01: steps 01.01–01.06 have separate step-scoped specifications, as requested by the owner.
- Put the phase, roadmap step, short name, and current execution status in every specification filename.
- For one step, use `p<PP>-St<SS>_<NN>-<short-name>(<Status>).md`; replace the period in the roadmap step ID with an underscore. Example: `p01-St01_06-design-approval(Backlog).md`.
- For one phase-wide specification covering a continuous step range, include both endpoint IDs: `p<PP>-St<first-SS>_<first-NN>-<last-SS>_<last-NN>-<short-name>(<Status>).md`.
- Use a lowercase, hyphen-separated short name. Use exactly these case-sensitive status values: `Backlog`, `Doing`, `Waiting`, or `Done`.
- **Backlog:** execution has not started. **Doing:** execution is active. **Waiting:** execution started but is paused for owner input, approval, or an external response. **Done:** acceptance criteria are complete and required owner approval is recorded.
- The filename status tracks execution, not specification authoring. Keep it synchronized with the specification's Status field and this index; rename the file and update links when its status changes.
- Define each roadmap phase as ordered, numbered steps.
- Give each step a scope, dependencies, acceptance criteria, and validation expectations.
- Use `SPEC_TEMPLATE.md` as the starting structure.
- Create or update the roadmap before writing a phase specification.
- Execute only a specification selected by the user.

## Current Phase 01 Specifications

- [Step 01.01 — Initial visual identity](<p01-St01_01-initial-visual-identity(Done).md>) — Done.
- [Step 01.02 — Screen inventory](<p01-St01_02-screen-inventory(Done).md>) — Done; final inventory approved by the owner.
- [Step 01.03 — Route and resource map](<p01-St01_03-route-resource-map(Waiting).md>) — Waiting for owner questionnaire responses; Step 01.02 is approved.
- [Step 01.04 — Screen interactions and patterns](<p01-St01_04-screen-interactions(Backlog).md>) — Backlog; Step 01.02 is approved, and execution depends on Step 01.03 approval.
- [Step 01.05 — Wireframes and navigation diagrams](<p01-St01_05-wireframes-navigation(Backlog).md>) — Backlog; Step 01.02 is approved, and execution depends on Steps 01.03–01.04 approval.
- [Step 01.06 — Design package and approval](<p01-St01_06-design-approval(Backlog).md>) — Backlog; Step 01.02 is approved, and execution depends on completion and approval of Steps 01.03–01.05.

## AI DLC Stages

1. **INCEPTION** - Requirements, objectives, and problem definition.
2. **CONSTRUCTION** - Architecture, implementation, tests, and validation.
3. **OPERATIONS** - Deployment, monitoring, and evolution; fully human-owned.

- Each specification must state which AI DLC stages apply to its increment and which do not.
- A specification does not need to use all three stages.
- Codex may identify Operations work as human-owned, but must not execute it.

## Execution Parameters

- Each execution request must identify the spec steps to execute or state how many eligible steps to execute.
- Each execution request must state the maximum number of concurrently running subagents; `0` means no subagents.
- Ask for either value if it is missing before changing source code.
- If the user lists step IDs, execute only those steps after confirming their dependencies are satisfied.
- If the user gives a step count, execute the next eligible pending steps in specification order, respecting dependencies.
- Use parallel subagents only for independent work and never exceed the requested maximum.
- Stop after the requested steps; do not start another phase automatically.
- Run tests and validation for the requested CONSTRUCTION steps and report observed results.
