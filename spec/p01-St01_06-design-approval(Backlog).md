# Especificação: Fase 01 — Entrega e aprovação dos designs de tela

## Referência ao roadmap

- **Fase:** 01 — Arquitetura de informação UX/UI antes da fundação técnica.
- **Etapa coberta:** 01.06 — entregar artefatos de design e obter aprovação explícita dos designs detalhados antes da implementação das interfaces dependentes nas Fases 10–14.
- **Limite:** esta especificação cobre somente a etapa 01.06. Ela consolida e apresenta os artefatos produzidos nas etapas 01.01–01.05; não reexecuta essas etapas nem implementa as interfaces das Fases 10–14.
- **Roadmap:** [Fase 01](../docs/project-roadmap.md).

## Mapeamento aos estágios AI DLC

- **INCEPTION — excluído:** problema, objetivo, requisitos, papéis, escopo e arquitetura aplicável já estão aprovados e são entradas desta etapa.
- **CONSTRUCTION — incluído:** consolidar, revisar, apresentar e registrar a aprovação do pacote documental de design. O trabalho é somente documental: não cria código, contratos formais ou comportamento de backend.
- **OPERATIONS — excluído:** implantação, monitoramento e evolução em produção são de responsabilidade humana e não fazem parte desta etapa.
- **Execução de tarefas de OPERATIONS pelo Codex:** não permitida.

## Objetivo

Entregar ao proprietário um pacote rastreável dos designs detalhados das experiências aprovadas, conferir sua consistência com os artefatos e requisitos aprovados e registrar uma aprovação explícita que funcione como pré-requisito para implementar as interfaces dependentes nas Fases 10–14.

## Escopo

- **Inclui:**
  - Criar `docs/ux-ui/design-package.md` como índice e registro de revisão, com links para os artefatos de origem, cobertura dos IDs finais do inventário, estado de revisão, feedback e decisão do proprietário.
  - Consolidar, sem duplicar o conteúdo de origem, a identidade visual, o inventário de telas, o mapa de rotas/recursos, os padrões de interação e os wireframes/diagramas de navegação.
  - Conferir que cada experiência e cada ID do inventário aprovado estejam ligados aos artefatos detalhados aplicáveis, preservando relações agrupadas ou embutidas.
  - Conferir a cobertura dos estados especificados na etapa 01.05 e registrar aplicabilidade ou lacunas sem presumir que todo estado se aplica a toda tela.
  - Apresentar o pacote para revisão do proprietário, incorporar ajustes de apresentação solicitados e registrar aprovação, pedidos de revisão e limitações.
  - Manter links e referências coerentes nos índices documentais e registrar o resultado em `docs/decision-log.md`.
- **Não inclui:**
  - Alterar requisitos, papéis, permissões, escopo do MVP, arquitetura ou decisões aprovadas nas etapas anteriores.
  - Criar novas experiências, rotas, recursos, contratos de API ou regras de produto.
  - Substituir ou reabrir silenciosamente decisões dos artefatos aprovados em 01.01–01.05. Se a revisão revelar uma mudança substantiva, registrar a pendência e encaminhá-la à etapa ou fonte responsável; atualizar este pacote depois da resolução.
  - Implementar telas, componentes, serviços, APIs ou código das Fases 10–14.
  - Executar implantação, monitoramento ou qualquer tarefa de OPERATIONS.

## Entradas e dependências

A execução desta especificação aguarda a conclusão e aprovação explícita de todas as entradas abaixo:

- Etapa 01.01: pacote de identidade visual aprovado em [`docs/visual-identity/README.md`](../docs/visual-identity/README.md).
- Etapa 01.02: inventário final aprovado em [`docs/ux-ui/screen-inventory.md`](../docs/ux-ui/screen-inventory.md).
- Etapa 01.03: [especificação de rotas e recursos](<p01-St01_03-route-resource-map(Backlog).md>), com saída prevista em `docs/ux-ui/route-resource-map.md`; o artefato final aprovado é pré-requisito.
- Etapa 01.04: [especificação de interações e padrões de tela](<p01-St01_04-screen-interactions(Backlog).md>), com saída prevista em `docs/ux-ui/screen-interactions.md`; o artefato final aprovado é pré-requisito.
- Etapa 01.05: wireframes e diagramas de navegação aprovados, no caminho definido pela especificação dessa etapa.
- Fontes aprovadas de INCEPTION e arquitetura, incluindo [requisitos](../docs/ai-dlc/inception/requirements.md), [usuários e papéis](../docs/ai-dlc/inception/users-and-roles.md), [escopo do MVP](../docs/ai-dlc/inception/mvp-scope.md) e [arquitetura](../docs/ai-dlc/architecture/architecture.md).

Preparar esta especificação não conclui nem aprova essas dependências. Se algum artefato estiver ausente, em revisão, ou tiver aprovação pendente, a execução de 01.06 deve aguardar.

## Regras de consolidação e aprovação

