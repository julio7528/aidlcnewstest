# Especificação: Fase 01 — Inventário de telas

## Referência ao roadmap

- **Fase:** 01 — Arquitetura de informação UX/UI antes da fundação técnica.
- **Etapa coberta:** 01.02 — Definir o inventário das 14 telas principais.
- **Limite:** esta especificação cobre somente a etapa 01.02; as etapas 01.03–01.06 terão especificação separada.
- **Roadmap:** [Fase 01](../docs/project-roadmap.md).

## Mapeamento aos estágios AI DLC

- **INCEPTION — Excluído:** problema, objetivo, requisitos, escopo do MVP e papéis do produto já estão aprovados e são entradas desta etapa.
- **CONSTRUCTION — Incluído:** o incremento produz e valida um artefato de design: o inventário de telas decidido com o proprietário.
- **OPERATIONS — Excluído:** implantação, monitoramento e evolução de produção são humanos e não fazem parte desta etapa.
- **Execução de tarefas de OPERATIONS pelo Codex:** não permitida.

## Objetivo

Produzir um inventário das 14 telas principais do GeophNews aprovado pelo proprietário. Durante a execução assistida, o proprietário decide propósito e fronteiras de cada tela; a lista do roadmap é a base inicial, não uma aprovação antecipada dos detalhes.

## Escopo

- **Inclui:** revisar com o proprietário as 14 entradas do roadmap; definir para cada tela um ID estável, nome canônico, público-alvo no nível dos papéis do produto, propósito em uma frase, domínio de informação em alto nível e decisão sobre ser uma tela distinta ou pertencer a uma tela vizinha. Registrar decisões e dúvidas não resolvidas.
- **Não inclui:** rotas, links, redirecionamentos, fronteiras de acesso público/autenticado e recursos de API por tela (etapa 01.03); rótulos exatos pt-BR/en-US, responsividade, teclado, componentes, formulários, filtros e interações do mapa (etapa 01.04); wireframes, diagramas de navegação e estados detalhados (etapa 01.05); código de interface, contratos de API ou implementação.
- **Responsabilidade pelas decisões:** nomes, propósitos, agrupamentos e fronteiras são propostas para discussão e só se tornam aprovados depois de confirmação explícita do proprietário.

## Entradas aprovadas

- O [roadmap](../docs/project-roadmap.md), etapa 01.02, fornece a lista-base de 14 telas.
- [Usuários e Papéis](../docs/ai-dlc/inception/users-and-roles.md) é a fonte de verdade para os dois papéis, estados de conta e permissões dos módulos.
- [Escopo do MVP](../docs/ai-dlc/inception/mvp-scope.md), [Requisitos](../docs/ai-dlc/inception/requirements.md) e [Objetivo do Produto](../docs/ai-dlc/inception/product-objective.md) limitam os propósitos e capacidades do produto.
- A [identidade visual inicial](../docs/visual-identity/README.md) está concluída e é uma dependência aprovada. Esta etapa documenta inventário, sem decidir nova implementação visual.

## Protocolo de decisão assistida pelo proprietário

A execução será colaborativa e sequencial. A lista-base e qualquer descrição proposta permanecem como rascunho até confirmação do proprietário.

1. Apresentar uma tela por vez por padrão. O proprietário pode pedir que um pequeno grupo de telas relacionadas seja analisado junto.
2. Para cada tela, apresentar uma proposta concisa e permitir ao proprietário decidir ou revisar o nome, propósito principal, papel do público-alvo, domínio de informação em alto nível e fronteira em relação às telas vizinhas.
3. Resumir a escolha e registrá-la como aprovada somente após confirmação explícita. Manter entradas ainda não confirmadas como **Rascunho** ou **Pendente**.
4. Pausar em cada ponto de decisão para receber a resposta do proprietário; não inferir aprovação por silêncio nem avançar sobre decisões dependentes.
5. Se o proprietário quiser mudar a quantidade ou o escopo das telas, pausar e atualizar o roadmap e esta especificação conforme a orientação recebida antes de continuar.
6. Depois de todas as entradas serem confirmadas, apresentar o inventário completo para revisão final do proprietário, aplicar as correções solicitadas e registrar a aprovação final.

