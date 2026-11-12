- Phase 01 — UX/UI information architecture before technical foundation (design artifacts only; no UI code or API contracts)
  - Feature — Screen inventory and navigation
    - Step 01.01 — Define the 14 principal screens: public home; login; signup; password recovery; awaiting admin approval; access denied/no module permission; consumer dashboard/geographic map; NEWS search/results; EVENT AGENDA search/results; admin dashboard; user list; user details/access permissions; aggregated AI usage report; per-user usage detail.
    - Step 01.02 — Map routes, links, redirects, public/authenticated boundaries, and screen-to-API resource/data needs by account role, status, and NEWS/EVENT AGENDA permissions, without defining formal API contracts.
  - Feature — Screen interactions and design artifacts
    - Step 01.03 — Specify pt-BR/en-US labels, responsive and keyboard-accessible patterns, shared components, forms, filters, and map interactions.
    - Step 01.04 — Produce wireframes and navigation diagrams covering loading, queued, running, partial, failed, cancelled, empty, cache-hit, and session-expired states.
    - Step 01.05 — Deliver design artifacts only; obtain separate user approval of detailed screen designs before implementing dependent interfaces in Phases 10–14.

- Phase 02 — Backend technical foundation after Phase 01
  - Feature — Django modular-monolith foundation
    - Step 02.01 — Establish the Django project and logical Django Ninja API and Django Web/UI boundaries, with API implementation first and no assumed microservice or deployment topology.
    - Step 02.02 — Configure local runtime, settings, and Supabase-managed PostgreSQL/PostGIS connectivity; resolve database connection/RLS details while leaving process/deployment topology undecided.
  - Feature — Persistence and engineering conventions
    - Step 02.03 — Define application data ownership, ORM conventions, initial migrations, and development conventions without duplicating Supabase Auth identities or passwords.
    - Step 02.04 — Establish focused pytest/Django validation foundations for settings, database connectivity, migrations, and API/UI boundary rules.

- Phase 03 — Authentication and authorization API
  - Feature — Supabase identity and secure sessions
    - Step 03.01 — Integrate Supabase Auth email/password and Google sign-in; settle callback, session/token rotation, JWT/JWKS validation, and secure BFF mechanics without adding an unapproved auth library.
    - Step 03.02 — Map Supabase identities to exactly the approved Consumer/User and Administrator account types; create new Consumers inactive with no NEWS or EVENT AGENDA permission.
  - Feature — Application access control
    - Step 03.03 — Implement backend checks for current account status, role, independent module permissions, and protected account operations.
    - Step 03.04 — Define and implement the controlled manual first-Administrator bootstrap without public admin self-signup; record access changes in audit data.
  - Feature — Authentication verification
    - Step 03.05 — Add focused tests and verification for Supabase credential validation, sessions, inactive accounts, module isolation, admin authorization, and audit attribution.

- Phase 04 — Geographic API and data foundation
  - Feature — Licensed geographic sources
    - Step 04.01 — Assess open tile, geocoder, and administrative-boundary datasets for licensing, attribution, coverage, and verifiable hierarchy; document unresolved source choices for the applicable specification.
    - Step 04.02 — Model world, continent, country, state/region, city, and neighborhood selection with verified containment and eligible descendants, without fabricating or silently expanding boundaries.
  - Feature — Geographic API behavior
    - Step 04.03 — Provide geographic selection and coverage-limit behavior for the API, including explicit limitations when a place or boundary cannot be verified.
    - Step 04.04 — Add focused tests and verification for hierarchy, containment, selected-level stopping, coverage gaps, and non-fabrication behavior.

- Phase 05 — Durable asynchronous search infrastructure
  - Feature — PostgreSQL-backed jobs and worker
    - Step 05.01 — Implement durable jobs and a worker outside the HTTP request lifecycle, with persisted status/progress and explicit state transitions.
    - Step 05.02 — Implement idempotent submission, safe claiming/recovery, bounded transient retries, cooperative cancellation, and distinct completion, partial, and failure outcomes.
  - Feature — Search-provider abstraction
    - Step 05.03 — Define the common discovery-provider boundary and normalize result provenance, usage, and errors without changing requested filters.
    - Step 05.04 — Integrate Serper.dev as primary and Tavily as fallback for Serper errors/unavailability, retaining the same geography, topic, and time constraints and reporting incomplete discovery.
  - Feature — Job and provider validation
    - Step 05.05 — Add focused tests and verification for job transitions, idempotency, retries, cancellation, recovery, provider fallback, and partial-failure reporting.

