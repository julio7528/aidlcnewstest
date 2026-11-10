# Setup

## Purpose

This file is an interactive setup guide for configuring the project through
Codex CLI. It asks for the information needed to fill the project files in the
sequence below.

## Activation

- Start this process only when the user explicitly asks to begin setup using `Setup.md` or gives an equivalent instruction.
- Creating or reading this file does not start the setup interview.
- When setup is activated, project configuration has begun; start recording new setup requests and decisions in `docs/decision-log.md`. Do not backfill earlier scaffold work.

## Interview Rules

- Read this file, `AGENTS.md`, `INFOFRAMEWORK.md`, and the current contents of each target before asking questions or editing.
- Follow the file sequence below exactly.
- Ask focused questions for the current file group only. Continue in later turns as needed; do not ask the entire questionnaire at once.
- Do not invent requirements, settings, roles, skills, contracts, commands, or approval rules. Ask for missing information or leave it marked as `TODO` when the user chooses to defer it.
- After each stage has enough answers, update that stage's files and briefly summarize what was captured before moving to the next stage.
- Preserve established project decisions, including the English language of `AGENTS.md` and the rule that Operations is human-owned.
- If existing files conflict with a new answer, show the conflict and ask which decision should prevail before overwriting established project context.
- Do not add active hooks, scripts, credentials, or permissive security settings based on assumptions.
- At the end, compare all files touched during setup with one another and with the project context. Fix only inconsistencies, then summarize completed files and remaining `TODO` items.

## Setup Sequence

### 1. `.codex/hooks.json`

Ask:

- Which Codex lifecycle events, if any, should trigger hooks?
- What should each hook do, and under what matching conditions?
- Does the hook need to run a command or call an already-configured MCP tool?
- What should happen when the hook fails or reaches its timeout?

Setup rules:

- Keep `hooks` empty when no hook has been defined.
- Before adding an active command hook, obtain the exact event, matcher, command, and intended effect from the user.
- Do not define hooks that deploy, monitor, or evolve production systems; Operations is human-owned.
- Project-local hooks require a trusted project and review before they run. See [Codex hooks](https://learn.chatgpt.com/docs/hooks).

### 2. `.codex/config.toml`

Ask which shared project settings are needed, such as approved MCP connections or project-wide agent defaults. Confirm each setting's purpose and value before adding it.

Setup rules:

- Keep the file without active settings when the user has not selected any.
- Use only documented, supported keys. Keep credentials, authentication, personal preferences, and machine-specific settings out of project configuration.
- Project configuration is loaded only for trusted projects, and some user-level settings cannot be overridden from a project file. See [Codex configuration basics](https://learn.chatgpt.com/docs/config-file/config-basic) and the [configuration reference](https://learn.chatgpt.com/docs/config-file/config-reference).

### 3. `.codex/agents/`

For each project-specific agent the user wants, ask for:

- Name and purpose.
- When Codex should use it.
- Its exact developer instructions and expected output.
- Any model, reasoning, or capability preferences the user wants to set.

Create one TOML file per defined role. Each custom agent file must include `name`, `description`, and `developer_instructions`. Do not create role files for undefined agents. See [Codex custom agents](https://learn.chatgpt.com/docs/agent-configuration/subagents).

### 4. `.agents/`

Ask which repeatable project workflows should become skills. For each requested skill, establish:

- Name and description, including when to use it.
- The ordered workflow and completion criteria.
- Any required references, scripts, or assets.

Create only skills whose workflows are defined. Use `.agents/skills/<skill-name>/SKILL.md` and add supporting folders only when needed. Do not create placeholder skills.

### 5. `contracts/`

Ask which project contracts are needed, such as interfaces, APIs, data schemas, events, compatibility rules, or validation requirements. For each contract, establish its authoritative format, owner, versioning expectations, and consumers before creating it.

Leave undefined contracts as `TODO` in the directory documentation; do not invent schemas or interfaces.

### 6. `docs/context.md` - INCEPTION

Ask for and record the project's initial definition:

- The problem being addressed.
- The main requirement.
- The project objective.
- Primary users or consumers.
- Scope, constraints, and known unknowns.

Keep requirements and decisions attributed to the user distinct from implementation facts. Architecture is defined in the later CONSTRUCTION step described in `INFOFRAMEWORK.md`; leave it open until those decisions are requested.

### 7. `AGENTS.md`

Update `AGENTS.md` last, using the settled setup decisions and the existing framework rules. Ask only for missing project-specific guidance, including:

- Minimum quality and review expectations.
- Security boundaries and approval criteria.
- Code conventions and project workflow.
- Documentation, source, skill, and contract locations.
- Execution, test, and validation commands.

Keep `AGENTS.md` in English. Preserve the AI DLC workflow, the incremental roadmap/spec process, the user-selected execution limits, and the human-only Operations boundary. Link to detailed material instead of duplicating it.

## Completion

- Report which files were created or updated.
- List unanswered items left as `TODO`.
- Confirm the project context and file references agree.
- Do not begin feature implementation as part of setup unless the user separately requests an eligible spec execution.