Recomendação de máximo de subagentes simultâneos: **0**, para preservar a participação direta do proprietário nas decisões tela por tela. O usuário informa o máximo na solicitação de execução.

### Registro de cada decisão

Para cada ID, apresentar e registrar:

- nome canônico proposto e confirmação ou revisão do proprietário;
- público-alvo no nível de papel do produto;
- propósito principal em uma frase;
- domínio de informação em alto nível;
- decisão sobre ser tela distinta ou agrupada com outra tela, com justificativa;
- estado **Rascunho**, **Pendente** ou **Aprovada**, além da justificativa confirmada.

Não usar esta ficha para decidir caminhos de navegação, controles, campos, conteúdo final, layout ou contratos de API.

## Lista-base do roadmap — 14 telas candidatas

Os nomes em inglês abaixo foram copiados da etapa 01.02 para manter rastreabilidade; são candidatos iniciais para revisão assistida. Os nomes canônicos finais e equivalentes pt-BR serão decididos com o proprietário. A lista não determina propósito final, acesso, conteúdo, rotas ou layout.

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

- O entregável contempla os 14 IDs candidatos e mapeia cada entrada aprovada à etapa 01.02 do roadmap.
- Cada entrada aprovada contém nome canônico, papel do público-alvo, propósito, domínio de informação em alto nível e decisão de fronteira confirmados pelo proprietário.
- O inventário é coerente com os papéis, permissões, escopo do MVP, requisitos e objetivo aprovados; não introduz capacidade não aprovada.
- Nomes e descrições propostos permanecem identificados como pendentes até confirmação explícita. Qualquer alteração da quantidade ou do escopo é refletida no roadmap e nesta especificação.
- Rotas, redirecionamentos, regras detalhadas de autorização, recursos/contratos de API, rótulos de interface, layout, interações, regras responsivas e wireframes ficam reservados às etapas correspondentes.
- O proprietário revisou e aprovou explicitamente o inventário final; o artefato aprovado está ligado ao índice de documentação e ao log de decisões.

## Etapas

### Etapa 01.02 — Definir o inventário das 14 telas principais

- **Estágio AI DLC:** CONSTRUCTION.
- **Objetivo:** produzir o inventário decidido em conjunto conforme descrito nesta especificação.
- **Itens de trabalho:** revisar os candidatos S01–S14 na ordem usando o protocolo assistido; registrar decisões confirmadas em `docs/ux-ui/screen-inventory.md`; identificar dúvidas sem resolvê-las por suposição; validar o inventário contra as fontes aprovadas; apresentar o artefato completo para aprovação final do proprietário.
- **Dependências:** etapa 01.01 concluída; Usuários e Papéis, Escopo do MVP, Requisitos e Objetivo do Produto aprovados; etapa 01.02 presente no roadmap.
- **Critérios de aceite:** cumprir todos os critérios de aceite desta especificação.
- **Validação:** conferir cobertura exata dos IDs contra o roadmap; validar propósitos e públicos-alvo contra as fontes aprovadas; confirmar aprovação explícita de cada entrada; verificar que detalhes das etapas 01.03–01.05 não foram incorporados silenciosamente; abrir e validar links; registrar aprovação e resultado em `docs/decision-log.md`.
- **Estado:** pronta para execução assistida pelo proprietário. Criar esta especificação não inicia a execução nem aprova telas candidatas.

## Parâmetros da solicitação de execução

- **IDs das etapas ou quantidade a executar:** informados pelo usuário; esta especificação contém somente a etapa 01.02.
- **Máximo de subagentes simultâneos:** informado pelo usuário; `0` significa nenhum. Recomendação: `0` para preservar o processo de decisão assistida.
- **Condição de parada:** parar após a aprovação da etapa 01.02. Não iniciar automaticamente a etapa 01.03 ou outra etapa da Fase 01.
