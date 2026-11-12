# Requisitos — GeophNews

> **STATUS: APPROVED — baseline de requisitos de INCEPTION, aprovado em 2026-11-10.**
> As decisões do proprietário aprovadas em 2026-11-10 estão consolidadas em
> [MVP Scope](mvp-scope.md) e rastreadas em [OD-01 a OD-14](open-decisions.md).

## 1. Estado e limites

Este documento formaliza decisões confirmadas na conversa e requisitos não funcionais que foram propostos e aprovados nesta revisão. A origem indicada em cada requisito distingue decisões originalmente confirmadas de propostas analíticas agora aprovadas.

- **Confirmado na conversa:** decisão explicitamente fornecida pelo usuário e incorporada ao baseline aprovado.
- **Proposta analítica aprovada nesta revisão:** requisito ou critério proposto pelo analista e aprovado pelo usuário como parte deste baseline.
- **Adiado para CONSTRUCTION:** métodos, heurísticas e responsabilidades técnicas; não são decisões de requisito pendentes.

Os critérios de aceitação pertencem ao baseline aprovado. Ressalvas de evidência são explicitadas como limitações de validação; métodos e heurísticas técnicas permanecem para CONSTRUCTION.

Este baseline cobre somente INCEPTION — requisitos. O Product Objective, Users and Roles e MVP Scope estão aprovados em seus documentos próprios: [Product Objective](product-objective.md), [Users and Roles](users-and-roles.md) e [MVP Scope](mvp-scope.md). O requisito principal RP-01 foi aprovado separadamente em 2026-11-11 e está registrado no [contexto do projeto](../../context.md); sua aprovação não é inferida deste baseline. Arquitetura e implementação permanecem para CONSTRUCTION; contratos formais permanecem fora deste baseline. Este documento não inicia CONSTRUCTION. OPERATIONS continua sendo uma etapa exclusivamente humana.

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

NEWS e EVENT AGENDA devem permitir seleção geográfica em mapa mundial interativo e clicável, navegável pela hierarquia mundo > continente > país > estado/região > cidade > bairro. A pessoa usuária pode encerrar a seleção em qualquer nível, e a busca deve cobrir as sub-regiões elegíveis da área selecionada.

**Critérios de aceitação:**

- Os seis níveis da hierarquia estão disponíveis para seleção.
- Uma busca pode usar qualquer nível como área selecionada, sem exigir a escolha de um nível mais específico.
- Ao selecionar uma área com sub-regiões, a busca considera acontecimentos elegíveis nessas sub-regiões.
- Limites e contenção geográfica são verificados; o sistema não inventa bairro ou relação de contenção e informa quando referências confiáveis forem insuficientes.

Os critérios não definem limites cartográficos, fontes de geocodificação ou a taxonomia de cada jurisdição.

**Rastreabilidade:** P-02, P-05.

### RF-003 — Categoria e tópico em texto livre

**Origem:** Confirmado pelo proprietário na decisão 2, aprovada em 2026-11-10.

Em ambos os modos, a busca deve permitir seleção de categoria e busca opcional por tópico em texto livre. O catálogo inicial inclui Politics, Economy, Technology, Sports, Agribusiness, Health, Education, Science, Culture, Environment e Other, além de All/Todos como opção sem restrição de categoria.

**Critérios de aceitação:**

- A interface oferece o catálogo definido e All/Todos como opção sem filtro de categoria.
- A busca pode ser enviada sem texto livre.
- A interface permite informar texto livre quando desejado.
- Com uma categoria específica, o texto livre restringe essa categoria por interseção; com All/Todos, o texto livre busca sem restrição de categoria; sem texto livre, aplica-se somente a categoria selecionada.

**Rastreabilidade:** P-03, P-05.

### RF-004 — Descoberta pública e atribuição à fonte original

**Origem:** Confirmado na conversa.

NEWS e EVENT AGENDA devem descobrir candidatos em fontes públicas da internet, aplicar as regras proporcionais de evidência de RF-005 e RF-012 e preservar atribuição precisa à fonte original.

**Critérios de aceitação:**

- Cada resultado exibido identifica sua fonte e apresenta o link original associado à informação.
- O sistema não apresenta uma URL inventada como se fosse uma fonte original.
- Uma informação sem verificação suficiente não é apresentada como verificada.

**Rastreabilidade:** P-01, P-03, P-05.

### RF-005 — Qualificação de fontes para NEWS

**Origem:** Confirmado pelo proprietário na decisão 5, aprovada em 2026-11-10.

