# Product Objective — GeophNews

> **APPROVED — limited to the Product Objective only.** This approval does not approve users or roles, full product scope, architecture, roadmap, specifications, implementation, or Operations decisions; these remain subject to their applicable activities and approvals.

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

NEWS apresenta notícias cuja **data de publicação original verificável** está dentro das 24 horas imediatamente anteriores à consulta. A relevância geográfica pode decorrer de a notícia ocorrer na geografia selecionada ou de seu impacto regional ser diretamente verificável. A experiência deve permitir categorias predefinidas — incluindo “Todos”, conforme o alinhamento registrado — e busca por tema livre.

O usuário pode solicitar 5, 10, 15 ou 20 itens. A seleção deve ser ordenada por relevância, evitar duplicações e conter apenas notícias verificadas. Cada item deve apresentar título fundamentado nas evidências da fonte, chamada de aproximadamente duas linhas, atribuição e URL original. Se não houver itens verificados suficientes, a quantidade exibida pode ser menor que a solicitada.

### EVENT AGENDA

EVENT AGENDA apresenta eventos públicos **em andamento ou futuros** dentro de um intervalo de datas escolhido obrigatoriamente pelo usuário. O evento deve estar geograficamente ligado ao local onde acontece. A agenda abrange eventos anunciados publicamente, gratuitos ou pagos, inclusive por organizadores ou terceiros quando o anúncio for crível.

A experiência deve permitir categorias predefinidas e busca por tema livre. O usuário pode solicitar até 5, 10, 15 ou 20 itens e ordená-los por data — opção padrão — ou por relevância. Cada item deve apresentar identidade do evento, data e horário quando disponíveis, local efetivo, descrição breve e fonte original.

## Indicadores candidatos para validação futura

Os indicadores abaixo são propostas para orientar validações posteriores. Não constituem critérios aprovados nem definem metas numéricas.

- **Correspondência geográfica:** para itens avaliados, é possível verificar a relação com a geografia escolhida — ocorrência no local ou impacto regional diretamente verificável para NEWS; local de realização para EVENT AGENDA.
- **Correspondência temporal:** a publicação original de cada notícia avaliada pode ser confirmada dentro da janela móvel de 24 horas; eventos avaliados podem ser confirmados como em andamento ou futuros e compatíveis com o intervalo informado.
- **Aderência temática:** as notícias e os eventos apresentados são pertinentes à categoria ou ao tema livre usado na consulta.
- **Verificabilidade e rastreabilidade:** as informações apresentadas podem ser conferidas nas fontes atribuídas, e os links levam às fontes originais.
- **Integridade dos resultados:** duplicações relevantes são consolidadas, e resultados sem sustentação verificável não são inventados para preencher a quantidade solicitada.
- **Utilidade para consulta:** em avaliação futura, usuários conseguem compreender os dados apresentados, distinguir notícias de eventos e abrir suas fontes para conferir detalhes.

A forma de avaliação, os critérios de aceitação e eventuais metas quantitativas ainda precisam ser definidos e aprovados.

## Premissas e questões em aberto

### Premissas de partida desta proposta

- NEWS e EVENT AGENDA são experiências igualmente importantes na direção de produto informada.
- A exploração geográfica segue a hierarquia mundo > continente > país > estado/região > cidade > bairro, e o usuário pode parar em qualquer nível.
- As opções 5, 10, 15 e 20 são quantidades que o usuário pode solicitar; não são metas de desempenho.
- O intervalo de 24 horas de NEWS não define a regra temporal da EVENT AGENDA.
- Os indicadores acima são candidatos para validação futura, não métricas já aprovadas.

### Questões que requerem confirmação do responsável

- Quais categorias serão oferecidas em cada experiência, qual será o comportamento de “Todos” e como categorias e busca por tema livre poderão ser combinadas.
- Quais idiomas, mercados e fontes públicas deverão ser cobertos.
- Quais referências geográficas definirão estados/regiões, cidades, bairros e cobertura de sub-regiões.
- Qual nível de evidência será suficiente para verificar fontes, fatos, horários de publicação, relevância geográfica e anúncios de eventos.
- Como equilibrar relevância e diversidade geográfica, quais duplicações devem ser consolidadas e quais critérios de confiabilidade e ordenação serão aceitos.
- Como interpretar datas de eventos, limites do intervalo, fusos horários, ocorrências recorrentes e a diferença entre a data do evento e a data de seu anúncio.
- Quais usuários ou papéis devem ser considerados e quais serão os limites e exclusões do MVP.
- Quais indicadores serão adotados, como serão validados e se haverá metas quantitativas.

## Limite desta atividade

Este documento aprova somente o Product Objective da etapa INCEPTION. Não define os usuários ou o escopo completo do produto; esses itens permanecem para atividades posteriores. Também não aprova arquitetura, roadmap, especificações ou código, que dependem das respectivas etapas e aprovações. OPERATIONS — implantação, monitoramento e evolução — permanece sob responsabilidade humana.
