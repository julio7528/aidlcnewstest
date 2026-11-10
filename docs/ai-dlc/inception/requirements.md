# Requisitos — GeophNews

> **STATUS: APPROVED — baseline de requisitos de INCEPTION, aprovado em 2026-11-10.**
> Esta aprovação cobre somente este baseline de requisitos. Os assuntos listados
> em “Decisões em aberto” não foram decididos por inferência.

## 1. Estado e limites

Este documento formaliza decisões confirmadas na conversa e requisitos não funcionais que foram propostos e aprovados nesta revisão. A origem indicada em cada requisito distingue decisões originalmente confirmadas de propostas analíticas agora aprovadas.

- **Confirmado na conversa:** decisão explicitamente fornecida pelo usuário e incorporada ao baseline aprovado.
- **Proposta analítica aprovada nesta revisão:** requisito ou critério proposto pelo analista e aprovado pelo usuário como parte deste baseline.
- **Em aberto:** assunto sem decisão suficiente; não deve ser completado por suposição.

Os critérios de aceitação pertencem ao baseline aprovado, exceto quando dependem explicitamente de uma decisão em aberto.

Este baseline cobre somente INCEPTION — requisitos. Ele não aprova o requisito principal, o objetivo de produto, o escopo final do MVP, arquitetura, implementação ou contratos formais. Usuários e Papéis são tratados separadamente em [Usuários e Papéis](users-and-roles.md) e não são redefinidos aqui. Este documento não inicia CONSTRUCTION. OPERATIONS continua sendo uma etapa exclusivamente humana.

## 2. Rastreabilidade ao problema aprovado

A definição aprovada em [Problem Definition](problem-definition.md) permanece autoritativa e imutável. Os códigos abaixo são referências analíticas às ideias do texto aprovado, não alterações à definição:

- **P-01 — Fragmentação:** notícias e eventos estão distribuídos entre fontes públicas na internet.
- **P-02 — Geografia:** a descoberta e o acompanhamento referem-se a acontecimentos relevantes em localizações específicas e diferentes níveis territoriais.
- **P-03 — Esforço de verificação:** consultas manuais, comparação de fontes e avaliação de atualidade, relevância geográfica e confiabilidade são necessárias nos mecanismos convencionais.
- **P-04 — Necessidades temporais distintas:** notícias dizem respeito a publicações recentes; agendas de eventos, a atividades em andamento ou futuras.
- **P-05 — Descoberta e rastreabilidade:** há necessidade de facilitar a descoberta e consulta e preservar a rastreabilidade às fontes originais.

## 3. Requisitos funcionais

### RF-001 — Duas experiências de primeira classe

**Origem:** Confirmado na conversa.

GeophNews deve oferecer NEWS e EVENT AGENDA como duas experiências de primeira classe do MVP.

**Critérios de aceitação:**

- NEWS e EVENT AGENDA podem ser selecionadas como experiências distintas.
- Cada experiência permite iniciar e consultar sua própria busca sem exigir que a pessoa usuária passe primeiro pela outra.

**Rastreabilidade:** P-04, P-05.

### RF-002 — Seleção geográfica hierárquica em mapa

**Origem:** Confirmado na conversa.

NEWS e EVENT AGENDA devem permitir seleção geográfica baseada em mapa na hierarquia mundo > continente > país > estado/região > cidade > bairro. A pessoa usuária pode encerrar a seleção em qualquer nível, e a busca deve cobrir as sub-regiões da área selecionada.

**Critérios de aceitação:**

- Os seis níveis da hierarquia estão disponíveis para seleção.
- Uma busca pode usar qualquer nível como área selecionada, sem exigir a escolha de um nível mais específico.
- Ao selecionar uma área com sub-regiões, a busca considera acontecimentos elegíveis nessas sub-regiões.

Os critérios não definem limites cartográficos, fontes de geocodificação ou a taxonomia de cada jurisdição.

**Rastreabilidade:** P-02, P-05.

### RF-003 — Categoria e tópico em texto livre

**Origem:** Confirmado na conversa; a interação entre os filtros permanece em aberto.

Em ambos os modos, a busca deve permitir seleção de categoria, incluindo a opção All, e busca opcional por tópico em texto livre.

