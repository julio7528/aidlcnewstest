# Phase Specifications

- Create one specification file for each phase listed in `../docs/project-roadmap.md`.
- Exception for Phase 01: steps 01.01 and 01.02 have separate step-scoped specifications, as requested by the owner. Steps 01.03–01.06 remain for a later separate specification.
- Name phase files `phase-<number>-<short-name>.md`.
- Define each roadmap phase as ordered, numbered steps.
- Give each step a scope, dependencies, acceptance criteria, and validation expectations.
- Use `SPEC_TEMPLATE.md` as the starting structure.
- Create or update the roadmap before writing a phase specification.
- Execute only a specification selected by the user.

## Current Phase 01 Specifications

- [Step 01.01 — Initial visual identity](phase-01-ux-ui.md) — completed.
- [Step 01.02 — Screen inventory](phase-01-screen-inventory.md) — ready for owner-guided execution.
- Steps 01.03–01.06 are not specified yet.

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
