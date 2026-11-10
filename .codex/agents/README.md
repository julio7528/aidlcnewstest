# Custom Agent Definitions

These roles are used only for steps in a specification whose execution the user
has requested. The parent Codex agent assigns eligible steps and coordinates
dependencies and handoffs.

| Agent | Responsibility |
| --- | --- |
| `frontend` | Implement assigned geographic and date selection and news/event result presentation as the specification defines them. |
| `backend` | Implement assigned internet retrieval and geographic/date filtering for news and events as the specification defines them. |
| `qa` | Validate assigned acceptance criteria and report observed results with evidence. |

Detailed behavior and output come from the user request and selected
specification. These roles use the normal Codex harness and inherit the parent
model, reasoning, permissions, tools, and skills. No technology stack, API,
provider, or persistence choice is established by these roles.