Uma notícia pode ser verificada com uma fonte jornalística identificável e confiável ou uma fonte primária/oficial autoritativa, desde que o timestamp original de publicação, os fatos usados, o URL original e a relação geográfica sejam verificáveis. Uma publicação isolada e não corroborada em rede social não é notícia confirmada.

**Critérios de aceitação:**

- Uma única fonte elegível satisfaz a regra somente quando sua identificação, confiabilidade e os dados requeridos pelo tipo de notícia são verificáveis.
- Uma postagem social isolada e não corroborada não sustenta uma notícia apresentada como confirmada.

**Rastreabilidade:** P-03, P-05.

### RF-006 — Relevância geográfica de NEWS

**Origem:** Confirmado na conversa.

A elegibilidade geográfica de NEWS exige ocorrência na área selecionada ou impacto direto verificado nela; endereço do publisher, por si só, nunca qualifica. A ordenação prioriza geografia e tópico verificados, significância/impacto direto, confiabilidade da fonte e recência da publicação original.

**Critérios de aceitação:**

- Uma notícia cujo único vínculo com a área seja a localização do veículo local não é considerada geograficamente correspondente.
- A correspondência é aceita quando a ocorrência está dentro da área ou há impacto direto verificável nela.
- Diversidade geográfica é considerada quando apropriado, sem superar a elegibilidade ou itens claramente mais relevantes.

**Rastreabilidade:** P-02, P-03.

### RF-007 — Janela temporal de NEWS

**Origem:** Confirmado pelo proprietário na decisão 4, aprovada em 2026-11-10.

NEWS deve considerar exatamente a janela móvel das 24 horas imediatamente anteriores à execução da consulta, usando o instante original de publicação verificado e normalizado para UTC. Horário do acontecimento e horário de última atualização não substituem o horário original de publicação. A exibição de timestamps usa o fuso horário relevante do evento/local.

Notícias sem horário original de publicação verificável devem ser excluídas dos resultados verificados.

**Critérios de aceitação:**

- Uma notícia cuja publicação original verificável esteja fora da janela móvel não é incluída como recente.
- Uma notícia sem timestamp original verificável é excluída dos resultados verificados.
- Horário do evento e timestamp de última atualização não são usados como substitutos do timestamp original.
- Instantes são comparados em UTC; publicação sem instante original verificável é excluída.

**Rastreabilidade:** P-03, P-04.

### RF-008 — Limite de resultados de NEWS

**Origem:** Confirmado pelo proprietário na decisão 7, aprovada em 2026-11-10.

NEWS deve permitir solicitar limites máximos de 5, 10, 15 ou 20 resultados. O limite selecionado é um máximo, não uma promessa de quantidade mínima.

**Critérios de aceitação:**

- As opções de limite incluem 5, 10, 15 e 20, com padrão 10.
- A quantidade retornada não excede o limite solicitado.

**Rastreabilidade:** P-05.

### RF-009 — Deduplicação e ordenação de NEWS

**Origem:** Confirmado pelo proprietário na decisão 6, aprovada em 2026-11-10; pesos e heurísticas são decisões de CONSTRUCTION.

NEWS deve colapsar a cobertura do mesmo acontecimento em um resultado e ordenar os itens por relevância, preferindo a melhor fonte original verificada. A ordenação prioriza geografia/tópico verificados, significância/impacto direto, confiabilidade da fonte e recência da publicação original; diversidade geográfica aplica-se quando apropriado sem sobrepor elegibilidade ou itens claramente mais relevantes.

**Critérios de aceitação:**

- Matérias identificadas como referentes ao mesmo acontecimento não aparecem como resultados independentes duplicados.
- A ordenação considera importância e relevância para a consulta, além de diversidade geográfica apropriada.
- Cobertura do mesmo acontecimento aparece uma única vez e o item mantém atribuição à melhor fonte original verificada disponível.

**Rastreabilidade:** P-02, P-03, P-05.

### RF-010 — Apresentação de resultados de NEWS

**Origem:** Confirmado pelo proprietário na decisão 7, aprovada em 2026-11-10.

Cada resultado de NEWS deve apresentar um título fundamentado em evidências, um teaser de aproximadamente duas linhas, uma descrição curta e distinta, timestamp de publicação quando verificável, identificação da fonte e URL original verificado.

**Critérios de aceitação:**

- O título e o resumo podem ser sustentados pelo conteúdo verificado da fonte.
- A apresentação inclui identificação da fonte e link original verificado.
- A informação não verificada não é acrescentada ao título ou resumo.
- Não se impõe contagem fixa de caracteres; truncamento visual é decisão posterior de UI.

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

