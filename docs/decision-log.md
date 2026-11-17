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

## 2026-11-12 — CONSTRUCTION architecture defined

- **Owner decisions:** Approved the 11 explicit architecture choices in
  `docs/ai-dlc/architecture/architecture.md`: (1) modular monolith with the
  critical API-first boundary and a separate API-consuming Django Web/UI layer;
  (2) Supabase Auth with backend application authorization and secure manual
  first-Administrator provisioning; (3) Supabase-managed PostgreSQL, Django ORM
  and PostGIS as needed; (4) MapLibre with open, verifiable geographic data and
  deferred licensing/source research; (5) Serper.dev then Tavily through a
  provider abstraction; (6) deterministic eligibility/verification plus
  evidence-grounded Pydantic AI/DeepSeek, without LangGraph or RAG; (7) durable
  asynchronous jobs on PostgreSQL with worker, idempotency, retry, transition
  and cancellation boundaries; (8) ten-minute language/filter-isolated cache
  with current eligibility and authorization checks and correct model metering;
  (9) Django Templates/HTMX/MapLibre UI consuming the API securely; (10)
  PostgreSQL audit and separate provider/LLM usage metering with the approved
  administration boundary; and (11) layered pytest/Django validation including
  the NEWS and EVENT AGENDA p95 ≤120-second validation target under the approved
  normal test profile.
- **Scope:** Documentation-only architecture definition. Approved INCEPTION
  documents, RP-01, product semantics, no-contracts policy and human-owned
  OPERATIONS remain unchanged. No source code, tests, schemas, migrations,
  roadmap steps, specifications, provider calls, deployment or operations work
  was performed.
- **Outcome:** Added the architecture record under
  `docs/ai-dlc/architecture/`; updated its CONSTRUCTION and navigation
  references in `docs/context.md`, `docs/ai-dlc/README.md`, `docs/README.md` and
  `AGENTS.md`. Recorded approved boundaries separately from technical
  uncertainties, including runtime/deployment topology and exact UI-to-API
  invocation choices. Validation was limited to documentation links, content
  consistency and `git diff --check`; no tests were run.

## 2026-11-12 — Roadmap v2 approved

- **Owner approval:** Approved the 15-phase roadmap, with UX/UI information
  architecture and separate screen-design approval before dependent interface
  implementation.
- **Outcome:** Replaced the roadmap placeholder with the ordered Phase 01–15
  feature and step outline. This was documentation-only; no specification,
  design artifact, source code, test, migration, deployment, or Operations task
  was created or executed.

## 2026-11-16 — Initial visual identity added to Phase 01

- **User request:** Add an initial visual identity feature covering colors,
  images, logos, fonts, typography, and icons.
- **Outcome:** Added the visual identity package as the first Phase 01 feature,
  limited to reusable design artifacts for owner review. Renumbered the
  remaining Phase 01 steps to preserve their order. No specification, source
  code, or other phase was changed.

## 2026-11-16 — Phase 01 specification and visual identity documentation

- **Request:** Specify the initial visual identity work, with the owner deciding
  each point, and establish a dedicated documentation folder.
- **Outcome:** Created the Phase 01 specification with a detailed, user-led
  decision process for step 01.01 and an indexed visual identity folder. The
  remaining phase steps are outlined for later detailing. Execution and visual
  decisions remain pending.

## 2026-11-16 — Visual identity specification scope corrected

- **Request:** Restrict the existing specification to step 01.01; document the
  remaining Phase 01 steps separately.
- **Outcome:** Removed the other steps from the specification and recorded the
  Phase 01 exception to the one-specification-per-phase convention. No visual
  identity decisions or execution were performed.

## 2026-11-16 — Brand direction selected

- **User decision:** GeophNews should feel journalistic and geographic, with
  balance, sobriety, and connection between places.
- **Outcome:** Recorded this as the approved brand direction in
  `docs/visual-identity/brand-direction.md`. Other visual identity decisions
  remain open for the user.

## 2026-11-16 — Color palette base selected

- **User decision:** Selected option C, Contemporary Newsroom, as the visual
  identity palette base.
- **Outcome:** Recorded its four hex colors in
  `docs/visual-identity/color-palette.md`. Functional color roles, combinations,
  and contrast checks remain to be decided or validated.

## 2026-11-16 — Color roles assigned

- **User preferences:** Use a light interface with `#F3F5F6` as the base and
  `#252E3B` for text/dark emphasis; reserve `#426D94` for geography; use
  `#A24F4F` as a brand accent and separate semantic colors for system states.
- **Outcome:** Documented the color roles and calculated contrast ratios for
  the planned flat-color combinations. Map-tile combinations require review in
  their rendered context; system-state color values remain open.

## 2026-11-17 — Mixed image direction and prompt set

