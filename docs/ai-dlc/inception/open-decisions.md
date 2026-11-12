# Registro de decisões INCEPTION — OD-01 a OD-14

> **STATUS: RESOLVIDO — decisões de produto aprovadas pelo proprietário em 2026-11-10.**
> Este registro reconcilia questões numeradas no baseline de requisitos. Não é uma
> aprovação de arquitetura. Detalhes técnicos indicados como diferidos pertencem a
> CONSTRUCTION; OPERATIONS continua sob responsabilidade humana.

**Fonte das decisões:** aprovação explícita do proprietário em 2026-11-10,
registrada no [decision log](../../decision-log.md). Cada linha identifica o
conjunto de decisão aprovado e aponta para os requisitos e documentos de escopo
ou papéis que o formalizam.

## Referências

- [Requirements](requirements.md) — IDs RF/RNF preservados e atualizados.
- [Users and Roles](users-and-roles.md) — contas, papéis e permissões.
- [Product Objective](product-objective.md) — objetivo aprovado.
- [MVP Scope](mvp-scope.md) — limites do MVP aprovados.
- [Problem Definition](problem-definition.md) — definição aprovada e imutável.

## Resoluções

| ID anterior | Conjunto aprovado | Resolução | Estado |
|---|---|---|---|
| **OD-01 — Categoria e texto livre** | Decisão 2 | Categoria específica intersecta/restringe o texto livre. All/Todos remove a restrição de categoria; texto livre continua pesquisando entre categorias. Texto vazio aplica somente a categoria selecionada. | Resolvido em INCEPTION; ver RF-003. |
| **OD-02 — Catálogo e All** | Decisão 2 | Catálogo inicial: Politics, Economy, Technology, Sports, Agribusiness, Health, Education, Science, Culture, Environment e Other; All/Todos é opção sem filtro de categoria. | Resolvido em INCEPTION; ver RF-003. |
| **OD-03 — Geografia, limites e idiomas** | Decisão 3 | Mapa mundial clicável, níveis mundo > continente > país > estado/região > cidade > bairro, seleção em qualquer nível, sub-regiões elegíveis e suporte de UI/conteúdo conciso em pt-BR e en-US. Fontes e métodos de mapa/geocodificação ficam para CONSTRUCTION. | Resolvido em INCEPTION; implementação geográfica diferida para CONSTRUCTION. |
| **OD-04 — Tempo e timestamp de NEWS** | Decisão 4 | Janela exata móvel de 24 horas anterior à execução da consulta, baseada no instante original de publicação verificado; comparação normalizada em UTC. Timestamp de atualização e ocorrência não substituem publicação original. Exibição usa fuso horário relevante do evento/local. | Resolvido em INCEPTION; ambiguidades de fonte são ressalvas de validação, não fatos presumidos. |
| **OD-05 — Relevância, qualidade e deduplicação** | Decisão 6 | NEWS prioriza geografia/tópico verificados, significância/impacto direto, confiabilidade da fonte e recência de publicação. Diversidade geográfica é aplicada quando apropriada sem sobrepor elegibilidade ou itens claramente mais relevantes. Cobertura do mesmo evento vira um resultado, preferindo a melhor fonte original verificada. | Princípios resolvidos; pesos e algoritmos diferidos para CONSTRUCTION; ver RF-006 e RF-009. |
| **OD-06 — Intervalo e eventos em andamento** | Decisão 4 | EVENT AGENDA exige início e fim explícitos, datas inclusivas no fuso local do evento. Um evento qualifica se sua duração real se sobrepõe ao intervalo e ele ainda está em andamento ou é futuro; evento concluído não qualifica. Data de anúncio não substitui data de ocorrência. | Resolvido em INCEPTION; data sem horário, incerteza de limite e horário local ambíguo são ressalvas de validação. |
| **OD-07 — Ordenação de eventos** | Decisão 7 | EVENT AGENDA ordena por data/hora inicial em ordem cronológica ascendente por padrão e oferece ordenação por relevância. | Resolvido em INCEPTION; ver RF-016. |
| **OD-08 — Evidência e número de fontes** | Decisão 5 | NEWS pode usar uma fonte jornalística identificável confiável ou fonte primária/oficial autoritativa, desde que tempo original, fatos usados, URL original e relação geográfica sejam verificáveis. EVENT pode usar uma fonte oficial verificável do organizador; sem fonte autoritativa, exige ao menos duas fontes independentes confiáveis que sustentem ocorrência, data/horário e venue aplicável. | Limiares de aceitação resolvidos; heurísticas de detecção diferidas para CONSTRUCTION; ver RF-004, RF-005 e RF-012. |
| **OD-09 — Meta de desempenho** | Decisão 8 | Meta inicial de validação: p95 ≤120 segundos para até 10 resultados e até cinco usuários concorrentes, em condições normais de teste, medida separadamente por NEWS e EVENT AGENDA. Não é SLA nem desempenho já medido. | Resolvido em INCEPTION; ver RNF-003. |
| **OD-10 — Cache e fallback** | Decisão 8 | Cache de busca/resultados por 10 minutos, com revalidação temporal/elegibilidade, separação por idioma/filtros, controle de acesso, atribuição correta de chamadas reais e sem contabilizar cache hit como nova geração DeepSeek. Tavily é fallback em erro/indisponibilidade Serper; falha parcial é informada. | Política aprovada; desenho técnico diferido para CONSTRUCTION; ver RNF-005, RNF-006, RF-018 e RF-027. |
| **OD-11 — Contagem padrão** | Decisão 7 | NEWS e EVENT AGENDA oferecem máximos 5, 10, 15 e 20 e usam 10 como padrão. | Resolvido em INCEPTION; ver RF-008 e RF-016. |
| **OD-12 — Eventos online/híbridos** | Decisão 3 | Eventos físicos e híbridos exigem venue físico verificado dentro da área selecionada. Eventos totalmente online só qualificam na seleção WORLD. | Resolvido em INCEPTION; ver RF-015. |
| **OD-13 — Conteúdo e concisão** | Decisão 7 | NEWS mostra headline fundamentado, teaser de aproximadamente duas linhas e descrição curta distinta, fonte e URL original verificado. EVENT AGENDA mostra nome, data/hora quando disponível, local real, descrição breve e fonte original. Não há contagem fixa de caracteres nem preenchimento inventado; truncamento visual é escolha de UI em CONSTRUCTION. | Resolvido em INCEPTION; ver RF-010 e RF-017. |
| **OD-14 — Limite de aprovação documental** | Aprovações anteriores e decisões 1–8 | Problem Definition, Product Objective, Users and Roles, Requirements e MVP Scope têm aprovações limitadas aos respectivos documentos. O requisito principal separado não é criado por inferência; RP-01 recebeu aprovação explícita em 2026-11-11 e consta em [Project Context](../../context.md). Arquitetura e implementação não estão aprovadas e seguem para CONSTRUCTION; OPERATIONS continua humana. | Resolvido como fronteira documental; não é requisito de produto. |