**Critérios de aceitação:**

- A interface oferece seleção de categoria e inclui All entre as opções.
- A busca pode ser enviada sem texto livre.
- A interface permite informar texto livre quando desejado.
- A combinação e o efeito de categoria e texto livre não são presumidos até a decisão OD-01.

**Rastreabilidade:** P-03, P-05.

### RF-004 — Descoberta pública e atribuição à fonte original

**Origem:** Confirmado na conversa.

NEWS e EVENT AGENDA devem descobrir candidatos em fontes públicas da internet, validar a confiabilidade das informações apresentadas e preservar a atribuição à fonte original.

**Critérios de aceitação:**

- Cada resultado exibido identifica sua fonte e apresenta o link original associado à informação.
- O sistema não apresenta uma URL inventada como se fosse uma fonte original.
- Uma informação sem verificação suficiente não é apresentada como verificada.

**Rastreabilidade:** P-01, P-03, P-05.

### RF-005 — Qualificação de fontes para NEWS

**Origem:** Confirmado na conversa; limiares permanecem em aberto.

A validação de notícias deve priorizar jornalismo identificável e fontes oficiais ou primárias confiáveis. Uma publicação isolada e não confirmada em rede social não pode ser tratada como notícia verificada.

**Critérios de aceitação:**

- Uma publicação social isolada e não confirmada não é suficiente para apresentar uma notícia como verificada.
- A seleção e validação consideram se a fonte é jornalismo identificável ou fonte oficial/primária confiável.
- Pesos, limiares e evidências suficientes para essas avaliações permanecem em aberto em OD-05 e OD-08.

**Rastreabilidade:** P-03, P-05.

### RF-006 — Relevância geográfica de NEWS

**Origem:** Confirmado na conversa.

Uma notícia só corresponde à área selecionada quando o acontecimento ocorre nessa área ou quando existe impacto direto nela que possa ser verificado. A localização do veículo ou publisher, por si só, não estabelece relevância geográfica.

**Critérios de aceitação:**

- Uma notícia cujo único vínculo com a área seja a localização do veículo local não é considerada geograficamente correspondente.
- A correspondência é aceita quando a ocorrência está dentro da área ou há impacto direto verificável nela.
- A definição de evidência suficiente para impacto direto permanece em aberto em OD-05.

**Rastreabilidade:** P-02, P-03.

### RF-007 — Janela temporal de NEWS

**Origem:** Confirmado na conversa; detalhes de fuso horário e evidência do timestamp permanecem em aberto.

NEWS deve considerar publicações da janela móvel das 24 horas anteriores à busca, usando o horário original de publicação verificado. Horário do acontecimento e horário de última atualização não substituem o horário original de publicação.

Notícias sem horário original de publicação verificável devem ser excluídas dos resultados verificados.

**Critérios de aceitação:**

- Uma notícia cuja publicação original verificável esteja fora da janela móvel não é incluída como recente.
- Uma notícia sem timestamp original verificável é excluída dos resultados verificados.
- Horário do evento e timestamp de última atualização não são usados como substitutos do timestamp original.
- Fuso horário, evidências aceitas e tratamento do instante exato de corte são tratados em OD-04.

**Rastreabilidade:** P-03, P-04.

### RF-008 — Limite de resultados de NEWS

**Origem:** Confirmado na conversa.

NEWS deve permitir solicitar limites máximos de 5, 10, 15 ou 20 resultados. O limite selecionado é um máximo, não uma promessa de quantidade mínima.

**Critérios de aceitação:**

- As opções de limite incluem 5, 10, 15 e 20.
- A quantidade retornada não excede o limite solicitado.
- A regra para um limite padrão quando nenhum é selecionado permanece em aberto em OD-11.

**Rastreabilidade:** P-05.

### RF-009 — Deduplicação e ordenação de NEWS

**Origem:** Confirmado na conversa; critérios quantitativos permanecem em aberto.

NEWS deve deduplicar matérias sobre um mesmo acontecimento e ordenar os resultados considerando importância, relevância e diversidade geográfica apropriada.

**Critérios de aceitação:**