**Origem:** Confirmado pelo proprietário na decisão 5, aprovada em 2026-11-10.

Antes de apresentar um evento como verificado, deve-se confirmar sua ocorrência, data/horário e fonte, além do local físico quando aplicável. Um anúncio oficial verificável do organizador pode, sozinho, satisfazer a evidência desses dados. Sem fonte oficial/autoritativa do organizador, são necessárias pelo menos duas fontes confiáveis e independentes que corroborem ocorrência, data/horário e local físico quando aplicável. Terceiros, pessoas comuns e redes sociais podem ser pistas, não fatos publicados sem verificação.

**Critérios de aceitação:**

- Um anúncio oficial verificável do organizador pode satisfazer a regra com uma fonte quando sustentar a ocorrência, data/horário e venue físico quando aplicável.
- Na ausência de fonte oficial/autoritativa do organizador, pelo menos duas fontes confiáveis e independentes corroboram ocorrência, data/horário e local físico quando aplicável.
- Um candidato sem verificação suficiente não é apresentado como evento verificado.
- Pistas de terceiros ou sociais não são apresentadas como fatos verificados sem a evidência exigida.
- Os limiares de evidência são os desta regra; heurísticas de detecção e classificação são decisões de CONSTRUCTION.

**Rastreabilidade:** P-03, P-05.

### RF-013 — Intervalo de datas de EVENT AGENDA

**Origem:** Confirmado pelo proprietário na decisão 4, aprovada em 2026-11-10.

Uma busca em EVENT AGENDA exige que a pessoa usuária selecione uma data inicial e uma data final. Não deve haver intervalo padrão preenchido automaticamente.

**Critérios de aceitação:**

- A busca não começa sem as duas datas selecionadas.
- A interface não preenche automaticamente um intervalo como se tivesse sido selecionado pela pessoa usuária.
- As datas inicial e final são inclusivas e avaliadas no fuso horário local do evento.

**Rastreabilidade:** P-04, P-05.

### RF-014 — Elegibilidade temporal de eventos

**Origem:** Confirmado pelo proprietário na decisão 4, aprovada em 2026-11-10.

EVENT AGENDA só pode retornar eventos em andamento ou futuros; eventos encerrados não são elegíveis. A data do anúncio não substitui a data de ocorrência do evento.

**Critérios de aceitação:**

- Um evento comprovadamente encerrado antes da consulta não aparece como elegível.
- Um evento em andamento ou futuro é elegível quando sua duração real se sobrepõe a qualquer parte do intervalo selecionado, no fuso horário local do evento.
- Um evento concluído não é elegível, mesmo que sua data se sobreponha historicamente ao intervalo.
- Fontes que fornecem apenas data, sem hora ou duração, não autorizam inferência desses dados; incerteza de limite ou horário local ambíguo deve ser sinalizada como limitação de validação.

**Rastreabilidade:** P-04.

### RF-015 — Relevância geográfica de EVENT AGENDA

**Origem:** Confirmado pelo proprietário na decisão 3, aprovada em 2026-11-10.

A correspondência geográfica de um evento deve usar seu local/venue real. A residência do publisher ou o mero impacto externo do evento não são suficientes.

**Critérios de aceitação:**

- Um evento físico ou híbrido corresponde à área selecionada quando seu local/venue físico verificado está nessa área.
- Um evento totalmente online só é elegível com o escopo WORLD.
- A residência do anunciante ou publisher, sem correspondência do local/venue, não qualifica o evento.

**Rastreabilidade:** P-02, P-05.

### RF-016 — Limite e ordenação de EVENT AGENDA

**Origem:** Confirmado pelo proprietário na decisão 7, aprovada em 2026-11-10.

EVENT AGENDA deve permitir solicitar até 5, 10, 15 ou 20 resultados, com padrão 10, e ordenar por data ou relevância. A ordenação padrão é cronológica crescente pela data/hora de início do evento.

**Critérios de aceitação:**

- As opções de limite incluem 5, 10, 15 e 20, e a quantidade retornada não excede o limite solicitado.
- A pessoa usuária pode escolher ordenação cronológica crescente por data/hora de início ou por relevância.
- A quantidade retornada não excede o máximo selecionado ou o padrão 10.

**Rastreabilidade:** P-04, P-05.

### RF-017 — Apresentação de resultados de EVENT AGENDA

