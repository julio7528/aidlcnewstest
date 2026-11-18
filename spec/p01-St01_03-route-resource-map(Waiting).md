# Especificação: Fase 01 — Mapeamento de rotas e recursos

## Referência ao roadmap

- **Fase:** 01 — Arquitetura de informação UX/UI antes da fundação técnica.
- **Etapa coberta:** 01.03 — mapear rotas, links, redirecionamentos, fronteiras públicas/autenticadas e necessidades de recursos/dados de API por tela, papel, estado da conta e permissões de NEWS/EVENT AGENDA.
- **Limite:** esta especificação cobre somente a etapa 01.03. As etapas 01.04–01.06 permanecem em especificações separadas.
- **Roadmap:** [Fase 01](../docs/project-roadmap.md).

## Mapeamento aos estágios AI DLC

- **INCEPTION — excluído:** problema, objetivo, requisitos, papéis, permissões e escopo do MVP já estão aprovados e são entradas desta etapa.
- **CONSTRUCTION — incluído:** o incremento produz e valida um artefato de arquitetura de informação para rotas, navegação, acesso e necessidades de dados.
- **OPERATIONS — excluído:** implantação, monitoramento e evolução de produção são humanos e não fazem parte desta etapa.
- **Execução de tarefas de OPERATIONS pelo Codex:** não permitida.

## Objetivo

Documentar, com revisão do proprietário, como as experiências aprovadas no inventário de telas se conectam por rotas, links e redirecionamentos; quais fronteiras de acesso se aplicam; e quais capacidades e dados conceituais cada tela precisa consumir da API, considerando papel, estado da conta e permissões independentes dos módulos NEWS e EVENT AGENDA.

## Escopo

- **Inclui:** mapa de navegação e destinos; propostas de rotas visíveis na UI; links e redirecionamentos; classificação de acesso público ou autenticado; matriz de acesso para papel, estado e permissões de módulo; e matriz conceitual de necessidades de recursos/dados por tela.
- **Artefato previsto:** docs/ux-ui/route-resource-map.md.
- **Não inclui:** alterar o inventário aprovado; definir contratos formais, endpoints, métodos HTTP, schemas, payloads, códigos de resposta ou autenticação técnica; implementar rotas, API ou UI; especificar rótulos, responsividade, teclado, componentes, formulários, filtros e interações da etapa 01.04; produzir wireframes e diagramas detalhados da etapa 01.05; nem executar OPERATIONS.
- **Fronteira da API:** descrever necessidades de negócio e dados em nível conceitual. A API é dona da lógica de negócio, validação e autorização; a UI consome a API. Não prescrever acesso da UI direto ao ORM.
- **Decisões do proprietário:** nomes e caminhos candidatos de rota, ligações entre experiências, destinos de redirecionamento e ambiguidades de acesso devem permanecer como propostas ou pendências até confirmação explícita. Não inferir aprovação por silêncio.

## Entradas e dependências

- O [roadmap](../docs/project-roadmap.md), etapa 01.03, define o resultado solicitado e seus limites.
- O [inventário de telas](../docs/ux-ui/screen-inventory.md) da etapa 01.02 é a entrada direta e foi revisado e aprovado pelo proprietário em 2026-11-17. A execução desta especificação permanece não iniciada e só ocorrerá após solicitação própria do usuário.
- [Usuários e Papéis](../docs/ai-dlc/inception/users-and-roles.md) é a fonte de verdade para os dois papéis, autenticação, estados da conta e permissões independentes.
- [Requisitos](../docs/ai-dlc/inception/requirements.md), [Escopo do MVP](../docs/ai-dlc/inception/mvp-scope.md) e [Objetivo do Produto](../docs/ai-dlc/inception/product-objective.md) limitam as capacidades que podem aparecer na navegação.
- [Arquitetura aprovada](../docs/ai-dlc/architecture/architecture.md) define as fronteiras lógicas API-first e os detalhes técnicos que esta etapa não deve antecipar.
- A identidade visual da etapa 01.01 está concluída. Ela não altera as decisões de acesso ou recursos desta especificação.

## Regras de interpretação

- Usar exatamente os IDs e os agrupamentos definidos na versão final aprovada do inventário; manter rastreabilidade de S01–S14 sem criar ou descartar experiências.
- Tratar os papéis do produto como Usuário/Consumer e Administrador/Administrator. Não criar papéis adicionais.
- Distinguir pessoa anônima de pessoa autenticada. Para contas, usar os estados aprovados ativo e inativo; “aguardando aprovação” é uma experiência associada a uma conta inativa, não um novo estado de conta.
- Uma conta inativa não pode utilizar o portal, mesmo que permissões de módulo estejam registradas. Uma conta ativa do tipo Usuário só pode usar cada módulo quando a permissão correspondente estiver concedida.
- Considerar NEWS e EVENT AGENDA separadamente: sem permissão, NEWS apenas, EVENT AGENDA apenas, ou ambas. Não inferir autorização para um módulo a partir da permissão do outro.
- Para Administrador, mapear somente capacidades administrativas aprovadas: gestão do estado/permissões das contas e consulta dos relatórios de uso de IA previstos. Não inferir capacidade de pesquisar NEWS ou EVENT AGENDA como Administrador; registrar como não definida se surgir essa necessidade.
- A semântica pública da página inicial e qualquer ambiguidade remanescente no inventário devem seguir a decisão explícita do proprietário. A regra aprovada de autenticação para uso do portal não torna automaticamente pública qualquer capacidade autenticada.
- Se a revisão final do inventário 01.02 alterar quantidade, nomes, agrupamentos ou limites, reconciliar o escopo desta especificação antes de executá-la.

