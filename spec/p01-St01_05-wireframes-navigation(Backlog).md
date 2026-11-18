# Especificação: Fase 01 — Wireframes e diagramas de navegação

## Referência ao roadmap

- **Fase:** 01 — Arquitetura de informação UX/UI antes da fundação técnica.
- **Etapa coberta:** 01.05 — Produzir wireframes e diagramas de navegação cobrindo os estados loading, queued, running, partial, failed, cancelled, empty, cache-hit e session-expired.
- **Limite:** esta especificação cobre somente a etapa 01.05. A etapa 01.06 consolida os artefatos de design e obtém aprovação separada dos designs detalhados antes da implementação das interfaces nas fases 10–14.
- **Roadmap:** [Fase 01](../docs/project-roadmap.md).

## Mapeamento aos estágios AI DLC

- **INCEPTION — Excluído:** problema, objetivo, usuários, requisitos e escopo do MVP já foram aprovados e são entradas desta etapa.
- **CONSTRUCTION — Incluído:** produzir e validar artefatos de design UX/UI. Esta etapa não implementa telas, código, contratos de API ou comportamento de backend.
- **OPERATIONS — Excluído:** implantação, monitoramento e evolução de produção são de responsabilidade humana e não fazem parte desta etapa.
- **Execução de tarefas de OPERATIONS pelo Codex:** não permitida.

## Objetivo

Produzir wireframes revisáveis e diagramas de navegação para as experiências aprovadas no inventário, aplicando os padrões de interação e identidade visual aprovados. Representar os nove estados previstos no roadmap sem confundir estados de apresentação com contratos ou estados técnicos de backend.

## Escopo

- **Inclui:**
  - Usar como base o inventário final aprovado da etapa 01.02, o mapa de rotas e recursos aprovado na etapa 01.03, os padrões e rótulos aprovados na etapa 01.04 e a identidade visual aprovada na etapa 01.01.
  - Produzir wireframes para as 11 telas autônomas do inventário. Representar Cadastro e Recuperação de senha como experiências agrupadas no Login, e Sem permissão para o módulo como estado embutido no Painel do usuário; preservar os IDs rastreáveis sem criar páginas independentes.
  - Mostrar uma composição desktop e uma móvel para cada tela autônoma. Usar os padrões de tablet da etapa 01.04 e incluir variação adicional quando a mudança de disposição ou interação não puder ser entendida pelas composições desktop e móvel.
  - Criar uma matriz de cobertura que associe cada um dos nove estados às telas e aos fluxos em que se aplica, com exemplos de NEWS e EVENT AGENDA quando suas diferenças de conteúdo ou resultado forem relevantes.
  - Produzir diagramas para os caminhos públicos, de autenticação, Consumer/User e Administrator, além dos fluxos de busca e das transições entre estados. Reutilizar as rotas, condições de acesso e relações entre experiências já aprovadas na etapa 01.03.
  - Revisar os artefatos com o proprietário, registrar escolhas e questões pendentes e manter o pacote identificado como rascunho até sua aprovação nesta etapa e sua consolidação na etapa 01.06.
- **Não inclui:**
  - Alterar IDs, agrupamentos, rotas, fronteiras de acesso, redirecionamentos ou necessidades de recursos de API definidos nas etapas anteriores. Uma lacuna ou conflito deve ser registrado e encaminhado à etapa correspondente, sem resolução implícita no desenho.
  - Definir novos rótulos, comportamento responsivo, controles de teclado, componentes, campos, filtros ou interações de mapa; estes devem seguir a especificação aprovada na etapa 01.04.
  - Definir endpoints, payloads, schemas, percentuais ou estimativas de progresso, contratos de API, máquina de estados técnica ou comportamento interno de jobs e cache.
  - Implementar telas, frontend, API, worker ou serviços; reabrir decisões aprovadas; ou executar tarefas de OPERATIONS.

## Entradas e invariantes aprovadas

- [Identidade visual](../docs/visual-identity/README.md) fornece paleta, tipografia, ícones e direção visual aprovada; esta etapa não reabre essas decisões.
- O inventário [Step 01.02](../docs/ux-ui/screen-inventory.md) determina os IDs, a contagem de 11 telas autônomas e as experiências agrupadas ou embutidas. A revisão final do proprietário foi aprovada em 2026-11-17.
- O artefato da [Etapa 01.03](../docs/ux-ui/route-resource-map.md) é a fonte aprovada para rotas, fluxos, redirects, fronteiras de acesso e necessidades conceituais da API.
- O artefato da [Etapa 01.04](../docs/ux-ui/screen-interactions.md) é a fonte aprovada para rótulos pt-BR/en-US, padrões responsivos e de teclado, componentes, formulários, filtros e mapa.
- [Requisitos](../docs/ai-dlc/inception/requirements.md), [Usuários e Papéis](../docs/ai-dlc/inception/users-and-roles.md), [Escopo do MVP](../docs/ai-dlc/inception/mvp-scope.md) e [arquitetura](../docs/ai-dlc/architecture/architecture.md) continuam autoritativos para regras de produto, acesso e fronteiras técnicas.
- A interface deve diferenciar ausência de resultados verificados de descoberta incompleta (RNF-004). Ao representar cache-hit, deve respeitar a revalidação e não sugerir novo consumo de tokens DeepSeek ou nova chamada de provedor quando o conteúdo for integralmente servido do cache (RNF-005).
- Os nove nomes de estado são estados de experiência previstos pelo roadmap. A representação visual não determina uma máquina técnica de estados nem altera os detalhes de implementação definidos em fases posteriores.