- **User decision/request:** Use a mix of documentary photography and
  cartographic illustration; prepare ten image-generation prompts for the site
  and create a place in the project for the generated images.
- **Outcome:** Recorded the image direction and created ten standalone prompts
  in `docs/visual-identity/image-prompts.md`. Created the empty destination
  folder `docs/visual-identity/generated-images/`.

## 2026-11-17 — Logo formats and prompt set

- **User decision/request:** Define a long `GeophNews` logo and a short `GN`
  logo, each in light- and dark-theme versions, matching the two provided logo
  sketches, with transparent PNG output. Put four generation prompts in
  `docs/visual-identity/image-prompts.md`.
- **Outcome:** Recorded the approved formats and reference images in
  `docs/visual-identity/logo-direction.md`; added four standalone prompts that
  apply the approved palette and transparent-background requirements. No logo
  artwork was generated in this documentation step.

## 2026-11-17 — Logo files generated and typography exploration started

- **User update/request:** The four logo files are complete; prepare prompts to
  compare the three proposed typographic directions before choosing one.
- **Outcome:** Confirmed the four PNG files in `generated-images/logos/`, updated
  the logo status, and added three comparable typography specimen prompts to
  `docs/visual-identity/image-prompts.md`. Typography remains undecided pending
  the user's review of generated examples.

## 2026-11-17 — Editorial typography direction selected

- **User decision:** Selected Direction 1 — Editorial, pairing serif headlines
  with a neutral sans serif for subtitles, body text, labels, and interface.
- **Outcome:** Recorded the direction in
  `docs/visual-identity/typography-direction.md`. Specific font families,
  weights, hierarchy, fallbacks, and licensing remain to be decided.

## 2026-11-17 — Typeface comparison prompts prepared

- **User request:** List the typography decisions still needed and prepare
  prompts to compare specific family pairings; the user will generate and
  review the examples before choosing.
- **Outcome:** Added a decision checklist and three comparable pairing prompts
  to `docs/visual-identity/prompts.md`. No typeface family was selected.

## 2026-11-17 — Typeface families selected

- **User decision:** Selected Option A: Source Serif 4 for headings and Source
  Sans 3 for body text and interface.
- **Outcome:** Recorded the family pairing in
  `docs/visual-identity/typography-direction.md`. Weights, hierarchy, fallbacks,
  and application details remain open.

## 2026-11-17 — Editorial typography decisions completed

- **User decisions:** Use Source Serif 4 for all page, section, news and event
  titles; H1 700 and H2/card titles 600. Use Source Sans 3 at 400 for body,
  500 for navigation and 600 for buttons. Italic is reserved for quotations;
  letter spacing stays standard. Select the comfortable scale; approve both
  fallback stacks; self-host WOFF2, load only used weights, and use
  `font-display: swap`. Keep the same families and scale in pt-BR and en-US.
- **Mobile sizing:** The supplied values “3236”, “2428” and “1822” were
  interpreted as ranges 32–36, 24–28 and 18–22 px, respectively; the user
  expects refinement in wireframes.
- **Outcome:** Recorded the full typography system and verified the official
  Google Fonts metadata for SIL OFL 1.1, Latin Extended coverage and weight
  axes. Actual local WOFF2 binaries still require validation before use.

## 2026-11-17 — Filled icon direction and crop sheet planned

- **User decision/request:** Use filled icons. Have Codex choose sizes and uses,
  write a prompt for a transparent sheet of equally sized icons, and create an
  empty folder for the cropped files.
- **Outcome:** Defined 24×24 px as the common UI size and 32×32 px for map
  controls; added a 16-icon 4×4 sheet prompt and icon documentation. Created
  `docs/visual-identity/generated-images/icons/` for the cropped PNGs.

## 2026-11-17 — Cropped icon files received

- **User update:** The icon files were created in
  `docs/visual-identity/generated-images/icons/`.
- **Outcome:** Confirmed 16 PNG files with transparency. Their cropped canvas
  dimensions vary; recorded review and size normalization as pending. Original
  files were left unchanged.

## 2026-11-17 — Icon files named and normalized

- **User request:** Review the icon crops, prepare standardized sizes, and
  rename the assets semantically.
- **Outcome:** Visually mapped and renamed 16 icons. Geographic selection and
  map-control icons use transparent 32×32 px canvases; content and interface
  icons use 24×24 px canvases. Preserved the original generated crops in
  `docs/visual-identity/generated-images/icons/source-crops/`. Recorded the
  filename-to-symbol mapping in `icon-direction.md`; user review remains open.

## 2026-11-17 — Icon set approved

- **User decision:** Approved the prepared GeophNews icon set.
- **Outcome:** Recorded explicit approval in `icon-direction.md`; the icon
  theme is closed, subject to the overall visual-identity package review.

## 2026-11-17 — Semantic color, font, and wireframe review started

