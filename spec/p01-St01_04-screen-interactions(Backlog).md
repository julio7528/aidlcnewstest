# Especificação: Fase 01 — Interações e padrões de tela

## Referência ao roadmap

- **Fase:** 01 — Arquitetura de informação UX/UI antes da fundação técnica.
- **Etapa coberta:** 01.04 — Especificar rótulos pt-BR/en-US, padrões responsivos e acessíveis por teclado, componentes compartilhados, formulários, filtros e interações do mapa.
- **Limite:** esta especificação cobre somente a etapa 01.04. A etapa 01.05 produzirá wireframes e diagramas de navegação; a etapa 01.06 reunirá os artefatos de design e obterá aprovação explícita antes das interfaces das fases 10–14.
- **Roadmap:** [Fase 01](../docs/project-roadmap.md).

## Mapeamento aos estágios AI DLC

- **INCEPTION — Excluído:** problema, objetivo, usuários, requisitos, papéis e escopo do MVP já estão aprovados e são entradas desta etapa.
- **CONSTRUCTION — Incluído:** produzir e validar um artefato de especificação de UX/UI. Esta etapa não implementa telas, código, contratos de API ou comportamento de backend.
- **OPERATIONS — Excluído:** implantação, monitoramento e evolução de produção são de responsabilidade humana e não fazem parte desta etapa.
- **Execução de tarefas de OPERATIONS pelo Codex:** não permitida.

## Objetivo

Definir, com aprovação explícita do proprietário, os textos de interface em pt-BR e en-US e os padrões reutilizáveis de responsividade, acessibilidade por teclado, componentes, formulários, filtros e seleção geográfica para as experiências aprovadas no inventário. O resultado deve preparar os wireframes da etapa 01.05 sem introduzir capacidades, regras de produto ou rotas novas.

## Escopo

- **Inclui:**
  - Registrar uma matriz de rastreabilidade entre os IDs aprovados do inventário S01–S14, as experiências agrupadas ou embutidas e os componentes compartilhados que se aplicam a cada uma.
  - Propor e registrar rótulos finais em pt-BR e en-US, incluindo nomes de campos e controles, ações, instruções, texto de ajuda, nomes acessíveis, mensagens de validação e termos consistentes entre telas.
  - Definir padrões responsivos para celular, tablet e desktop, registrando prioridades e mudanças de disposição sem perda de conteúdo, controles ou contexto. Limiares de viewport, se necessários, são uma decisão de design a documentar; não são pressupostos de implementação.
  - Especificar interação por teclado, ordem e visibilidade do foco, ativação de controles, apresentação textual de seleção/estado e comunicação de atualizações dinâmicas. Estados e mensagens não podem depender somente de cor; a validação deve seguir os critérios de acessibilidade aprovados.
  - Definir o catálogo e os padrões de uso dos componentes compartilhados, formulários de conta e administração, filtros de NEWS e EVENT AGENDA e interações do mapa para Consumer/User.
  - Reutilizar a identidade visual e os wireframes estáticos aprovados em [Identidade Visual](../docs/visual-identity/README.md), sem reabrir suas decisões aprovadas. Verificar combinações novas contra os critérios de contraste já adotados.
- **Não inclui:**
  - Alterar requisito, papel, autorização, conteúdo de produto ou capacidade aprovada; decidir política de acesso, rota, link, redirecionamento ou recurso de API (etapa 01.03).
  - Criar wireframes, diagramas de navegação ou especificar os estados completos de carregamento, fila, execução, parcial, falha, cancelamento, vazio, cache-hit e sessão expirada (etapa 01.05).
  - Aprovar os designs detalhados finais da fase ou implementar interfaces, contratos, serviços ou código (etapa 01.06 e fases 10–14, sujeitas às aprovações previstas no roadmap).
  - Definir fontes de dados cartográficos, geocodificação, cobertura, limites administrativos ou regras de busca além dos requisitos aprovados.

## Entradas e invariantes aprovadas

- [Requisitos aprovados](../docs/ai-dlc/inception/requirements.md), [Usuários e Papéis](../docs/ai-dlc/inception/users-and-roles.md), [Escopo do MVP](../docs/ai-dlc/inception/mvp-scope.md) e [arquitetura aprovada](../docs/ai-dlc/architecture/architecture.md) são fontes de verdade para comportamento e limites do produto.
- A execução depende da revisão e aprovação final do inventário de telas da etapa 01.02 e da conclusão da etapa 01.03. O inventário e o mapa de rotas/dados aprovados delimitam quais experiências, estados de conta e permissões devem aparecer em cada contexto.
- A UI e o conteúdo conciso gerado suportam pt-BR e en-US, e o conteúdo acompanha o idioma selecionado na interface. A descoberta pode usar fontes públicas em outros idiomas.
- NEWS e EVENT AGENDA permanecem experiências independentes. Ambas usam a hierarquia geográfica mundo > continente > país > estado/região > cidade > bairro e permitem encerrar a seleção em qualquer nível.
- As categorias disponíveis são Politics, Economy, Technology, Sports, Agribusiness, Health, Education, Science, Culture, Environment e Other, além de All/Todos. Uma categoria específica intersecta com tópico livre; All/Todos remove somente a restrição de categoria, mantendo o tópico, quando preenchido.
- A quantidade de resultados é 5, 10, 15 ou 20, com padrão 10. NEWS mantém sua janela móvel aprovada de 24 horas; a interface não a converte em um filtro de data escolhido pelo usuário.
- EVENT AGENDA exige datas inicial e final escolhidas explicitamente, inclusivas no fuso local do evento e sem intervalo automático. A ordenação padrão é cronológica crescente, com relevância como alternativa aprovada.
- Cadastro cria apenas Consumer/User e começa inativo, sem permissões NEWS ou EVENT AGENDA. A administração pode ativar/desativar a conta e alterar as permissões dos módulos independentemente.
- A identidade aprovada (cores, tipografia, ícones e wireframes estáticos) é entrada visual, não uma autorização para inferir comportamento que ainda não foi decidido.