1. Usar o inventário final aprovado como fonte dos IDs, nomes e relações entre experiências. Não tratar as 14 experiências candidatas como 14 páginas independentes quando o inventário aprovado as agrupar ou incorporar.
2. Usar os documentos de origem como fontes autoritativas de seus respectivos conteúdos. O pacote deve resumir cobertura e apontar para as fontes; não copiar tabelas ou decisões completas para outro local.
3. Manter rastreabilidade por ID entre inventário, acesso/rotas, interações e wireframes/diagramas. Para cada estado de design, apontar a tela ou fluxo aplicável conforme a etapa 01.05.
4. Comparar os artefatos entre si e com os requisitos, papéis, permissões, escopo e arquitetura aprovados. Registrar inconsistências ou lacunas como pendentes; não resolvê-las por inferência.
5. Apresentar ao proprietário o pacote completo e colher uma decisão explícita. Uma aprovação em lote só vale se identificar claramente todos os IDs e artefatos abrangidos. Silêncio, revisão parcial ou aprovação anterior de identidade visual não aprovam os designs detalhados como pacote.
6. Registrar, para cada ID ou grupo aprovado, o estado da revisão, a decisão do proprietário, a data e eventuais ressalvas. Estados possíveis incluem **Pendente**, **Revisão solicitada** e **Aprovado**.
7. Se o proprietário pedir uma mudança substantiva em uma decisão ou artefato anterior, preservar o estado pendente, indicar a fonte/etapa responsável e aguardar sua resolução antes de declarar o pacote aprovado.
8. A aprovação deste pacote não autoriza implementação por si só. As Fases 10–14 continuam sujeitas às solicitações de execução e aos limites definidos pelo processo do projeto.

## Critérios de aceite

- `docs/ux-ui/design-package.md` identifica a versão dos artefatos de origem e fornece links funcionais para eles.
- O pacote cobre exatamente todos os IDs, experiências e relações do inventário final aprovado, sem criar, excluir ou duplicar experiências.
- Cada ID está rastreado aos artefatos detalhados aplicáveis de rotas/acesso, interações e design visual; agrupamentos e experiências incorporadas estão visíveis na rastreabilidade.
- Os estados de carregamento, fila, execução, parcial, falha, cancelamento, vazio, cache-hit e sessão expirada definidos na etapa 01.05 estão localizados no fluxo aplicável ou marcados como pendência, sem exigir que todos apareçam em todas as telas.
- A revisão de consistência não encontra conflito não registrado com requisitos, papéis, permissões, escopo do MVP, arquitetura ou decisões aprovadas nas etapas anteriores.
- Toda lacuna ou conflito remanescente aparece como pendente, com referência à decisão ou artefato necessário para resolvê-lo; nenhuma aprovação é inferida.
- O proprietário revisou explicitamente os designs detalhados e o pacote registra a decisão para todos os IDs cobertos, individualmente ou em lote. A etapa só pode ser concluída quando todos estiverem aprovados e as ressalvas forem aceitas explicitamente; nenhum item pode permanecer pendente ou com revisão solicitada.
- A decisão e o resultado estão registrados em `docs/decision-log.md`, e os índices documentais apontam para a spec e para o pacote entregue.
- Nenhuma interface, contrato formal, API ou código foi implementado nesta etapa.

## Etapas

### Etapa 01.06 — Entregar e aprovar o pacote de designs detalhados

- **Estágio AI DLC:** CONSTRUCTION.
- **Objetivo:** consolidar os artefatos aprovados de UX/UI em uma entrega rastreável, obter revisão explícita do proprietário e estabelecer o gate de design para as interfaces dependentes das Fases 10–14.
- **Itens de trabalho:**
  1. Confirmar a conclusão e aprovação das dependências 01.01–01.05 e conferir que os links e caminhos de origem estão disponíveis.
  2. Criar `docs/ux-ui/design-package.md` com índice dos artefatos, matriz de rastreabilidade por ID, estados cobertos, pendências e campos de revisão/decisão do proprietário.
  3. Conferir cobertura e consistência cruzada do pacote contra o inventário final, o mapa de rotas/recursos, as interações, os wireframes/diagramas e as fontes aprovadas de produto e arquitetura.
  4. Apresentar o pacote completo ao proprietário. Registrar aprovação ou pedidos de revisão por ID/artefato; encaminhar mudanças substantivas às fontes/etapas responsáveis e reapresentar o pacote após a resolução.
  5. Atualizar os índices documentais e registrar a decisão final, a data, o escopo aprovado e as ressalvas em `docs/decision-log.md`.
- **Dependências:** etapas 01.01, 01.02, 01.03, 01.04 e 01.05 concluídas e aprovadas; requisitos, usuários e papéis, escopo do MVP e arquitetura aprovados; Step 01.06 presente no roadmap.
- **Critérios de aceite:** cumprir todos os critérios de aceite desta especificação, incluindo aprovação explícita de todos os designs detalhados cobertos pelo inventário final.
- **Validação:** verificar links documentais; comparar a matriz de IDs com o inventário aprovado; verificar cobertura aplicável dos estados da etapa 01.05; revisar consistência com os documentos autoritativos; confirmar que lacunas e mudanças substantivas estão identificadas sem alteração silenciosa de decisões; e conferir o registro da decisão do proprietário no pacote e no log.
- **Artefato esperado:** `docs/ux-ui/design-package.md`, além do registro correspondente em `docs/decision-log.md`.
- **Status:** Backlog — especificação criada; execução não iniciada. A execução depende da conclusão e aprovação dos artefatos 01.01–01.05.

## Parâmetros da solicitação de execução

- **IDs das etapas ou quantidade a executar:** informados pelo usuário em futura solicitação; esta especificação contém somente a etapa 01.06.
- **Máximo de subagentes simultâneos:** informado pelo usuário em futura solicitação; `0` significa nenhum. Recomenda-se `0` para manter a revisão e a decisão de design diretamente com o proprietário.
- **Condição de parada:** parar após a entrega e aprovação do pacote 01.06. Não iniciar automaticamente as Fases 10–14 nem executar OPERATIONS.