- **User request:** Continue the visual-identity step with semantic colors and
  contrast verification, WOFF2 validation, and review in wireframes.
- **Outcome:** Recorded icon-set approval. Obtained four regular WOFF2 subset
  files and their OFL licenses from Google Fonts; checked WOFF2 signatures,
  family names, variable axes, and pt-BR accented glyph coverage. Recalculated
  the approved palette contrast pairs and documented a semantic-color proposal
  with two treatments and measured ratios. The semantic tokens, contrast
  target, two typography details, and wireframe review remain open for owner
  decisions.

## 2026-11-17 — Semantic colors, typography checks, and angular wireframe revision

- **User decisions:** Selected 1A–5A: apply WCAG 2.2 AA contrast targets; approve
  the documented semantic color tokens; use the soft-background treatment;
  enable automatic optical sizing for Source Serif 4; and use Source Serif 4
  Italic for quotations. The user also requested square corners and stronger,
  modern strokes after evaluating the open desktop and mobile wireframes.
- **Evaluation:** The open drafts used rounded panels, fields, buttons, and image
  crops, with low-opacity, thin outlines. That treatment did not match the
  user's stated preference.
- **Outcome:** Marked the semantic palette approved; validated the four regular
  and two italic WOFF2 files, including signatures, family/axis metadata,
  Portuguese glyph coverage, and preserved OFL licenses. Revised both wireframes
  to remove rounded corners, use 2 px `#52606D` panel and field outlines, firm
  1.5 px result and semantic-state borders, and a heavier brand navigation
  marker. Updated the visual-identity index, wireframe notes, and step status.
  The revised drafts remain open for the user's visual approval; the complete
  visual-identity package is not yet approved.

## 2026-11-17 — Wireframe outlines reduced

- **User request:** Show the desktop and mobile SVGs with thin outlines instead
  of the previously stronger borders.
- **Outcome:** Kept the square-corner direction and reduced the panel, field,
  result, and semantic-state outlines in both SVGs to 1 px. Reduced the desktop
  header divider to 1 px and the red active-navigation markers to 2 px. Updated
  the wireframe notes and status references. Visual approval remains pending.

## 2026-11-17 — Desktop and mobile wireframes approved

- **User approval:** Approved the desktop and mobile SVG wireframes in the
  square-corner, thin-outline version.
- **Outcome:** Marked the two wireframes approved in their README and updated
  the identity index and Phase 01 step status. The complete visual-identity
  package remains in progress because the four generated logo variants and ten
  generated site images have not yet received explicit visual approval.

## 2026-11-17 — Initial visual identity package approved

- **User approval:** Confirmed that all four logo PNGs and all ten generated
  site images are approved, following the previously approved desktop/mobile
  wireframes, semantic colors, typography, and icon set.
- **Final review:** Confirmed four transparent RGBA logo PNGs, ten WebP image
  assets, 16 normalized transparent icon PNGs, six local WOFF2 files with OFL
  licenses, valid wireframe SVGs, and documented flat-color contrast results.
- **Outcome:** Added the image-asset inventory, recorded logo metadata and
  approval, marked the visual-identity package and Phase 01 Step 01.01 complete,
  and updated project documentation indexes. The external image-generation
  provider and its usage terms were not supplied; this limitation is identified
  in the asset documentation and does not change the user's visual approval.

## 2026-11-17 — ChatGPT identified as visual-asset generator

- **User clarification:** The external tool used to generate the logos and site
  images was ChatGPT.
- **Outcome:** Updated the asset documentation to identify ChatGPT as the
  provider. The applicable usage terms were not reviewed as part of the visual
  identity specification; reuse permissions remain unverified.

## 2026-11-17 — Phase 01 Step 01.02 specification created

- **User request:** Create a separate specification for defining the 14
  principal screens, to be executed with the owner making decisions together
  with Codex during the work.
- **Outcome:** Created `spec/phase-01-screen-inventory.md`, restricted to
  roadmap Step 01.02. It uses the roadmap's 14 candidate screens, an owner-led
  sequential decision protocol, explicit approval checkpoints, scope boundaries
  for Steps 01.03–01.05, and a future artifact path at
  `docs/ux-ui/screen-inventory.md`. The specification is ready; execution has
  not started.

## 2026-11-17 — Phase 01 Step 01.02 execution started

- **User request:** Begin the screen-inventory specification. Step 01.02 is the
  selected step; the user set a maximum of two concurrent subagents.
- **Execution approach:** Used no subagents, within the stated limit and in
  keeping with the specification's owner-led sequential decision protocol.
- **Outcome:** Created the draft inventory at `docs/ux-ui/screen-inventory.md`
  with all 14 roadmap candidates and pending decision fields. S01 — public
  home — is the first owner decision checkpoint; no screen has been approved
  yet.
