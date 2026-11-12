# Decision Log

This file will record project-related requests given to Codex, the decisions
made in response, and their outcomes.

Recording begins when the user starts configuring the project. Until then,
this file remains explanatory and contains no request entries.

## 2026-11-08 — Setup interview started

- **Request:** The user asked to begin `Setup.md` and ask the setup questions.
- **Outcome:** Began the interview at stage 1 (`.codex/hooks.json`). No lifecycle
  event or handler was defined, so the hooks object remains empty.

## 2026-11-08 — Preferences for later setup stages

- **User statements:** Use GPT-6 Luna Max; use MCP connections already logged into
  Codex when explicitly requested; no timeout or contract policy; execute a
  requested specification through completion, following `INFOFRAMEWORK.md`.
- **Outcome:** The model remains a user-selected setting; MCP use is manual, not
  a hook. No hook event, matcher, or handler was defined. The specification
  execution preference is being reconciled with the existing `AGENTS.md` rules
  on selected steps, maximum concurrent subagents, and human-owned Operations.

## 2026-11-08 — Project definition and setup answers received

- **User statements:** The intended model is GPT-6 Luna Max, with the user
  configuring it together with Codex. The project should have frontend, backend,
  and QA agents; project skills should be based on those agents; there will be no
  contracts. The project is a regional news search agent that searches the
  internet for news and events by date and geographic scope (world, continent,
  country, region, city, or neighborhood). The user is the only consulter and
  will configure everything through the agent. No restrictions were identified.
- **Outcome:** Captured for later stages. The config and custom-agent files have
  since been handled; contracts and project context remain to be completed.

## 2026-11-08 — Single-request execution preference

- **User request:** When the user asks Codex to execute a task, one request should
  authorize carrying it through without repeated approvals at each routine step.
- **Outcome:** Recorded for the `AGENTS.md` setup stage. No active setting was
  added to `.codex/config.toml` at first. The user then explicitly requested
  `approval_policy = "never"` and access restricted to `C:\dev\projeto`; those
  settings are now recorded in `.codex/config.toml`.

## 2026-11-08 — Custom agent roles defined

- **User decisions:** Use frontend, backend, and QA agents only during execution
  of a requested specification. Derive their detailed tasks and output from the
  user's request and selected spec. Use the normal Codex harness without
  per-agent model, reasoning, or capability preferences.
- **Outcome:** Added `.codex/agents/frontend.toml`, `.codex/agents/backend.toml`,
  and `.codex/agents/qa.toml`, and documented their shared boundaries and handoff
  in `.codex/agents/README.md`.

## 2026-11-08 - Agent role details filled

- **User authorization:** Codex may define and fill the stage 3 agent roles.
- **Outcome:** Expanded frontend duties around geographic/date selection and
  result presentation, backend duties around internet retrieval and filtering,
  and QA duties around acceptance validation. Kept the stack, providers, APIs,
  and persistence unspecified and left detailed tasks to the selected spec.

## 2026-11-08 - Project workflow skills defined

- **User decision:** Codex may define and fill the stage 4 skills based on the
  frontend, backend, and QA agent roles.
- **Outcome:** Added one workflow skill per role under `.agents/skills/`, with
  ordered steps, completion criteria, and no assumed technology stack, provider,
  API, or command set. Updated `.agents/skills/README.md` to index them.

## 2026-11-08 - No project contracts

- **User decision:** The project will not have contracts.
- **Outcome:** Updated `contracts/README.md` to record that decision and to avoid
  leaving TODOs for contract formats or schemas that the user has declined.

## 2026-11-08 - Initial project context recorded

- **User decisions:** Build an internet search agent for news and events by a
  selected date and one of the geographic scopes world, continent, country,
  region, city, or neighborhood. The user stated no project-specific
  restrictions and identified consultation as the user activity.
- **Outcome:** Filled the INCEPTION section of `docs/context.md` and recorded
  unspecified source, date, geographic-matching, result-presentation, and
  architecture details as open questions. Architecture remains for CONSTRUCTION.

## 2026-11-09 - Setup guidance and architecture direction

- **User decisions:** Use Python, Django, and LangGraph, developing the API
  before the Django frontend. For each requested implementation step, finish
  coding, test, and verify; fix failures and repeat until the checks pass, then
  record the passing result here before proceeding. Keep the news/event agent's
  behavior and output within the requested content and stated search parameters.
  Project documentation belongs in `docs/` and follows the AI DLC workflow
  after setup. The user will provide additional security guidance during
  development. Explicitly requested work may proceed through implementation and
  validation without repeated approval, while preserving the selected-step,
  dependency, concurrency-limit, and human-owned Operations rules.