**Origem:** Confirmado pelo proprietário na decisão 7, aprovada em 2026-11-10.

Cada resultado de EVENT AGENDA deve apresentar nome, data/horário verificados quando disponíveis, local/venue real, descrição concisa e link original verificado para a fonte.

**Critérios de aceitação:**

- A apresentação inclui o nome, local/venue real, descrição concisa e link original verificado da fonte.
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
- A resposta distingue zero resultados verificados de descoberta incompleta causada por falha de fontes; não afirma ausência de notícias ou eventos quando a descoberta não pôde ser concluída.

**Rastreabilidade:** P-02, P-03, P-05.

### RF-019 — Cadastro, autenticação e acesso ao portal

**Origem:** Confirmado pelo proprietário na decisão 1, aprovada em 2026-11-10.

Toda pessoa precisa cadastrar-se e autenticar-se para usar o portal, com as opções aprovadas de e-mail e Google. Existem exatamente dois papéis de produto: Usuário/Consumer e Administrador.

**Critérios de aceitação:**

- Uma pessoa não autenticada não acessa as experiências do portal.
- Cadastro e autenticação por e-mail e Google permanecem disponíveis.
- Nenhum papel de produto adicional é introduzido.

**Rastreabilidade:** objetivo aprovado; [Usuários e Papéis](users-and-roles.md).

### RF-020 — Estado inicial e permissões de novas contas

**Origem:** Confirmado pelo proprietário na decisão 1, aprovada em 2026-11-10.

Toda nova conta de Usuário começa INACTIVE, sem permissão para NEWS ou EVENT AGENDA, até aprovação administrativa.

**Critérios de aceitação:**

- Uma nova conta permanece inativa e sem permissões de módulo até que um Administrador a altere.
- Conta inativa não pode usar o portal.

**Rastreabilidade:** [Usuários e Papéis](users-and-roles.md).

### RF-021 — Administração de contas e autorização de módulo

**Origem:** Confirmado pelo proprietário na decisão 1, aprovada em 2026-11-10.

Um Administrador pode ativar ou desativar individualmente cada conta e conceder ou retirar, de forma independente, acesso a NEWS e EVENT AGENDA, inclusive ambos ou nenhum. A autorização deve ser aplicada no backend, além de refletida na interface.

**Critérios de aceitação:**

- Cada módulo pode ser concedido ou revogado sem alterar a permissão do outro.
- Uma conta pode ter os dois módulos, um módulo ou nenhum.
- A API/servidor recusa operações de módulo não autorizado, mesmo quando solicitadas fora da interface.

**Rastreabilidade:** [Usuários e Papéis](users-and-roles.md).

### RF-022 — Bootstrap inicial do Administrador

**Origem:** Comportamento confirmado pelo proprietário na decisão 1, aprovada em 2026-11-10.

O primeiro Administrador deve ser criado manualmente por processo ou comando de gerenciamento seguro e controlado. Este requisito descreve o comportamento esperado; não autoriza nem especifica sua implementação nesta etapa.

**Critério de aceitação:**

- O primeiro Administrador não é criado por autoinscrição pública; sua criação ocorre por processo manual controlado.

**Rastreabilidade:** [Usuários e Papéis](users-and-roles.md); detalhes de implementação ficam para CONSTRUCTION.

### RF-023 — Busca iniciada pela pessoa usuária

**Origem:** Confirmado pelo proprietário na decisão 8, aprovada em 2026-11-10.

As buscas de NEWS e EVENT AGENDA são iniciadas sob demanda pela pessoa usuária; o MVP não executa rastreamento agendado automático.

**Critério de aceitação:**

- Uma consulta a fontes é iniciada em resposta a uma busca solicitada pela pessoa usuária, não por agenda de crawling periódico.

**Rastreabilidade:** MVP Scope.

### RF-024 — Idioma da interface e do conteúdo gerado

**Origem:** Confirmado pelo proprietário na decisão 3, aprovada em 2026-11-10.

A interface e o conteúdo conciso gerado devem oferecer português brasileiro e inglês; a descoberta pode consultar fontes públicas em qualquer idioma. O idioma de exibição acompanha o idioma selecionado na interface.

**Critérios de aceitação:**

- A interface e o conteúdo conciso podem ser exibidos em pt-BR e en-US.
- A descoberta não é restrita a fontes publicadas nesses dois idiomas.
- O conteúdo gerado acompanha o idioma da interface selecionado.

**Rastreabilidade:** MVP Scope.

### RF-025 — Transparência de uso de IA por geração