## Protocolo de decisões com o proprietário

1. Confirmar que o inventário 01.02 e o mapeamento 01.03 foram aprovados e usar suas IDs, agrupamentos e fronteiras como base. Se houver conflito com requisitos aprovados, registrar a inconsistência e pausar o ponto dependente, sem resolver por suposição.
2. Organizar propostas por componente ou grupo de experiências relacionadas, mostrando pt-BR e en-US lado a lado e indicando em quais IDs cada decisão se aplica. Manter textos ainda não aprovados como **Proposta** ou **Pendente**.
3. Apresentar padrões concretos e implicações responsivas e de teclado para revisão do proprietário. Registrar a escolha, justificativa fornecida, data, estado e exceções por tela. Não inferir aprovação por silêncio.
4. Consolidar o artefato, validar sua consistência com as entradas aprovadas e apresentar o documento completo para revisão final. Só marcar a etapa como concluída depois da aprovação explícita do proprietário; aplicar ajustes solicitados e repetir a validação.

## Critérios de aceite

- O artefato cobre todos os IDs e agrupamentos que constarem no inventário 01.02 finalmente aprovado, sem criar, eliminar ou duplicar experiências.
- Cada texto de interface incluído tem versão coerente em pt-BR e en-US, contexto de uso e estado de aprovação rastreável. Termos compartilhados mantêm tradução consistente; exceções por tela têm justificativa.
- Os padrões responsivos descrevem como cada família de componentes se reorganiza em celular, tablet e desktop e preserva as ações e informações necessárias.
- Os padrões de teclado especificam alcance e ativação de controles, foco perceptível e identificação textual de seleção, estado e mensagens relevantes. Controles do mapa possuem um percurso de seleção utilizável por teclado, sem depender exclusivamente de clique, gesto ou cor.
- Formulários e filtros estão especificados por experiência e respeitam os requisitos aprovados, incluindo campos obrigatórios, ajuda, validação, categoria/tópico, contagem de resultados e datas obrigatórias de EVENT AGENDA. Nenhum valor ou intervalo é selecionado implicitamente quando o requisito exige escolha explícita.
- O catálogo de componentes identifica seus usos e variações sem definir contratos ou implementação; padrões administrativos refletem somente as permissões independentes aprovadas.
- Rótulos, exemplos e comportamentos não apresentam resultados ilustrativos como notícias ou eventos reais nem sugerem acesso não autenticado a recursos protegidos.
- O proprietário revisou e aprovou explicitamente o artefato final, que está ligado ao índice de documentação e ao log de decisões. Até essa aprovação, propostas permanecem identificadas como pendentes.

## Etapas

### Etapa 01.04 — Especificar textos e padrões de interação das telas

- **Estágio AI DLC:** CONSTRUCTION.
- **Objetivo:** produzir uma especificação bilíngue, acessível e rastreável de componentes e padrões de interação para as experiências aprovadas.
- **Itens de trabalho:**
  1. Reunir as decisões aprovadas de inventário, rotas/recursos e identidade visual; registrar dependências e lacunas.
  2. Montar a matriz de IDs, experiências, componentes e usos por tela/estado de conta/permissão.
  3. Propor, revisar e registrar rótulos pt-BR/en-US e padrões de campos, ações, ajuda, validação e componentes compartilhados.
  4. Especificar os padrões responsivos e de teclado, os formulários e filtros das duas experiências, e a seleção/interação geográfica no mapa.
  5. Conferir rastreabilidade e consistência com requisitos, submeter o artefato consolidado ao proprietário e registrar sua decisão final.
- **Dependências:** requisitos, objetivo, papéis, escopo e arquitetura aprovados; etapa 01.01 concluída; inventário 01.02 consolidado e aprovado pelo proprietário; etapa 01.03 concluída e aprovada. A etapa 01.05 consome este artefato e não deve ser iniciada automaticamente por esta especificação.
- **Critérios de aceite:** cumprir todos os critérios de aceite desta especificação e registrar aprovação explícita do proprietário.
- **Validação:** conferir a cobertura de IDs contra o inventário aprovado; auditar a paridade dos rótulos pt-BR/en-US; revisar matrizes de responsividade e teclado; verificar filtros e formulários contra os requisitos; conferir a hierarquia e a alternativa de teclado do mapa; revisar contraste das combinações visuais usadas; abrir os links e registrar pendências e a revisão do proprietário em `docs/decision-log.md`.
- **Artefato esperado:** `docs/ux-ui/screen-interactions.md`.
- **Status:** Backlog — especificação criada; execução não iniciada. A etapa 01.02 foi concluída e aprovada em 2026-11-17; a aprovação do mapeamento 01.03 ainda é dependência para execução.

## Parâmetros da solicitação de execução

- **IDs das etapas ou quantidade a executar:** informados pelo usuário em futura solicitação; esta especificação contém somente a etapa 01.04.
- **Máximo de subagentes simultâneos:** informado pelo usuário em futura solicitação; `0` significa nenhum. Recomenda-se `0` para preservar as decisões explícitas do proprietário sobre conteúdo e interação.
- **Condição de parada:** parar após aprovação do artefato da etapa 01.04; não iniciar automaticamente a etapa 01.05 nem outra fase.