## Índice de rastreabilidade

As decisões-fonte são as oito decisões explicitamente aprovadas pelo proprietário em 2026-11-10 e registradas em [decision-log.md](../../decision-log.md). Esta matriz liga cada ID anterior aos requisitos atuais e aos documentos autoritativos de escopo/papéis:

| OD | Decisão aprovada | Requisitos e documentos autoritativos |
|---|---|---|
| OD-01 | Decisão 2 | [RF-003](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-02 | Decisão 2 | [RF-003](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-03 | Decisão 3 | [RF-002 e RF-024](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-04 | Decisão 4 | [RF-007](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-05 | Decisão 6 | [RF-006, RF-009 e RF-028](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-06 | Decisão 4 | [RF-013 e RF-014](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-07 | Decisão 7 | [RF-016](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-08 | Decisão 5 | [RF-004, RF-005 e RF-012](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-09 | Decisão 8 | [RNF-003](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-10 | Decisão 8 | [RNF-005 e RNF-006, RF-018 e RF-027](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-11 | Decisão 7 | [RF-008 e RF-016](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-12 | Decisão 3 | [RF-015](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-13 | Decisão 7 | [RF-010, RF-017 e RF-018](requirements.md); [MVP Scope](mvp-scope.md) |
| OD-14 | Decisões 1–8 e aprovações anteriores | [Problem Definition](problem-definition.md), [Product Objective](product-objective.md), [Users and Roles](users-and-roles.md), [Requirements](requirements.md), [MVP Scope](mvp-scope.md), [Project Context](../../context.md) |

## Ressalvas de validação e itens diferidos

- Fontes que apresentam somente uma data não autorizam inferir horário ou duração. Se isso impedir comprovar sobreposição, estado em andamento/futuro ou limite temporal, o resultado não pode afirmar esses fatos como verificados; a limitação deve ser informada.
- Horários locais ambíguos, incertezas de fronteira e dados ausentes devem ser tratados sem fabricação e sem ampliar silenciosamente os parâmetros da consulta.
- A escolha de fontes de dados geográficos/mapas, heurísticas de evidência, algoritmos/pesos de ranking e deduplicação, desenho do cache e mecânica de truncamento são decisões de CONSTRUCTION, não ODs de produto.
- A meta de desempenho é somente um alvo inicial de validação; não foi medida neste trabalho e não oferece garantia ou SLA.
