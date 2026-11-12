> **Status — INCEPTION approvals: COMPLETE; CONSTRUCTION architecture: APPROVED.** Problem Definition, the separately formulated main requirement RP-01, Product Objective, Users and Roles, Requirements, and MVP Scope are approved in their respective records. See the [decision resolution register](ai-dlc/inception/open-decisions.md), [approved architecture](ai-dlc/architecture/architecture.md), and [decision log](decision-log.md). Implementation remains pending a separate request; OPERATIONS is human-owned.

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

- **Architecture status:** APPROVED at the decision level on 2026-11-12. The [CONSTRUCTION architecture record](ai-dlc/architecture/architecture.md) is authoritative for approved boundaries and explicitly undecided implementation choices; approved INCEPTION semantics remain unchanged.
- **System overview:** A Django modular monolith exposes a Django Ninja API first and a distinct Django Templates/HTMX/MapLibre Web/UI layer afterward. The UI consumes the API; API owns business logic, validation, and authorization. These are logical boundaries and do not require microservices, separate repositories, or separate deployments.
- **Major responsibilities:** Accounts/authentication and authorization; geography; provider-backed discovery/search; independent NEWS and EVENT AGENDA rules; evidence/source verification; Pydantic AI/DeepSeek editorial assistance; PostgreSQL-backed asynchronous jobs; PostgreSQL cache; and usage/audit metering.
- **Data flow:** Authenticated UI request → API token and current account/module authorization → durable PostgreSQL job → worker discovery (Serper.dev then Tavily fallback), deterministic eligibility/evidence checks, and evidence-grounded DeepSeek generation → persisted results/provenance/usage → authorized API polling and UI presentation.
- **Data and identity ownership:** Supabase Auth owns credentials and identity/session issuance. Supabase-managed PostgreSQL is shared application persistence through Django ORM, with PostGIS where needed. Application mappings, roles/permissions, jobs/results/evidence/cache and usage/audit are not duplicate Auth identities or passwords.
- **Runtime boundary:** A worker runs independently of the HTTP request lifecycle using a durable PostgreSQL job model. Exact runtime/deployment topology and UI-to-API transport remain implementation choices; no microservices or hosting topology is mandated.
- **External dependencies:** Supabase Auth/PostgreSQL, Serper.dev with Tavily fallback, Pydantic AI with DeepSeek, and open verifiable MapLibre-compatible geographic sources. Dataset/geocoder/licensing research and detailed provider mechanics remain technical follow-ups.
- **Cache and controls:** Search/results cache TTL is 10 minutes with language/filter isolation, current authorization, and temporal/geographic revalidation before display. Deterministic checks govern eligibility and attribution; LLM output must remain grounded in verified evidence. LangGraph and RAG are not in the MVP.
- **Development order:** API → backend validations, worker and integrations → API-consuming Django Web/UI. No implementation is authorized by this documentation update.
- **Operations:** Initial runtime is local with Supabase PostgreSQL. Vercel is only a possible future human-owned OPERATIONS consideration; no deployment, monitoring, or operations work is authorized here.

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