- Phase 06 — Shared evidence, AI, cache, and metering services
  - Feature — Evidence and source provenance
    - Step 06.01 — Implement reusable source, original timestamp, geographic evidence, URL provenance, and proportional verification services for NEWS and EVENT AGENDA.
  - Feature — Grounded AI generation
    - Step 06.02 — Integrate Pydantic AI with DeepSeek for evidence-grounded semantic interpretation, relevance assistance, and concise pt-BR/en-US generation, with validation against verified evidence.
  - Feature — Cache, audit, and usage accounting
    - Step 06.03 — Implement the 10-minute PostgreSQL search/results cache with language/filter isolation, current authorization checks, temporal/geographic revalidation, and a documented per-user versus shared-cache scope.
    - Step 06.04 — Record correlated request/job, source, status, timing, cache, provider, model, token, and estimated-cost events; define verifiable pricing inputs and keep search-provider usage/cost separate from DeepSeek calls and tokens.
  - Feature — Shared-service validation
    - Step 06.05 — Add focused tests and verification for evidence gates, URL attribution, LLM output grounding, cache behavior, revalidation, and provider-versus-model metering.

- Phase 07 — NEWS API
  - Feature — NEWS query and eligibility
    - Step 07.01 — Implement user-scoped, on-demand NEWS filters with category/free-text intersection, selected geography, language, and maximum 5/10/15/20 results defaulting to 10.
    - Step 07.02 — Enforce the rolling 24-hour UTC window from verified original publication time, occurrence/direct-impact geography, proportionate source evidence, and no silent filter broadening.
  - Feature — NEWS result pipeline
    - Step 07.03 — Deduplicate event coverage, rank eligible results by approved relevance principles, and produce grounded title, approximately two-line teaser, distinct short description, and verified original source URL.
    - Step 07.04 — Persist and return authorized NEWS job results; add focused tests and verification for time, geography, topics, source attribution, deduplication, ranking, limits, and partial failures.

- Phase 08 — EVENT AGENDA API
  - Feature — EVENT AGENDA query and eligibility
    - Step 08.01 — Implement user-scoped, on-demand filters with category/free-text intersection, explicitly selected inclusive start/end dates and no default range, selected geography, language, and maximum 5/10/15/20 results defaulting to 10.
    - Step 08.02 — Enforce ongoing/future eligibility and real-duration overlap; require verified physical venue for physical/hybrid events and allow fully online events only at WORLD.
  - Feature — Event verification and results
    - Step 08.03 — Apply proportional event evidence, occurrence deduplication, chronological ascending start-time default or relevance sorting, and verified event name/date/venue/description/source fields.
    - Step 08.04 — Persist and return authorized EVENT AGENDA job results; add focused tests and verification for date boundaries, event state, venue/geography, online scope, evidence, sorting, limits, and partial failures.

- Phase 09 — Administration and reporting API
  - Feature — Account management
    - Step 09.01 — Implement authorized account listing/details, activation/deactivation, and independent NEWS/EVENT AGENDA permission changes with audit history.
  - Feature — AI usage reporting
    - Step 09.02 — Implement aggregated and per-user DeepSeek token and estimated-cost reports plus per-generation user transparency, preserving unknown prices and separate provider usage.
  - Feature — Administrative API verification
    - Step 09.03 — Add focused tests and verification for admin-only access, account state/permission changes, user-level report isolation, metering, and excluded admin capabilities.

