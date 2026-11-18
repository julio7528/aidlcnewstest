# Framework Documentation

This directory contains maintained documentation for the framework and project.

Use it for explanations of framework structure, decisions, contributor
guidance, and operator guidance. The `templates/` directory is for prototypes.

- `../INFOFRAMEWORK.md` - required order for framework setup and incremental work.
- `../Setup.md` - guided interview for initial project setup.

## AI DLC

- `ai-dlc/README.md` — index of the INCEPTION, CONSTRUCTION, and human-owned OPERATIONS stages.
- `ai-dlc/architecture/architecture.md` — approved CONSTRUCTION architecture decisions, component responsibilities, flows, security boundaries, and explicitly undecided technical follow-ups.
- `ai-dlc/inception/problem-definition.md` — authoritative approved problem statement.
- `ai-dlc/inception/product-objective.md` — authoritative approved Product Objective.
- `ai-dlc/inception/users-and-roles.md` — authoritative approved account roles, authentication, permissions, and administration boundaries.
- `ai-dlc/inception/requirements.md` — approved INCEPTION functional and nonfunctional requirements.
- `ai-dlc/inception/mvp-scope.md` — authoritative approved MVP inclusions, exclusions, constraints, and later-version boundaries.
- `ai-dlc/inception/open-decisions.md` — resolution register for OD-01 through OD-14.

## Project Records

- [Phase 01, Step 01.03 specification](<../spec/p01-St01_03-route-resource-map(Waiting).md>) — Step 01.02 is approved; execution is waiting for owner questionnaire responses.
- [Phase 01, Step 01.04 specification](<../spec/p01-St01_04-screen-interactions(Backlog).md>) — Step 01.02 is approved; execution depends on Step 01.03 approval and a separate user request.
- [Phase 01, Step 01.05 specification](<../spec/p01-St01_05-wireframes-navigation(Backlog).md>) — Step 01.02 is approved; execution depends on Steps 01.03–01.04 and a separate user request.
- [Phase 01, Step 01.06 specification](<../spec/p01-St01_06-design-approval(Backlog).md>) — Step 01.02 is approved; execution depends on Steps 01.03–01.05 and a separate user request.

- `visual-identity/README.md` — approved initial GeophNews visual identity package for Phase 01, Step 01.01; records assets, decisions, validation, and the remaining ChatGPT asset-terms review limitation.
- `ux-ui/screen-inventory.md` — consolidated inventory of 14 owner-approved IDs for Phase 01, Step 01.02: 11 standalone screens, S03/S04 grouped in S02, and S06 embedded in S07; final artifact approved.
- [Step 01.02 specification](<../spec/p01-St01_02-screen-inventory(Done).md>) — owner-guided inventory; final artifact approved by the owner.

- `decision-log.md` — explains the request and decision record, which starts when project configuration begins.
- `context.md` — canonical project context; all INCEPTION approvals, including main requirement RP-01, are complete. Its CONSTRUCTION summary links to the approved architecture record.
- `pre-inception-alignment.md` — **PROVISIONAL / HISTORICAL** record; later approved decisions are maintained in the INCEPTION artifacts and resolution register.
- `project-roadmap.md` - incremental phase, feature, and step outline written only as topic bullets.
- `../spec/README.md` and `../spec/SPEC_TEMPLATE.md` - AI DLC stage mapping and phase specification workflow.

```
Nota pessoal:
1. INCEPTION — definir o problema, os requisitos, o objetivo, os usuários, o escopo e as dúvidas em aberto.
2. CONSTRUCTION — definir a arquitetura; planejar fases no roadmap; criar uma especificação por fase; implementar os passos selecionados; testar e verificar. Se algo falhar, corrigir e repetir. Depois de aprovar cada passo, registrar o resultado e atualizar a documentação.
3. OPERATIONS — implantar, monitorar e evoluir o sistema. Esta etapa é humana; o Codex não a executa.

No seu projeto, a arquitetura e o roadmap já estão definidos, e as etapas 01.01 e 01.02 foram concluídas. O proprietário confirmou em lote as 14 decisões individuais e aprovou o inventário consolidado em `ux-ui/screen-inventory.md`.
```