## Cobertura dos estados

| Estado previsto no roadmap | Contextos mínimos a representar | Limite de interpretação |
| --- | --- | --- |
| **loading** | Carregamento inicial de uma experiência protegida e carregamento de dados/resultados nas experiências em que se aplica. | Não equivale a job aceito ou em execução; seguir os estados de tela definidos na etapa 01.04. |
| **queued** | Busca NEWS e busca EVENT AGENDA depois da submissão e antes do processamento. | Não inventar prazo, posição na fila ou percentual de progresso. |
| **running** | Busca NEWS e busca EVENT AGENDA durante o processamento. | Mostrar somente progresso e ações suportados pelas entradas aprovadas; registrar como pendente qualquer detalhe sem decisão. |
| **partial** | Busca NEWS e EVENT AGENDA com resultados utilizáveis e descoberta incompleta. | Identificar a incompletude; não afirmar que zero resultados existem nem apresentar como resultado completo. |
| **failed** | Busca NEWS e EVENT AGENDA que terminou sem resultados utilizáveis por falha. | Distinguir de partial e empty; não sugerir ausência de conteúdo como se a busca tivesse sido concluída. |
| **cancelled** | Busca NEWS e EVENT AGENDA após solicitação e conclusão do cancelamento. | Não pressupor se resultados parciais permanecem disponíveis ou quais controles iniciam/cancelam a ação; aplicar somente decisões aprovadas e registrar lacunas. |
| **empty** | Busca NEWS e EVENT AGENDA concluída sem resultados verificados elegíveis; representar listas administrativas vazias se esse caso estiver coberto pelos padrões aprovados. | Expressar ausência de resultados verificados para a consulta, sem afirmar que não existem notícias ou eventos. |
| **cache-hit** | Busca NEWS e EVENT AGENDA atendida por resultados em cache após as verificações atuais aplicáveis. | Não sugerir nova chamada de busca ou nova geração de IA quando não ocorreu; manter visíveis a consulta e os filtros correspondentes. |
| **session-expired** | Acesso expirado a experiências protegidas, com destino ao fluxo de autenticação definido na etapa 01.03. | Não mostrar conteúdo protegido com sessão expirada nem presumir preservação de formulário ou destino pós-login que não conste nas decisões aprovadas. |

A matriz deve indicar quais telas e combinações de estado foram desenhadas, quais estados compartilham um componente visual e quais estados não se aplicam a cada experiência. Reuso visual não pode apagar diferenças entre partial, failed e empty, nem entre loading e queued/running.

## Protocolo de trabalho com o proprietário

1. Confirmar que as dependências 01.02–01.04 e a identidade visual 01.01 foram concluídas e aprovadas. Se alguma estiver pendente ou se os artefatos divergirem, interromper o trabalho dependente e registrar a lacuna.
2. Preparar um inventário de wireframes e diagramas baseado nos IDs, rotas, estados de acesso, rótulos e padrões já aprovados. Para cada composição, indicar a tela, o viewport, os estados cobertos e as fontes usadas.
3. Apresentar propostas visuais para revisão do proprietário. Registrar decisão, justificativa fornecida, data, status e revisões solicitadas; não inferir aprovação por silêncio.
4. Se uma escolha visual depender de uma regra ainda não aprovada — por exemplo, destino após sessão expirada, ação de cancelamento, conteúdo parcial após cancelamento ou disponibilidade de progresso — registrar a pergunta e pausar somente a parte afetada.
5. Consolidar os artefatos revisados, solicitar ao proprietário aprovação explícita dos wireframes e diagramas desta etapa e aplicar as revisões acordadas. Essa aprovação não substitui a aprovação final do pacote de designs detalhados prevista na etapa 01.06.

## Critérios de aceite