**Origem:** Confirmado pelo proprietário nas decisões 1 e 8, aprovadas em 2026-11-10.

Para cada geração de conteúdo, a pessoa usuária deve poder consultar o uso de IA associado, incluindo tokens e custo estimado quando disponível.

**Critério de aceitação:**

- Se conteúdo for servido integralmente do cache sem nova geração, o uso já registrado não aparece como consumo novo de tokens DeepSeek; chamadas reais de geração são exibidas como tais.

**Rastreabilidade:** MVP Scope.

### RF-026 — Relatório administrativo de uso e custo

**Origem:** Confirmado pelo proprietário na decisão 1, aprovada em 2026-11-10.

Administradores podem consultar relatórios por usuário de uso de IA, tokens e custo estimado. Essa capacidade não lhes concede moderação jornalística, configuração de provedores, cotas ou configurações operacionais gerais.

**Critério de aceitação:**

- Um relatório administrativo permite distinguir usuários e consultar tokens e custo estimado quando os dados de preço estiverem disponíveis.
- O escopo administrativo não inclui as capacidades explicitamente excluídas.

**Rastreabilidade:** [Usuários e Papéis](users-and-roles.md); MVP Scope.

### RF-027 — Registro de chamadas do modelo e distinção de custos

**Origem:** Confirmado pelo proprietário na decisão 8, aprovada em 2026-11-10.

Cada chamada real de geração registra usuário atuante, módulo, modelo, tokens de entrada, tokens de saída, total de tokens e custo estimado do LLM quando houver dados de preço. Consultas a Serper.dev ou Tavily não são tokens de LLM; eventual utilização ou custo desses provedores deve ser identificado separadamente.

**Critérios de aceitação:**

- Uma chamada real registra os campos especificados, distinguindo input e output.
- Custo não é inventado quando os dados de preço não estão disponíveis.
- Consultas de busca não são contabilizadas como tokens DeepSeek.

**Rastreabilidade:** MVP Scope.

### RF-028 — Deduplicação de EVENT AGENDA

**Origem:** Confirmado pelo proprietário na decisão 6, aprovada em 2026-11-10.

EVENT AGENDA deve evitar listar mais de uma vez a mesma ocorrência de evento.

**Critério de aceitação:**

- Listagens verificadas que descrevem a mesma ocorrência não aparecem como eventos distintos duplicados.

Detalhes de correspondência e deduplicação são decisões de CONSTRUCTION.

**Rastreabilidade:** P-05; MVP Scope.

## 4. Requisitos não funcionais

Os requisitos abaixo foram originalmente propostos pelo analista e aprovados pelo usuário como parte deste baseline, com as metas de desempenho e cache também confirmadas pelo proprietário na decisão 8. Critérios técnicos de implementação continuam para CONSTRUCTION.

### RNF-001 — Acessibilidade dos controles

**Origem:** Proposta analítica aprovada nesta revisão.

Os controles de mapa, modo, categoria, tópico, intervalo de datas, ordenação e links de resultados devem ser utilizáveis por teclado. Estados e mensagens não devem depender exclusivamente de cor.

**Critérios de aceitação:**

- Os controles interativos podem ser alcançados e acionados por teclado.
- O foco atual é perceptível.
- Seleções, estados de verificação e mensagens de insuficiência têm identificação textual além de cor.

O detalhamento do padrão de acessibilidade e das tecnologias assistivas usadas na validação fica para CONSTRUCTION.

### RNF-002 — Integridade da proveniência

**Origem:** Proposta analítica aprovada nesta revisão.

A apresentação de um resultado deve preservar a associação entre o item, a identificação da fonte e seu URL original verificado.

**Critérios de aceitação:**

- Em cada resultado de teste, o link exibido corresponde ao URL original verificado associado àquele item.
- A atribuição não é substituída por URL gerada ou por link de outro resultado.

### RNF-003 — Meta inicial de validação de desempenho

**Origem:** Confirmado pelo proprietário na decisão 8, aprovada em 2026-11-10.

Como meta inicial de validação, p95 deve ser menor ou igual a 120 segundos para até 10 resultados solicitados e até cinco usuários concorrentes sob condições normais de teste, avaliada separadamente para NEWS e EVENT AGENDA. Esta meta não é SLA nem garantia de latência e ainda não foi medida.

**Critérios de aceitação:**

- A validação mede p95 por modo sob as condições e o perfil descritos, até cinco usuários concorrentes e até 10 resultados.
- O relatório registra condições e valores observados; não declara a meta atendida sem medição.

