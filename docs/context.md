# Project Context

This file is the initial source of truth for the project's problem, main
requirement, objective, and architecture. Keep user-defined requirements
distinct from implementation details verified in `../src/`. Cite source paths
for implemented behavior and mark unknowns explicitly.

## 1. INCEPTION - Requirements and Problem Definition

- **Problem:** The project is intended to help a consulter find internet news
  and events for a selected geographic scope and date. This is a restatement of
  the user's project description.
- **Main requirement:** Search the internet for both news and events based on a
  user-selected geographic scope and date.
- **Objective:** Let the consulter choose a scope from world, continent, country,
  region, city, or neighborhood and a date, then find relevant news and events.
- **Primary users or consumers:** People who consult news and events. The
  project owner says they will configure the agent through Codex. The number of
  consultees and any additional user roles are unknown.
- **Scope and constraints:** In scope are internet search, the listed geographic
  levels, user-defined date selection, news, and events. The user initially
  stated that there were no project-specific restrictions; the output guardrail
  below is a later-defined constraint. Sources, date semantics, geographic
  matching rules, and result presentation are not yet defined.
  The agent's behavior and output must stay within the requested news or events
  and the user's stated search parameters; it must not add unrelated content.

## 2. CONSTRUCTION - Architecture

- **Architecture status:** Partial; the user has selected the technology direction
  and development order, while component responsibilities remain TODO.
- **System overview:** Develop the API first, then the frontend with Django.
- **Entry points:** TODO
- **Major components and responsibilities:** TODO
- **Data flow:** TODO
- **External dependencies and integrations:** TODO
- **Architecture decisions and rationale:** The user selected Python, Django, and
  LangGraph, and specified API development before the Django frontend. The exact
  role of LangGraph and the division of component responsibilities are TODO.

## Source Implementation Context

- **Source directory:** `../src/`
- **Implementation status:** No source implementation is present yet.
- **Last source review:** Not yet reviewed.
- **Verified behavior and source paths:** TODO

## 3. OPERATIONS - Human-Owned

- **Deployment, monitoring, and evolution notes:** TODO
- **Operational decisions and actions:** Owned and performed by humans.

## Open Questions

- How are geographic scopes resolved, especially region and neighborhood?
- Does a date mean a single calendar day or a range, and which timezone applies?
- Which internet sources or providers should be searched?
- How should results be ranked, attributed, and presented?
- How will Python, Django, and LangGraph be divided across the API and agent
  components?