- A matriz de cobertura preserva os 14 IDs aprovados, 11 telas autônomas, Cadastro e Recuperação agrupados em Login e Sem permissão embutido no Painel do usuário; não cria, remove ou duplica experiências.
- Cada tela autônoma tem composição desktop e móvel, e as mudanças relevantes de tablet seguem os padrões aprovados da etapa 01.04.
- Os wireframes e diagramas representam explicitamente loading, queued, running, partial, failed, cancelled, empty, cache-hit e session-expired em seus contextos aplicáveis, abrangendo os fluxos de NEWS e EVENT AGENDA.
- Os diagramas refletem as rotas, fronteiras de acesso e redirecionamentos aprovados em 01.03, distinguem os caminhos públicos, de Consumer/User e Administrator e indicam as transições de estados sem criar rotas ou regras novas.
- Partial, failed e empty são visual e semanticamente distinguíveis. Cache-hit respeita a atribuição de uso aprovada. Session-expired não exibe conteúdo protegido e segue somente o fluxo de autenticação aprovado.
- Rótulos, componentes, acessibilidade de teclado e comportamento responsivo seguem 01.04; a aplicação visual segue a identidade aprovada em 01.01. Estados e mensagens relevantes não dependem somente de cor.
- Nenhum wireframe apresenta como definidos contratos de API, dados de progresso, comportamento de backend ou decisões técnicas ainda pendentes. Lacunas são identificadas e encaminhadas à fonte ou etapa apropriada.
- Os artefatos e fontes são navegáveis a partir de `docs/ux-ui/README.md`, as decisões e limitações estão registradas no log de decisões e o pacote permanece explicitamente como rascunho até a aprovação prevista em 01.06.
- O proprietário revisou e aprovou explicitamente os wireframes e diagramas desta etapa; mudanças solicitadas foram incorporadas ou registradas como pendentes para a revisão final na etapa 01.06.

## Etapas

### Etapa 01.05 — Produzir wireframes e diagramas de navegação com estados

- **Estágio AI DLC:** CONSTRUCTION.
- **Objetivo:** transformar o inventário, o mapa de rotas e os padrões de interação aprovados em wireframes responsivos e diagramas de navegação/estados revisáveis.
- **Itens de trabalho:**
  1. Conferir as aprovações e dependências das etapas 01.01–01.04; reunir os artefatos de identidade visual, inventário, rotas/recursos e interações.
  2. Montar a matriz de telas, viewports e nove estados; sinalizar lacunas de produto ou dependências ainda sem decisão.
  3. Desenhar as experiências autônomas, agrupadas e embutidas em layouts desktop e móvel, aplicando os padrões responsivos aprovados.
  4. Desenhar as variações de estado aplicáveis às buscas NEWS/EVENT AGENDA e às experiências protegidas; criar diagramas de navegação e transição consistentes com as rotas aprovadas.
  5. Revisar acessibilidade, rótulos, semântica de estado, identidade visual e consistência dos caminhos; apresentar os rascunhos ao proprietário e aplicar as revisões acordadas.
  6. Publicar o pacote revisado como rascunho em `docs/ux-ui/wireframes/` e `docs/ux-ui/navigation-diagrams.md`, atualizar `docs/ux-ui/README.md` e registrar o resultado e as pendências em `docs/decision-log.md`.
  7. Apresentar os wireframes e diagramas ao proprietário para aprovação explícita da etapa; manter a aprovação final dos designs detalhados para a etapa 01.06.
- **Dependências:** etapas 01.01 concluída e identidade visual aprovada; etapa 01.02 concluída com o inventário consolidado aprovado pelo proprietário; etapa 01.03 concluída com mapa de rotas/recursos aprovado; etapa 01.04 concluída com padrões e rótulos aprovados; requisitos, papéis, escopo e arquitetura aprovados. A especificação de uma etapa não equivale à conclusão de sua execução.
- **Critérios de aceite:** cumprir todos os critérios de aceite desta especificação, incluindo aprovação explícita do proprietário para os artefatos da etapa 01.05. A aprovação final dos designs detalhados permanece para a etapa 01.06.
- **Validação:** conferir cobertura dos 14 IDs/11 telas e dos nove estados; percorrer diagramas e comparar cada rota e condição de acesso com 01.03; comparar rótulos, viewports, teclado e componentes com 01.04; revisar a distinção de partial/failed/empty e o tratamento de cache/session com os requisitos; abrir e revisar os arquivos; verificar links documentais e registrar feedback, aprovação do Step 01.05 e pendências no log de decisões. Não executar testes de software nem validação de implementação.
- **Artefatos esperados:** `docs/ux-ui/wireframes/`, `docs/ux-ui/navigation-diagrams.md` e atualização do índice `docs/ux-ui/README.md`.
- **Status:** Backlog — especificação criada; execução não iniciada. A etapa 01.02 foi aprovada; a execução aguarda as aprovações das etapas 01.03 e 01.04. A aprovação final dos designs detalhados permanece reservada à etapa 01.06.

## Parâmetros da solicitação de execução

- **IDs das etapas ou quantidade a executar:** informados pelo usuário em futura solicitação; esta especificação contém somente a etapa 01.05.
- **Máximo de subagentes simultâneos:** informado pelo usuário em futura solicitação; `0` significa nenhum. Recomenda-se `0` para manter o proprietário diretamente envolvido nas decisões visuais e de estado.
- **Condição de parada:** parar após a aprovação dos wireframes e diagramas da etapa 01.05. Não iniciar automaticamente a etapa 01.06 ou as fases 10–14.
