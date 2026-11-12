> **Status — INCEPTION approvals: COMPLETE.** Problem Definition, the separately formulated main requirement RP-01, Product Objective, Users and Roles, Requirements, and MVP Scope are approved in their respective records. See the [decision resolution register](ai-dlc/inception/open-decisions.md) and [decision log](decision-log.md). Architecture and implementation are **not approved** and remain for CONSTRUCTION; OPERATIONS is human-owned.

# Project Context

This file is the initial source of truth for the project's problem, main
requirement, objective, and architecture. Keep user-defined requirements
distinct from implementation details verified in `../src/`. Cite source paths
for implemented behavior and mark unknowns explicitly.

## 1. INCEPTION - Requirements and Problem Definition

- **Problem:** Information about recent news and events is fragmented across
  internet sources, making geographically relevant discovery and follow-up
  difficult and requiring manual comparison and checks. See the [approved
  problem definition](ai-dlc/inception/problem-definition.md) for the
  authoritative statement.
- **Requirements baseline:** The [approved INCEPTION requirements](ai-dlc/inception/requirements.md) records the confirmed functional and proposed nonfunctional requirements. The original OD-01 through OD-14 are reconciled in the [resolution register](ai-dlc/inception/open-decisions.md); remaining caveats and deferred technical choices are not open product requirements.
- **Main requirement (RP-01 — Descoberta geográfica unificada; approved 2026-11-11):** “O GeophNews deve permitir que pessoas consumidoras com conta ativa e permissão para o módulo pesquisem, sob demanda, notícias e eventos públicos relacionados à geografia e ao tema selecionados. NEWS deve apresentar notícias com publicação original verificável nas últimas 24 horas; EVENT AGENDA, eventos em andamento ou futuros no intervalo de datas escolhido. Os resultados devem ser concisos, verificáveis e vinculados às fontes originais.”
- **Objective:** The approved objective is maintained in [Product Objective](ai-dlc/inception/product-objective.md).
- **Primary users or consumers:** Exactly two approved product roles—Consumer/User and Administrator—are defined in [Users and Roles](ai-dlc/inception/users-and-roles.md). Authentication, activation, module permissions, and administrator reporting are specified there and in the requirements.
- **Scope and constraints:** The approved MVP boundary is maintained in [MVP Scope](ai-dlc/inception/mvp-scope.md). Both modules are on-demand; use only verified geographic/topic/time matches, preserve source attribution, do not fabricate results, and disclose insufficient evidence or incomplete discovery. NEWS and EVENT AGENDA have distinct temporal rules in the requirements.

## 2. CONSTRUCTION - Architecture

- **Architecture status:** NOT APPROVED. The documented stack and development order are planned technical direction only; detailed architecture and responsibilities remain for CONSTRUCTION.
- **System overview:** Develop the API first, then the frontend with Django.
- **Entry points:** TODO
- **Major components and responsibilities:** TODO
- **Data flow:** TODO
- **External dependencies and integrations:** TODO
- **Planned technical direction (not approved architecture):** Python, Django, Django Ninja, HTMX, MapLibre GL JS, PostgreSQL/PostGIS, Pydantic AI with DeepSeek, Serper.dev primary with Tavily fallback, optional Redis, and API before frontend. Supabase PostgreSQL is the local MVP development environment. LangGraph is deferred; RAG is not planned for the MVP. Vercel hosting is a possible later human-owned OPERATIONS consideration, not a deployment authorization.

## Source Implementation Context

- **Source directory:** `../src/`
- **Implementation status:** No source implementation is present yet.
- **Last source review:** Not yet reviewed.
- **Verified behavior and source paths:** TODO

## 3. OPERATIONS - Human-Owned

- **Deployment, monitoring, and evolution notes:** TODO
- **Operational decisions and actions:** Owned and performed by humans.

## Validation caveats and CONSTRUCTION deferrals

- Approved semantics are authoritative in the linked INCEPTION documents. If source evidence lacks a precise time/duration, local timestamps are ambiguous, or geographic boundaries cannot be verified, report the validation limitation without inventing a value or match.
- Map/geocoding datasets, taxonomies, ranking and deduplication heuristics, provider integration mechanics, and component responsibilities are deferred to CONSTRUCTION; this file does not approve architecture.
- The initial p95 validation target is stated in RNF-003. It is not a service guarantee and has not yet been measured.