- **Outcome:** Updated `AGENTS.md` and recorded the technology direction and
  output guardrail in `docs/context.md`. The final setup consistency review
  confirmed these decisions align with the project context and the human-owned
  Operations boundary. Detailed architecture, security rules, exact commands,
  and source entry points remain open until defined during project development.
  No project contracts are planned.

## 2026-11-10 — Pre-INCEPTION alignment request

- **Request:** Align project guidance with the confirmed GeophNews decisions
  while keeping this work before INCEPTION approval. Do not finalize the
  existing `docs/context.md` definition, change source code or protected
  settings, populate the roadmap or specifications, or alter the no-contracts
  decision.
- **Outcome:** Added `docs/pre-inception-alignment.md` to distinguish confirmed
  conversational decisions from open questions; marked the existing context
  draft as pending revalidation; updated the documentation index; and corrected
  the current technology direction in `AGENTS.md` (LangGraph deferred, no RAG
  initially). Historical entries above were preserved. Repository portability
  and approval-policy discrepancies were identified and reported without
  changing `.codex/config.toml` or `.codex/hooks.json`.

## 2026-11-10 — Problem Definition approved

- **User approval:** Approved the Brazilian Portuguese problem statement
  reproduced verbatim in `docs/ai-dlc/inception/problem-definition.md`.
- **Scope:** Limited to the first INCEPTION activity and its documentation.
  The main requirement, product objective, users, scope, and architecture remain
  provisional or pending separate review. No specification or implementation
  work was authorized.
- **Outcome:** Created the AI DLC stage index and approved Problem Definition
  artifact; updated only the Problem entry and approval status in
  `docs/context.md`, the documentation indexes and reference in `AGENTS.md`,
  and a forward reference in the historical provisional alignment note.
  `INFOFRAMEWORK.md` and `Setup.md` remain unchanged because their sequence and
  instructions are consistent with this limited approval.

## 2026-11-10 — INCEPTION requirements baseline approved

- **User approval:** The user approved the proposed INCEPTION requirements
  baseline, including its separately labeled nonfunctional requirements.
- **Scope:** Documentation-only INCEPTION requirements. The approved Problem
  Definition remains unchanged; the main requirement, product objective, final
  MVP scope, architecture, implementation, and formal contracts remain outside
  this approval. Open decisions remain unresolved. No CONSTRUCTION or
  OPERATIONS work was authorized.
- **Outcome:** Added `docs/ai-dlc/inception/requirements.md`, updated the AI DLC
  and documentation references, linked the approved baseline from
  `docs/context.md` and `AGENTS.md`, and added a forward reference to the
  historical provisional alignment note. Existing Users and Roles changes
  were preserved and remain documented separately.

## 2026-11-11 — INCEPTION decisions reconciled

- **Owner approval:** On 2026-11-10, the project owner approved eight decision
  sets resolving the previously indexed OD-01 through OD-14, together with the
  MVP scope and DeepSeek as the primary LLM.
- **Scope:** Documentation-only synchronization and validation for INCEPTION.
  The approved Problem Definition remains unchanged. No source code, tests,
  roadmap, specifications, contracts, architecture, CONSTRUCTION, or OPERATIONS
  work was authorized or performed. The separately formulated main requirement
  and detailed architecture remain unapproved; Operations remains human-owned.
- **Outcome:** Created `docs/ai-dlc/inception/mvp-scope.md` and
  `docs/ai-dlc/inception/open-decisions.md`; reconciled the approved requirements,
  Product Objective, Users and Roles, and canonical context; corrected current
  status summaries and references in the documentation indexes and `AGENTS.md`;
  and added a forward pointer to the historical provisional alignment note.
  The local Supabase PostgreSQL development environment and planned technical
  direction are documented without approving architecture. Validation found no
  broken relative Markdown links, preserved the prior RF/RNF identifiers, and
  passed `git diff --check`.

## 2026-11-11 — Main requirement RP-01 approved

- **User approval:** Approved the separately formulated main requirement RP-01
  exactly as presented in the conversation.
- **Scope:** Documentation-only approval of the main INCEPTION requirement.
  This completes the remaining INCEPTION approval; detailed architecture and
  implementation remain for CONSTRUCTION, and OPERATIONS remains human-owned.
- **Outcome:** Recorded the approved requirement in `docs/context.md` and
  reconciled the requirements baseline, Problem Definition approval boundary,
  OD-14, and documentation indexes. No source code, roadmap, specifications,
  architecture, CONSTRUCTION, or OPERATIONS work was performed.
