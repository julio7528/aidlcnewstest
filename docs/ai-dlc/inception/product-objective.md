# Product Objective — GeophNews

> **APPROVED — Product Objective.** Users and roles and MVP scope are approved separately in [Users and Roles](users-and-roles.md) and [MVP Scope](mvp-scope.md). Architecture, roadmap, specifications, implementation, and Operations decisions remain outside this approval.

## Objetivo primário

Facilitar a descoberta, em uma experiência unificada, de notícias cuja publicação original ocorreu nas últimas 24 horas e de eventos públicos em andamento ou futuros no intervalo de datas escolhido pelo usuário, ambos relacionados à geografia selecionada, com informações verificáveis e rastreáveis às fontes originais.

## Objetivos de apoio

1. **Permitir uma exploração geográfica contínua:** os resultados devem fazer sentido para qualquer nível escolhido — do mundo ao bairro — e permitir que a exploração termine nesse nível.

2. **Apoiar a descoberta por tema:** notícias e eventos devem poder ser consultados por categorias predefinidas e por busca de tema livre, sem exigir que o usuário adote uma única forma de expressar o interesse.

3. **Tornar a consulta de notícias atual e pertinente:** a seleção deve refletir a janela móvel de 24 horas, a relevância geográfica e temática, e o interesse do usuário, com resultados ordenados e duplicações consolidadas.

4. **Tornar a agenda útil para planejar ou acompanhar atividades:** os eventos devem corresponder à localização e ao intervalo de datas escolhido, permitindo consulta por data ou relevância e apresentando os dados disponíveis para avaliar cada evento.

5. **Permitir conferir e comparar resultados:** cada item deve oferecer informações concisas, atribuição e acesso à fonte original, sem apresentar alegações ou resultados sem sustentação verificável.

## Distinção entre NEWS e EVENT AGENDA

### NEWS

NEWS apresenta notícias cuja **data de publicação original verificável** está dentro das 24 horas imediatamente anteriores à consulta. A relevância geográfica pode decorrer de a notícia ocorrer na geografia selecionada ou de seu impacto regional ser diretamente verificável. A experiência oferece as categorias iniciais aprovadas e All/Todos; quando uma categoria específica é selecionada, o tema livre a refina, e com All/Todos o tema busca entre categorias. A interface e o conteúdo conciso podem ser apresentados em pt-BR ou en-US.

O usuário pode solicitar 5, 10, 15 ou 20 itens, com padrão 10. A seleção deve ser ordenada por relevância, evitar duplicações e conter apenas notícias verificadas. Cada item deve apresentar título fundamentado nas evidências da fonte, teaser de aproximadamente duas linhas, descrição curta distinta, atribuição e URL original verificado. Se não houver itens verificados suficientes, a quantidade exibida pode ser menor que a solicitada e a insuficiência deve ser informada.

### EVENT AGENDA

EVENT AGENDA apresenta eventos públicos **em andamento ou futuros** dentro de um intervalo de datas escolhido obrigatoriamente pelo usuário. O evento deve estar geograficamente ligado ao local onde acontece. A agenda abrange eventos anunciados publicamente, gratuitos ou pagos, inclusive por organizadores ou terceiros quando o anúncio for crível.

A experiência oferece as categorias iniciais aprovadas e All/Todos, combinadas com o tema livre segundo a regra de interseção/refinamento descrita acima. A interface e o conteúdo conciso podem ser apresentados em pt-BR ou en-US, embora fontes públicas em qualquer idioma possam ser consideradas. O usuário seleciona obrigatoriamente datas inicial e final inclusivas, sem intervalo pré-preenchido, e pode solicitar 5, 10, 15 ou 20 itens, com padrão 10. A ordenação padrão é cronológica crescente por início do evento, com opção por relevância. Eventos físicos e híbridos exigem local físico verificado na área; eventos totalmente online só se qualificam no escopo WORLD. Cada item deve apresentar identidade do evento, data e horário verificados quando disponíveis, local efetivo, descrição breve e fonte original.

## Indicadores candidatos para validação futura

Os indicadores abaixo orientam validações futuras e não definem metas adicionais. A meta inicial de desempenho aprovada está separada em [RNF-003](requirements.md) e ainda não foi medida.

- **Correspondência geográfica:** para itens avaliados, é possível verificar a relação com a geografia escolhida — ocorrência no local ou impacto regional diretamente verificável para NEWS; local de realização para EVENT AGENDA.
- **Correspondência temporal:** a publicação original de cada notícia avaliada pode ser confirmada dentro da janela móvel de 24 horas; eventos avaliados podem ser confirmados como em andamento ou futuros e compatíveis com o intervalo informado.
- **Aderência temática:** as notícias e os eventos apresentados são pertinentes à categoria ou ao tema livre usado na consulta.
- **Verificabilidade e rastreabilidade:** as informações apresentadas podem ser conferidas nas fontes atribuídas, e os links levam às fontes originais.
- **Integridade dos resultados:** duplicações relevantes são consolidadas, e resultados sem sustentação verificável não são inventados para preencher a quantidade solicitada.
- **Utilidade para consulta:** em avaliação futura, usuários conseguem compreender os dados apresentados, distinguir notícias de eventos e abrir suas fontes para conferir detalhes.

Os critérios de aceite dos requisitos aprovados constam em [Requirements](requirements.md). Os indicadores desta seção não substituem esses critérios.

## Premissas e resoluções posteriores

### Premissas de partida desta proposta

- NEWS e EVENT AGENDA são experiências igualmente importantes na direção de produto informada.
- A exploração geográfica segue a hierarquia mundo > continente > país > estado/região > cidade > bairro, e o usuário pode parar em qualquer nível.
- As opções 5, 10, 15 e 20 são limites máximos de resultados, com padrão 10; não são metas de desempenho.
- O intervalo de 24 horas de NEWS não define a regra temporal da EVENT AGENDA.
- Os indicadores acima são candidatos para validação futura, não métricas já aprovadas.

As decisões de produto antes listadas como questões em aberto foram aprovadas em 2026-11-10 e estão rastreadas no [registro OD-01 a OD-14](open-decisions.md). Limites e referências geográficas sem verificação confiável, datas sem horário/duração e horários locais ambíguos permanecem ressalvas de validação, não decisões de produto em aberto. Métodos, fontes técnicas, pesos e heurísticas são definidos em CONSTRUCTION.

## Limite desta atividade

Este documento aprova somente o Product Objective da etapa INCEPTION. Os usuários e papéis e o escopo do MVP são mantidos nos documentos aprovados vinculados acima. Este documento não aprova arquitetura, roadmap, especificações ou código, que dependem das respectivas etapas e aprovações. OPERATIONS — implantação, monitoramento e evolução — permanece sob responsabilidade humana.