- Matérias identificadas como referentes ao mesmo acontecimento não aparecem como resultados independentes duplicados.
- A ordenação considera importância e relevância para a consulta, além de diversidade geográfica apropriada.
- Definições de duplicidade, limiares e balanceamento dos critérios são tratados em OD-05.

**Rastreabilidade:** P-02, P-03, P-05.

### RF-010 — Apresentação de resultados de NEWS

**Origem:** Confirmado na conversa; critérios de concisão permanecem em aberto.

Cada resultado de NEWS deve apresentar um título gerado fundamentado na fonte, um resumo de aproximadamente duas linhas, a identificação da fonte e seu URL original verificado.

**Critérios de aceitação:**

- O título e o resumo podem ser sustentados pelo conteúdo verificado da fonte.
- A apresentação inclui identificação da fonte e link original verificado.
- A informação não verificada não é acrescentada ao título ou resumo.
- A definição exata de “aproximadamente duas linhas” e os critérios de qualidade editorial permanecem em OD-05 e OD-13.

**Rastreabilidade:** P-03, P-05.

### RF-011 — Tipos de eventos e fontes de descoberta

**Origem:** Confirmado na conversa.

EVENT AGENDA deve aceitar eventos de todos os tipos que sejam anunciados publicamente, sejam pagos ou gratuitos. Anúncios de organizadores, terceiros, pessoas comuns e redes sociais podem servir como pistas para descoberta.

**Critérios de aceitação:**

- Um evento público não é excluído apenas por ser pago ou por pertencer a determinada categoria.
- Anúncios de terceiros ou em redes sociais podem originar um candidato a evento.
- Uma pista de descoberta, por si só, não torna o evento verificado; aplica-se RF-012.

**Rastreabilidade:** P-01, P-03, P-05.

### RF-012 — Verificação de eventos

**Origem:** Confirmado na conversa; quantidade e suficiência das fontes permanecem em aberto.

Antes de apresentar um evento como verificado, deve-se verificar sua ocorrência, data, local/venue e fonte, inclusive quando a pista inicial vem de terceiros, pessoas comuns ou redes sociais.

**Critérios de aceitação:**

- Um anúncio serve como pista, mas os dados de ocorrência, data, local/venue e fonte precisam de evidência verificável.
- Um candidato sem verificação suficiente não é apresentado como evento verificado.
- O número de fontes exigido e a evidência aceitável por tipo de fonte são tratados em OD-08.

**Rastreabilidade:** P-03, P-05.

### RF-013 — Intervalo de datas de EVENT AGENDA

**Origem:** Confirmado na conversa; semântica dos limites permanece em aberto.

Uma busca em EVENT AGENDA exige que a pessoa usuária selecione uma data inicial e uma data final. Não deve haver intervalo padrão preenchido automaticamente.

**Critérios de aceitação:**

- A busca não começa sem as duas datas selecionadas.
- A interface não preenche automaticamente um intervalo como se tivesse sido selecionado pela pessoa usuária.
- Os resultados correspondem ao intervalo informado, sujeito à decisão sobre fuso horário, limites e eventos que atravessam o intervalo em OD-06.

**Rastreabilidade:** P-04, P-05.

### RF-014 — Elegibilidade temporal de eventos

**Origem:** Confirmado na conversa; mecânica para eventos em andamento permanece em aberto.

EVENT AGENDA só pode retornar eventos em andamento ou futuros; eventos encerrados não são elegíveis.

**Critérios de aceitação:**

- Um evento comprovadamente encerrado antes da consulta não aparece como elegível.
- Eventos em andamento ou futuros podem ser considerados se também satisfizerem o intervalo selecionado e os requisitos de verificação.
- Fuso horário, horários ausentes e eventos que atravessam o início ou o fim do intervalo são tratados em OD-06.

**Rastreabilidade:** P-04.

### RF-015 — Relevância geográfica de EVENT AGENDA

**Origem:** Confirmado na conversa; eventos virtuais ou híbridos permanecem em aberto.

A correspondência geográfica de um evento deve usar seu local/venue real. A residência do publisher ou o mero impacto externo do evento não são suficientes.

**Critérios de aceitação:**