### RNF-004 — Diferenciação entre ausência de resultados e falha de descoberta

**Origem:** Proposta analítica aprovada nesta revisão.

A apresentação deve distinguir “nenhum resultado verificado disponível” de uma consulta cuja descoberta tenha sido incompleta por indisponibilidade de fontes.

**Critérios de aceitação:**

- Em uma validação com fonte indisponível, o resultado não afirma que não há eventos/notícias quando a consulta foi incompleta.
- A indicação de indisponibilidade não é apresentada como resultado verificado.
- Fallback e comunicação de falha são especificados em RNF-006; seus detalhes de implementação permanecem para CONSTRUCTION.

### RNF-005 — Revalidação de cache e atribuição de chamadas

**Origem:** Confirmado pelo proprietário na decisão 8, aprovada em 2026-11-10.

Resultados de busca podem ser armazenados em cache por 10 minutos, preservando revalidação de timestamp e elegibilidade, separação por idioma e filtros, controles atuais de acesso e atribuição correta de chamadas reais aos provedores. Um cache hit não representa novo consumo de tokens DeepSeek.

**Critérios de aceitação:**

- A duração máxima configurada do cache de busca/resultado é 10 minutos.
- A chave/uso do cache não mistura idiomas, filtros ou autorizações incompatíveis.
- Timestamp e elegibilidade são revalidados ao apresentar resultado em cache.
- Um resultado de busca integralmente servido do cache não é atribuído a uma chamada nova do provedor; se houver nova chamada real ao provedor ou ao LLM, ela é registrada e atribuída normalmente.
- Conteúdo integralmente servido do cache sem nova geração não é atribuído como novo consumo de tokens DeepSeek.

Os detalhes de implementação do cache são para CONSTRUCTION.

### RNF-006 — Fallback transparente de busca

**Origem:** Confirmado pelo proprietário na decisão 8, aprovada em 2026-11-10.

Serper.dev é o provedor primário de busca; Tavily é o fallback quando Serper.dev apresenta erro ou indisponibilidade. Falha parcial deve ser identificada, sem declarar ausência de notícias/eventos quando a descoberta não pôde ser concluída.

**Critérios de aceitação:**

- Erro ou indisponibilidade do provedor primário pode acionar o fallback planejado.
- A resposta distingue falha parcial de zero resultados verificados.
- Consultas e custos de provedores de busca são identificados separadamente de tokens/custos de LLM.

O comportamento técnico de retry, seleção de fallback e comunicação detalhada fica para CONSTRUCTION.

## 5. Direção técnica planejada — não é arquitetura aprovada

A direção abaixo é apenas técnica e planejada. Ela não aprova arquitetura, responsabilidades de componentes ou implementação e não converte essas escolhas em requisitos funcionais:

- Python/Django, Django Ninja, HTMX, MapLibre GL JS e PostgreSQL/PostGIS.
- DeepSeek API como LLM primário, na direção planejada com Pydantic AI.
- Serper.dev como primário e Tavily como fallback em caso de erro/indisponibilidade do primário.
- Supabase PostgreSQL como ambiente de desenvolvimento local do MVP; seleção e configuração técnica permanecem para CONSTRUCTION.
- Vercel como possibilidade futura de hospedagem, pertencente a OPERATIONS, de responsabilidade humana.
- Redis opcional.
- LangGraph adiado; workflows LangGraph não fazem parte do MVP.
- RAG não planejado para o MVP.
- Desenvolver a API antes do frontend.

## 6. Registro de decisões e ressalvas de validação

As decisões originalmente indexadas como OD-01 a OD-14 foram resolvidas ou corretamente deferidas conforme o [registro de decisões INCEPTION](open-decisions.md). Não há decisão de produto pendente nesses itens. Referências geográficas sem limites verificáveis, fontes que não informam hora/duração, horários locais ambíguos e incerteza nos limites de intervalo são limitações de validação a informar; não autorizam inventar dados nem alteram os critérios aprovados. Heurísticas, pesos, taxonomias e mecanismos técnicos permanecem para CONSTRUCTION. A meta de desempenho de RNF-003 é inicial e não foi medida.

## 7. Limites de aprovação e etapa seguinte

Este baseline não aprova:

- Alterações aos artefatos aprovados de Problem Definition, Product Objective, Users and Roles ou MVP Scope; cada um conserva sua própria fonte autoritativa.
- Arquitetura ou implementação.
- Contratos formais.
- Uma especificação de CONSTRUCTION ou qualquer atividade de OPERATIONS.
