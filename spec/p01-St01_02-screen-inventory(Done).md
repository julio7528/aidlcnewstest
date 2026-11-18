# Especificação: Fase 01 — Inventário de telas

## Referência ao roadmap

- **Fase:** 01 — Arquitetura de informação UX/UI antes da fundação técnica.
- **Etapa coberta:** 01.02 — Definir 14 IDs de inventário, correspondentes a 11 telas autônomas e três experiências agrupadas ou embutidas.
- **Limite:** esta especificação cobre somente a etapa 01.02; as etapas 01.03–01.06 terão especificação separada.
- **Roadmap:** [Fase 01](../docs/project-roadmap.md).

## Mapeamento aos estágios AI DLC

- **INCEPTION — Excluído:** problema, objetivo, requisitos, escopo do MVP e papéis do produto já estão aprovados e são entradas desta etapa.
- **CONSTRUCTION — Incluído:** o incremento produz e valida um artefato de design: o inventário de telas decidido com o proprietário.
- **OPERATIONS — Excluído:** implantação, monitoramento e evolução de produção são humanos e não fazem parte desta etapa.
- **Execução de tarefas de OPERATIONS pelo Codex:** não permitida.

## Objetivo

Produzir um inventário de 14 experiências rastreáveis do GeophNews, aprovadas individualmente pelo proprietário, correspondentes a 11 telas autônomas e três experiências agrupadas ou embutidas. Os 14 IDs preservam a rastreabilidade e não significam 14 páginas independentes.

## Escopo

- **Inclui:** registrar para cada um dos 14 IDs estáveis o nome canônico, público-alvo no nível dos papéis do produto, propósito em uma frase, domínio de informação em alto nível e decisão sobre ser tela autônoma, experiência agrupada ou estado embutido. Registrar justificativa e dúvidas não resolvidas.
- **Não inclui:** rotas, links, redirecionamentos, fronteiras detalhadas de acesso público/autenticado e recursos de API por tela (etapa 01.03); rótulos exatos pt-BR/en-US, responsividade, teclado, componentes, formulários, filtros e interações do mapa (etapa 01.04); wireframes, diagramas de navegação e estados detalhados (etapa 01.05); código de interface, contratos de API ou implementação.
- **Responsabilidade pelas decisões:** propostas só se tornam aprovadas após confirmação explícita do proprietário. Nesta execução, o proprietário confirmou as 14 decisões individuais em um único lote e revisou e aprovou o inventário consolidado em 2026-11-17.

## Entradas aprovadas

- O [roadmap](../docs/project-roadmap.md), etapa 01.02, fornece a lista-base de 14 experiências/IDs rastreáveis.
- [Usuários e Papéis](../docs/ai-dlc/inception/users-and-roles.md) é a fonte de verdade para os dois papéis, estados de conta e permissões dos módulos.
- [Escopo do MVP](../docs/ai-dlc/inception/mvp-scope.md), [Requisitos](../docs/ai-dlc/inception/requirements.md) e [Objetivo do Produto](../docs/ai-dlc/inception/product-objective.md) limitam os propósitos e capacidades do produto.
- A [identidade visual inicial](../docs/visual-identity/README.md) está concluída e é uma dependência aprovada. Esta etapa documenta inventário, sem decidir nova implementação visual.

## Protocolo de decisão assistida pelo proprietário

A execução assistida é sequencial por padrão. Uma autorização explícita do proprietário pode substituir esse formato em uma execução específica.

1. Apresentar uma tela por vez por padrão. O proprietário pode pedir que um pequeno grupo de telas relacionadas seja analisado junto.
2. Para cada tela, apresentar uma proposta concisa e permitir ao proprietário decidir ou revisar o nome, propósito principal, papel do público-alvo, domínio de informação em alto nível e fronteira em relação às telas vizinhas.
3. Resumir a escolha e registrá-la como aprovada somente após confirmação explícita. Manter entradas ainda não confirmadas como **Rascunho** ou **Pendente**.
4. Pausar em cada ponto de decisão para receber a resposta do proprietário; não inferir aprovação por silêncio nem avançar sobre decisões dependentes.
5. Se o proprietário quiser mudar a quantidade ou o escopo das telas, pausar e atualizar o roadmap e esta especificação conforme a orientação recebida antes de continuar.
6. Depois de todas as entradas serem confirmadas, apresentar o inventário completo para revisão final do proprietário, aplicar as correções solicitadas e registrar a aprovação final.

Recomendação de máximo de subagentes simultâneos: **0**, para preservar a participação direta do proprietário nas decisões tela por tela. O usuário informa o máximo na solicitação de execução.

### Exceção aprovada para esta execução — decisão em lote

Em 2026-11-17, o proprietário confirmou explicitamente, em um único lote, o vetor completo de escolhas S01–S14: **1B, 2A, 3B, 4B, 5A, 6B, 7A, 8A, 9A, 10A, 11A, 12A, 13A, 14A**. Para esta execução, essa aprovação substituiu o protocolo sequencial de confirmação individual; as decisões não foram coletadas uma a uma. Cada entrada recebeu status **APPROVED**. Em seguida, o proprietário revisou e aprovou o artefato consolidado; essa aprovação final está registrada no decision log. O fluxo sequencial permanece como padrão para outras execuções.