- Um evento corresponde à área selecionada quando seu local/venue real está nessa área.
- A residência do anunciante ou publisher, sem correspondência do local/venue, não qualifica o evento.
- A forma de tratar eventos online ou híbridos é tratada em OD-12.

**Rastreabilidade:** P-02, P-05.

### RF-016 — Limite e ordenação de EVENT AGENDA

**Origem:** Contagens e opções de ordenação confirmadas na conversa; ordem padrão cronológica continua sendo uma proposta pendente de confirmação específica.

EVENT AGENDA deve permitir limites de até 5, 10, 15 ou 20 resultados e ordenação por data ou relevância. Ordem cronológica é uma proposta de padrão, não uma decisão confirmada por este baseline.

**Critérios de aceitação:**

- As opções de limite incluem 5, 10, 15 e 20, e a quantidade retornada não excede o limite solicitado.
- A pessoa usuária pode escolher ordenação por data ou relevância.
- Ordem cronológica só será adotada como padrão após confirmação em OD-07.
- Padrão de quantidade quando não selecionada, direção da ordenação por data e definição de cronologia permanecem em aberto.

**Rastreabilidade:** P-04, P-05.

### RF-017 — Apresentação de resultados de EVENT AGENDA

**Origem:** Confirmado na conversa.

Cada resultado de EVENT AGENDA deve apresentar nome, datas/horários quando disponíveis, local, descrição concisa e link para a fonte original.

**Critérios de aceitação:**

- A apresentação inclui o nome, local, descrição concisa e link da fonte original.
- Datas e horários são apresentados quando disponíveis e verificados.
- Dados ausentes não são inventados para preencher campos.

**Rastreabilidade:** P-03, P-05.

### RF-018 — Limites, conteúdo e resultados insuficientes

**Origem:** Confirmado na conversa.

Em ambos os modos, os resultados devem respeitar os limites geográficos e tópicos solicitados. O sistema não deve inventar notícias, eventos, fatos ou URLs para completar uma quantidade. Quando houver menos resultados verificados do que o máximo solicitado, deve retornar os disponíveis e informar com transparência que os resultados verificados foram insuficientes.

**Critérios de aceitação:**

- Nenhum resultado é incluído fora dos limites de localização ou tópico da consulta.
- Uma quantidade insuficiente não causa ampliação silenciosa de localização ou tópico.
- Nenhum registro, fato ou URL é fabricado para alcançar a quantidade solicitada.
- Quando faltarem correspondências verificadas, a resposta informa essa insuficiência e retorna apenas os resultados verificados disponíveis.

**Rastreabilidade:** P-02, P-03, P-05.

## 4. Requisitos não funcionais

Os requisitos desta seção foram originalmente propostos pelo analista e aprovados pelo usuário como parte deste baseline. Os valores e padrões indicados como abertos ainda não estão definidos.

### RNF-001 — Acessibilidade dos controles

**Origem:** Proposta analítica aprovada nesta revisão.

Os controles de mapa, modo, categoria, tópico, intervalo de datas, ordenação e links de resultados devem ser utilizáveis por teclado. Estados e mensagens não devem depender exclusivamente de cor.

**Critérios de aceitação:**

- Os controles interativos podem ser alcançados e acionados por teclado.
- O foco atual é perceptível.
- Seleções, estados de verificação e mensagens de insuficiência têm identificação textual além de cor.

O padrão de acessibilidade e os dispositivos/tecnologias assistivas de validação permanecem em aberto.

### RNF-002 — Integridade da proveniência

**Origem:** Proposta analítica aprovada nesta revisão.

A apresentação de um resultado deve preservar a associação entre o item, a identificação da fonte e seu URL original verificado.

**Critérios de aceitação:**

- Em cada resultado de teste, o link exibido corresponde ao URL original verificado associado àquele item.
- A atribuição não é substituída por URL gerada ou por link de outro resultado.

### RNF-003 — Meta de desempenho mensurável

**Origem:** Proposta analítica aprovada nesta revisão.

O desempenho deve ser avaliado separadamente para NEWS e EVENT AGENDA com carga de teste acordada. Limites numéricos devem ser definidos antes de uma aprovação de desempenho.

