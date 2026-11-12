# Agent Instructions

> **Status:** Project-specific guidance is partially configured. Resolve remaining `TODO`s as the architecture and implementation take shape.

## 1. Minimum Quality Standard

- Make changes that are correct, focused, readable, and consistent with the existing project.
- Preserve existing behavior unless the task explicitly calls for a behavior change.
- Prefer the smallest complete change that solves the stated task.
- Document important assumptions and user-visible behavior.
- For each requested implementation step, finish the code, run the relevant tests, and verify the acceptance criteria. If a check fails, fix the issue and repeat testing and verification. Do not advance until the step passes. Record the passing outcome in `docs/decision-log.md`, then continue to the next selected step.
- **TODO:** Define any additional project-specific accessibility, performance, or review standards.

## 2. Security Boundaries

- Do not commit, print, or expose secrets, credentials, private keys, or sensitive user data.
- Use the least access and the narrowest scope needed for a task.
- Do not run destructive commands or make irreversible changes without the approval described below.
- Keep the news and event agent's behavior and output within the user's request and its stated search parameters. Do not add unrelated content or alter or broaden requested parameters.
- Follow additional security requirements the user provides during development.
- **TODO:** Define any further trusted-input, permitted-tool or network-access, data-handling, and environment rules when those requirements are specified.

## 3. Expected Workflow

1. Read the relevant instructions and inspect the existing code, documentation, and contracts. For guided configuration, follow `Setup.md`; for project development, follow the order in `INFOFRAMEWORK.md`.
2. For a project consistency review, read every repository file and compare its project context with other relevant repository files and source-of-truth documents. Leave aligned files unchanged; update only files that conflict with the overall project context.
3. Keep `docs/decision-log.md` explanatory during scaffold preparation. Start recording dated user requests, decisions, and outcomes only after the user begins configuring the project.
4. Define the problem, main requirement, and objective in `docs/context.md` before planning implementation. Define the architecture in that same file before implementing features.
5. Define or update `docs/project-roadmap.md` before creating phase specifications. Keep the roadmap as topic bullets only, with phases, features, and nested steps and no descriptive paragraphs.
6. Create one specification per roadmap phase in `spec/`. Each specification must identify the applicable AI DLC stages and contain ordered steps, scope, dependencies, acceptance criteria, and validation expectations.
7. Treat the AI DLC stages as: INCEPTION for requirements, objectives, and problem definition; CONSTRUCTION for architecture, implementation, tests, and validation; OPERATIONS for deployment, monitoring, and evolution. A specification may cover only the stages needed for its increment. OPERATIONS is fully human-owned; Codex must not execute Operations tasks.
8. Execute a specification only when the user requests it. The request must identify the steps to execute (or their count) and the maximum number of concurrently running subagents. If either value is missing, ask before changing source code.
9. Execute only the selected eligible steps, preserve dependencies and order, and do not continue into another phase automatically. Treat the requested subagent count as a hard ceiling; `0` means no subagents. Parallelize only independent work.
10. After requested CONSTRUCTION work, run relevant tests and validation, then report the selected steps, changes, observed results, and remaining limitations.
11. Keep `docs/context.md`  aligned with user-defined requirements and architecture, then reconcile implementation details against source files under `src/`. Mark unsupported details as unknown. Once project configuration has begun, record the request and outcome in `docs/decision-log.md`.

## 4. Documentation Location

- **Framework documentation:** `docs/`
- **Documentation index:** `docs/README.md`
- **Guided project setup:** `Setup.md`
- **Specifications:** `spec/`
- **Source code:** `src/`
- **Framework execution order:** `INFOFRAMEWORK.md`
- **Codex project configuration:** `.codex/`
- **Project skills:** `.agents/skills/`
- **Prototype directory:** `templates/` is for prototypes.
- **Contracts:** `contracts/`
- Keep documentation close to the code or in the designated documentation location, and update it when behavior or usage changes.
- Project documentation belongs in `docs/` and feature documentation is created or updated after setup according to the AI DLC workflow in `INFOFRAMEWORK.md`. Maintain setup records during setup as required by `Setup.md`.
- **TODO:** Define documentation ownership.

## 5. Code Conventions