- Phase 10 — Django Web/UI foundation and public/auth screens
  - Feature — API-consuming web foundation
    - Step 10.01 — Implement Django Templates/HTMX shared responsive pt-BR/en-US layout and a secure session, CSRF, and BFF-style API client that consumes implemented APIs without bypassing them through ORM business queries.
  - Feature — Public and account screens
    - Step 10.02 — Implement public home, login, signup, and password-recovery screens with the approved Supabase Auth flow.
    - Step 10.03 — Implement role-aware redirects, awaiting-approval, access-denied/no-module-permission, and expired-session states.
  - Feature — Web foundation verification
    - Step 10.04 — Add focused tests and verification for layout, locale selection, session handling, CSRF, API-client identity propagation, public/authenticated boundaries, and redirects.

- Phase 11 — Consumer dashboard and interactive MapLibre UI
  - Feature — Geographic consumer navigation
    - Step 11.01 — Implement the consumer dashboard and MapLibre map navigation across world, continent, country, state/region, city, and neighborhood, allowing selection to stop at any level.
    - Step 11.02 — Connect map selection and geographic coverage/error states to the geographic API and authorized NEWS/EVENT AGENDA entry points.
  - Feature — Map UI verification
    - Step 11.03 — Add focused tests and verification for API consumption, map interactions, keyboard access, responsive behavior, permission-aware entry points, and geographic limitations.

- Phase 12 — NEWS UI
  - Feature — NEWS filters and job flow
    - Step 12.01 — Implement category and narrowing free-text filters, result count, language, search submission, and queued/running job progress through the NEWS API.
    - Step 12.02 — Implement empty, cache-hit, partial, failed, and cancelled states without broadening the selected filters.
  - Feature — NEWS results and verification
    - Step 12.03 — Present verified NEWS cards with grounded title, teaser, distinct short description, original source links, and current-generation token/cost details.
    - Step 12.04 — Add focused tests and verification for category intersection, filters, states, source links, accessibility, API authorization, and user-attributed generation usage.

- Phase 13 — EVENT AGENDA UI
  - Feature — Event filters and job flow
    - Step 13.01 — Implement required start/end date selection, geography, category/free-text filters, sorting, result count, search submission, and queued/running job progress through the EVENT AGENDA API.
    - Step 13.02 — Implement empty, cache-hit, partial, failed, and cancelled states while preserving the selected inclusive date range and filters.
  - Feature — Event results and verification
    - Step 13.03 — Present verified event cards with event name, date/time when verified, physical venue or WORLD-only online status, concise description, source links, and usage attribution.
    - Step 13.04 — Add focused tests and verification for required dates, filters, sorting, venue/geographic rules, event states, accessibility, source links, and API authorization.

- Phase 14 — Administration UI
  - Feature — User management
    - Step 14.01 — Implement admin dashboard, user list, and user details with active/inactive controls and independent NEWS/EVENT AGENDA permission management through the API.
  - Feature — AI usage reports
    - Step 14.02 — Implement aggregated usage reporting and per-user drill-down for DeepSeek tokens, estimated cost, and generation attribution.
  - Feature — Administration UI verification
    - Step 14.03 — Add focused tests and verification for admin-only screens/actions, audit visibility, user-level report isolation, accessibility, and excluded admin capabilities.

- Phase 15 — Integrated MVP validation
  - Feature — Cross-phase journeys and security
    - Step 15.01 — Validate end-to-end public, authenticated, pending, Consumer, and Administrator journeys across browser and API boundaries, including authorization and CSRF.
  - Feature — NEWS and EVENT AGENDA correctness
    - Step 15.02 — Validate NEWS/EVENT AGENDA geotemporal eligibility, category/free-text semantics, source evidence, provenance, deduplication, and distinct result states.
  - Feature — Jobs, providers, cache, and metering
    - Step 15.03 — Validate asynchronous progress/cancellation, Serper-to-Tavily fallback, partial failures, cache revalidation, and user-attributed provider-versus-LLM usage/cost.
  - Feature — Accessible bilingual MVP and performance
    - Step 15.04 — Validate pt-BR/en-US, responsive and keyboard-accessible journeys, plus the separate NEWS and EVENT AGENDA p95 ≤120-second validation target (not an SLA) for up to 10 results and five concurrent users under controlled normal conditions.