**Critérios de aceitação:**

- O método, o perfil de carga e a meta de latência são aprovados antes do teste de desempenho.
- O relatório de validação registra latência observada por modo e compara os resultados à meta aprovada.

A meta e o perfil de carga permanecem em aberto em OD-09.

### RNF-004 — Diferenciação entre ausência de resultados e falha de descoberta

**Origem:** Proposta analítica aprovada nesta revisão.

A apresentação deve distinguir “nenhum resultado verificado disponível” de uma consulta cuja descoberta tenha sido incompleta por indisponibilidade de fontes.

**Critérios de aceitação:**

- Em uma validação com fonte indisponível, o resultado não afirma que não há eventos/notícias quando a consulta foi incompleta.
- A indicação de indisponibilidade não é apresentada como resultado verificado.
- Detalhes de fallback e comunicação de falhas permanecem em aberto em OD-10.

## 5. Direção técnica planejada — não é arquitetura aprovada

A direção abaixo é apenas técnica e planejada. Ela não aprova arquitetura, responsabilidades de componentes ou implementação e não converte essas escolhas em requisitos funcionais:

- Python/Django, Django Ninja, HTMX, MapLibre GL JS e PostgreSQL/PostGIS.
- Pydantic AI com DeepSeek.
- Serper.dev como fonte de descoberta primária e Tavily como suplementar.
- Redis opcional.
- LangGraph adiado, salvo se complexidade futura justificar sua adoção.
- RAG não planejado inicialmente.
- Desenvolver a API antes do frontend.

## 6. Decisões em aberto

- **OD-01 — Relação entre categoria e texto livre:** o texto livre refina ou expande a categoria selecionada?
- **OD-02 — Catálogo e All:** quais categorias serão oferecidas e qual é o comportamento exato de All em cada modo?
- **OD-03 — Geografia e idiomas:** quais limites e fontes definem continente, país, estado/região, cidade e bairro, quais idiomas são cobertos e como eventos virtuais/híbridos se relacionam à seleção geográfica?
- **OD-04 — Tempo e timestamp de NEWS:** qual fuso horário se aplica e quais evidências tornam verificável o horário original de publicação?
- **OD-05 — Relevância, qualidade e deduplicação:** quais limiares definem relevância, impacto geográfico direto, confiabilidade, importância, diversidade geográfica, duplicidade e qualidade de resumo?
- **OD-06 — Intervalos e eventos em andamento:** qual fuso horário se aplica a eventos; como tratar intervalos parciais, mesmo dia, limites do intervalo, eventos que o atravessam e inclusão de eventos em andamento?
- **OD-07 — Ordenação de eventos:** confirmar se a ordenação cronológica deve ser o padrão, além de definir direção e semântica da ordenação por data.
- **OD-08 — Verificação:** quantas fontes e quais evidências são necessárias por modo e tipo de fonte?
- **OD-09 — Desempenho:** quais metas de resposta, perfil de carga e método de validação devem ser usados?
- **OD-10 — Cache e fallback:** quais limites de cache e regras de fallback entre fontes devem ser adotados?
- **OD-11 — Limite padrão:** deve haver um limite de resultados padrão quando a pessoa usuária não selecionar 5, 10, 15 ou 20?
- **OD-12 — Eventos online/híbridos:** como verificar e associar local/venue real quando o evento não tem um local físico convencional?
- **OD-13 — Conteúdo de NEWS:** quais critérios definem grounding, concisão e a interpretação verificável de “aproximadamente duas linhas”?
- **OD-14 — Aprovações separadas:** requisito principal, objetivo de produto, escopo final do MVP, arquitetura, implementação e contratos formais permanecem fora deste baseline. Usuários e Papéis são mantidos em documento separado e não são redefinidos aqui.

## 7. Fora da aprovação deste baseline

Este baseline não aprova:

- O requisito principal ou o objetivo de produto.
- Definições de usuários e papéis, tratadas em documento separado.
- O escopo final do MVP.
- Arquitetura ou implementação.
- Contratos formais.
- Uma especificação de CONSTRUCTION ou qualquer atividade de OPERATIONS.