- Follow the formatting, naming, structure, and error-handling patterns already used in the relevant part of the project.
- Prefer clear names and straightforward control flow.
- Avoid unrelated refactors and unnecessary dependencies.
- **Language:** Python.
- **Selected technologies:** Python, Django, Django Ninja, HTMX, MapLibre GL JS, PostgreSQL/PostGIS, and Pydantic AI orchestrating DeepSeek; Serper.dev is primary with optional Tavily fallback, Redis is optional, LangGraph is deferred unless future complexity justifies it, and RAG is not planned initially.
- **Development order:** Build the API first, then the frontend with Django, HTMX, and MapLibre GL JS. Define detailed component responsibilities through the AI DLC workflow before implementation.
- **TODO:** Define formatters, linters, naming rules, file organization, and API conventions as the project is developed.

## 6. Approval Criteria 

An explicit user request to execute selected work, as scoped by the prompt and any selected roadmap item or specification, authorizes the in-scope implementation, testing, and verification through completion. Do not request repeated approval for routine steps. Keep the work within the requested scope and follow the selected-step, dependency, and maximum-concurrent-agent requirements in this file.

Obtain separate approval for destructive or difficult-to-reverse actions, costs, external publication or sending, or changes to shared or production systems unless the user explicitly authorized that specific action. Operations remains human-owned; Codex must not perform deployment, monitoring, or production evolution tasks.

- Routine in-scope implementation and validation are authorized as described above; no separate approval roles have been defined.

## 7. Source-Code References

- **Canonical source directories:** `src/`
- **Entry points:** TODO; define when source code is added.
- **Generated or vendored code:** TODO; define paths and handling rules if such code is introduced.
- When referencing implementation details, link to the relevant file and symbol or location where practical.

## 8. Documentation References

- **Documentation index:** `docs/README.md`
- **User request and decision record (after configuration begins):** `docs/decision-log.md`
- **Project context and source implementation details:** `docs/context.md`
- **Approved CONSTRUCTION architecture and technical follow-ups:** `docs/ai-dlc/architecture/architecture.md` (summarized in `docs/context.md`).
- **Approved problem definition:** `docs/ai-dlc/inception/problem-definition.md` (authoritative for the problem only).
- **Approved Product Objective:** `docs/ai-dlc/inception/product-objective.md`.
- **Approved users and roles:** `docs/ai-dlc/inception/users-and-roles.md`.
- **Approved INCEPTION requirements:** `docs/ai-dlc/inception/requirements.md`.
- **Approved MVP scope:** `docs/ai-dlc/inception/mvp-scope.md`.
- **INCEPTION decision resolution register:** `docs/ai-dlc/inception/open-decisions.md` (OD-01 through OD-14).
- **Phase and step roadmap:** `docs/project-roadmap.md`
- **Specification guidance and template:** `spec/README.md`, `spec/SPEC_TEMPLATE.md`
- **Framework execution order:** `INFOFRAMEWORK.md`
- **API/reference docs:** TODO; define when API documentation is created under `docs/` through the AI DLC workflow.
- Prefer the maintained project documentation over copied or outdated guidance.

## 9. Skill References

- **Project skill conventions:** `.agents/skills/README.md`
- Follow a skill when it applies to the task, along with this file and any more specific instructions.
- Each project skill documents its applicability and ordered workflow in `.agents/skills/`.

## 10. Contract References

- **Project contracts:** `contracts/README.md`
- **API and interface contracts:** None planned, per the user's decision; see `contracts/README.md`.
- **Data schemas and validation rules:** No project contracts are planned; define implementation details through the AI DLC workflow if needed.
- **Compatibility or versioning policy:** No project contracts are planned; define a policy through the AI DLC workflow if needed.
- If the user later defines project contracts, treat them as authoritative when changing affected consumers or persisted data.

## 11. Execution and Test Commands

| Purpose | Command |
| --- | --- |
| Install or set up | `TODO: determine from the Python project configuration` |
| Run locally | `TODO: define after the API and Django frontend are configured` |
| Format | `TODO: select a formatter during development` |
| Lint or static checks | `TODO: select checks during development` |
| Tests | `TODO: define from the project test configuration` |
| Build or package | `TODO: define when packaging is established` |

Run the commands relevant to the change and report their results. Do not assume a command exists until it is confirmed in the project configuration.