A classificação aprovada mantém 14 IDs rastreáveis e 11 telas autônomas: S03 e S04 são agrupadas em S02; S06 é um estado embutido em S07.

### Registro de cada decisão

Para cada ID, apresentar e registrar:

- nome canônico e confirmação ou revisão do proprietário;
- público-alvo no nível de papel do produto;
- propósito principal em uma frase;
- domínio de informação em alto nível;
- decisão sobre ser tela distinta ou agrupada com outra tela, com justificativa;
- justificativa concreta da decisão e estado **APPROVED** para as escolhas confirmadas pelo proprietário; usar **Pendente** somente para questões ainda não decididas.

Não usar esta ficha para decidir caminhos de navegação, controles, campos, conteúdo final, layout ou contratos de API.

## Lista-base do roadmap — 14 experiências/IDs candidatos

Os nomes em inglês abaixo foram copiados da etapa 01.02 para manter rastreabilidade aos rótulos-base do roadmap. Os nomes canônicos em pt-BR foram confirmados pelo proprietário no lote desta execução e serão registrados no inventário. A lista não determina rotas, conteúdo detalhado ou layout.

| ID | Nome candidato no roadmap |
| --- | --- |
| S01 | public home |
| S02 | login |
| S03 | signup |
| S04 | password recovery |
| S05 | awaiting admin approval |
| S06 | access denied/no module permission |
| S07 | consumer dashboard/geographic map |
| S08 | NEWS search/results |
| S09 | EVENT AGENDA search/results |
| S10 | admin dashboard |
| S11 | user list |
| S12 | user details/access permissions |
| S13 | aggregated AI usage report |
| S14 | per-user usage detail |

## Critérios de aceite

- O entregável contempla exatamente uma entrada para cada ID S01–S14 e mapeia cada uma à etapa 01.02 do roadmap.
- Cada entrada contém nome canônico, papel do público-alvo, propósito, domínio de informação em alto nível, classificação de fronteira e justificativa; as 14 escolhas foram confirmadas explicitamente pelo proprietário em um lote.
- A classificação total é de 11 telas autônomas, duas experiências agrupadas em S02 (S03 e S04) e um estado embutido em S07 (S06), sem duplicar, excluir ou criar IDs.
- O inventário é coerente com os papéis, permissões, escopo do MVP, requisitos e objetivo aprovados; não introduz capacidade não aprovada.
- As escolhas individuais constam como **APPROVED** e o proprietário aprovou o inventário consolidado; o resultado final está registrado no decision log.
- Qualquer alteração futura da quantidade ou do escopo deve ser refletida no roadmap e nesta especificação.
- Rotas, redirecionamentos, regras detalhadas de autorização, recursos/contratos de API, rótulos de interface, layout, interações, regras responsivas e wireframes ficam reservados às etapas correspondentes.
- Antes de marcar a etapa como concluída, o proprietário revisa e aprova explicitamente o inventário final; o artefato aprovado fica ligado ao índice de documentação e ao log de decisões.

## Etapas

### Etapa 01.02 — Definir o inventário de 14 IDs e 11 telas autônomas

- **Estágio AI DLC:** CONSTRUCTION.
- **Objetivo:** consolidar as 14 decisões individuais aprovadas e classificar as experiências em 11 telas autônomas e três agrupadas ou embutidas.
- **Itens de trabalho:** registrar em `docs/ux-ui/screen-inventory.md` as escolhas em lote S01–S14 e suas justificativas; validar o inventário contra as fontes aprovadas; apresentar o artefato completo para revisão final do proprietário.
- **Dependências:** etapa 01.01 concluída; Usuários e Papéis, Escopo do MVP, Requisitos e Objetivo do Produto aprovados; etapa 01.02 presente no roadmap.
- **Critérios de aceite:** cumprir todos os critérios de aceite desta especificação.
- **Validação:** conferir cobertura exata dos IDs contra o roadmap; validar propósitos e públicos-alvo contra as fontes aprovadas; confirmar o registro das 14 escolhas explicitamente aprovadas; verificar que detalhes das etapas 01.03–01.05 não foram incorporados silenciosamente; abrir e validar links; registrar decisões e estado da revisão final em `docs/decision-log.md`.
- **Status:** Done — decisões individuais S01–S14 registradas como **APPROVED**; inventário consolidado revisado e aprovado pelo proprietário em 2026-11-17.

## Parâmetros da solicitação de execução

- **IDs das etapas ou quantidade a executar:** informados pelo usuário; esta especificação contém somente a etapa 01.02.
- **Máximo de subagentes simultâneos:** informado pelo usuário; `0` significa nenhum. Recomendação: `0` para preservar o processo de decisão assistida.
- **Condição de parada:** parar após a aprovação da etapa 01.02. Não iniciar automaticamente a etapa 01.03 ou outra etapa da Fase 01.
