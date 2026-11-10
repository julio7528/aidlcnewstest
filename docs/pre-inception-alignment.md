# GeophNews — Provisional Pre-INCEPTION Alignment

> **Status: PROVISIONAL.** This note records decisions stated in the current
> conversation and questions still open for INCEPTION. It is not an approved
> final problem definition, product scope, or detailed architecture. The older
> draft in `context.md` remains pending revalidation; do not treat its
> INCEPTION sections as final.

## Confirmed conversational decisions

### Product and MVP experiences

- The project is **GeophNews** (not GeoNews), an experimental geographic news
  and events discovery portal.
- **NEWS** and **EVENT AGENDA** are equally important first-class experiences
  for the MVP.
- Both experiences support hierarchical geographic selection:
  world > continent > country > state/region > city > neighborhood. A user may
  stop at any level.

### NEWS behavior

- News supports topic/category selection, including **All**, and requested
  result counts of 5, 10, 15, or 20.
- The publication window is a rolling previous 24 hours based on original
  publication time. Exclude stories whose original publication timestamp cannot
  be verified, and return fewer than requested when there are not enough valid
  stories.
- A regional search must cover its subregions. Avoid duplicates and rank for
  relevance while considering geographic diversity. Preserve attribution to
  the original source and its real URL.
- Planned retrieval uses Serper.dev as the primary provider and Tavily as an
  optional supplementary fallback.
- Python services independently validate source URLs, original publication
  times, geographic relevance, and deduplication; these checks do not depend on
  the LLM.
- The DeepSeek API produces evidence-grounded headlines and approximately
  two-line teasers. It may return only source URLs that have already been
  verified.

### Technical direction and workflow

- Planned stack: Python, Django, Django Ninja, HTMX, MapLibre GL JS, and
  PostgreSQL/PostGIS. Pydantic AI orchestrates DeepSeek; Serper.dev is primary
  with optional Tavily fallback; Redis is optional.
- LangGraph is deferred unless future complexity justifies it. RAG is not
  planned initially.
- Build the API before the frontend.
- Preserve the AI DLC/SDD workflow: INCEPTION before CONSTRUCTION; roadmap
  before phase specifications; implementation only for explicitly selected
  steps and within the user's maximum concurrent-subagent limit; QA, tests, and
  verification for each requested step; OPERATIONS remains human-owned.
- Preserve the existing backend, frontend, and QA roles and their applicable
  project skills.
- No formal project contracts are planned, per the prior decision.

## Open questions for INCEPTION

### NEWS

- What topic/category choices should be offered, and how should **All** behave?
- What geographic reference should define state/region, city, and neighborhood
  boundaries and determine subregion coverage?
- What evidence is sufficient to verify an original publication timestamp and
  source URL, and what source attribution details should results display?
- What languages, markets, or source coverage are expected, and when should
  Tavily supplement Serper.dev?
- How should ranking balance relevance and geographic diversity, and what
  precise duplicate cases should be collapsed?

### EVENT AGENDA

- What event-time and date-selection semantics should apply, including event
  occurrence versus announcement time, single date versus range, and timezone?
- Which event categories should be offered?
- What event-source coverage and supplementary-provider behavior are expected?
- How should events be ranked and presented, and which details should each
  result show?
- The NEWS rolling 24-hour original-publication rule does **not** define event
  date or time behavior.

### Cross-cutting

- What additional user roles, if any, should be included in the final project
  definition? The current conversation has not settled this.
- What result presentation and attribution conventions apply across both
  experiences beyond the confirmed NEWS requirements above?