## Critérios de aceite

- O artefato cobre exatamente as experiências do inventário 01.02 aprovado, com cada ID rastreável e qualquer agrupamento claramente indicado.
- O mapa mostra as relações de navegação, links e destinos de redirecionamento entre as experiências, incluindo entradas públicas, autenticação, conta inativa, ausência de permissão, saídas e caminhos administrativos pertinentes.
- Cada rota candidata está identificada como pública ou protegida e registra as condições relevantes de papel, autenticação, estado ativo/inativo e permissões de módulo.
- A matriz de acesso trata, no mínimo, os casos anônimo; Usuário inativo; Usuário ativo sem permissões; Usuário ativo com NEWS; Usuário ativo com EVENT AGENDA; Usuário ativo com ambas; Administrador ativo; e conta Administrador inativa. Ela indica o destino, acesso permitido ou negado e eventual experiência associada, sem inventar estados.
- Para cada experiência, o artefato relaciona as necessidades conceituais de dados/recursos da API e os papéis/condições que as justificam. Necessidades dos módulos permanecem isoladas pelas permissões correspondentes.
- Os recursos descritos são necessidades de produto, não contratos: não há endpoints, métodos HTTP, schemas, payloads ou códigos de resposta.
- As decisões que dependem do proprietário estão marcadas como propostas ou pendentes; somente escolhas explicitamente confirmadas constam como aprovadas.
- A navegação não introduz capacidades fora dos requisitos e do escopo do MVP, nem contorna a autorização no backend ou a fronteira API-first aprovada.
- O proprietário revisou e aprovou o artefato consolidado; o resultado e as pendências remanescentes estão registrados no log de decisões.

## Etapas

### Etapa 01.03 — Mapear navegação, fronteiras de acesso e necessidades da API

- **Estágio AI DLC:** CONSTRUCTION.
- **Objetivo:** produzir um mapa revisável das rotas, conexões, redirecionamentos, limites de acesso e recursos/dados necessários por experiência, papel, estado e permissão.
- **Itens de trabalho:**
  1. Conferir IDs, nomes, agrupamentos e propósitos no inventário 01.02 aprovado.
  2. Propor rotas visíveis na UI e registrar origem, destino, tipo de ligação e condição de redirecionamento.
  3. Classificar cada destino como público ou protegido e explicitar as condições de acesso por papel, autenticação, estado e permissões NEWS/EVENT AGENDA.
  4. Mapear os casos de acesso permitidos, negados e redirecionados, sem transformar “aguardando aprovação” em um estado de conta novo.
  5. Relacionar, por experiência e condição de acesso, as capacidades e os dados conceituais que a UI precisa obter da API.
  6. Apresentar ambiguidades e decisões de rota/acesso ao proprietário, registrar somente as escolhas confirmadas e consolidar o artefato em docs/ux-ui/route-resource-map.md.
- **Dependências:** etapa 01.01 concluída; etapa 01.02 concluída com inventário revisado e aprovado; fontes aprovadas de INCEPTION e arquitetura disponíveis; etapa 01.03 presente no roadmap.
- **Critérios de aceite:** cumprir todos os critérios de aceite desta especificação.
- **Validação:** conferir cobertura exata dos IDs contra o inventário final aprovado; percorrer links e redirecionamentos para destinos consistentes; revisar a matriz para cada combinação de papel, estado e permissões; comparar as capacidades com os requisitos, papéis, escopo e arquitetura aprovados; confirmar que a UI não contorna a API; buscar e remover detalhes que constituam contrato formal; verificar links documentais; apresentar o mapa completo ao proprietário e registrar aprovação ou pendências no docs/decision-log.md.
- **Status:** Waiting — execução iniciada em 2026-11-17 e pausada aguardando respostas do proprietário ao questionário. A etapa 01.02 está concluída e aprovada; nenhuma decisão de rota ou necessidade de dados foi registrada como aprovada ainda. Nenhum mapa foi consolidado.

## Parâmetros da solicitação de execução

- **IDs das etapas ou quantidade a executar:** informados pelo usuário por solicitação de execução; esta especificação contém somente a etapa 01.03.
- **Máximo de subagentes simultâneos:** informado pelo usuário; 0 significa nenhum. Recomendação: 0 para preservar a revisão direta do proprietário das decisões de navegação e acesso.
- **Condição de parada:** parar após a etapa 01.03 e sua aprovação. Não iniciar automaticamente as etapas 01.04–01.06 nem fases seguintes.
