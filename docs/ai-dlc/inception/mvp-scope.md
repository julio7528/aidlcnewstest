# MVP Scope — GeophNews

> **STATUS: APPROVED — escopo e limites do MVP aprovados em 2026-11-10.**
> Esta aprovação define o escopo do produto; não aprova arquitetura, implementação
> ou tarefas de OPERATIONS.

## Referências autoritativas

- [Problem Definition](problem-definition.md) — problema aprovado e imutável.
- [Product Objective](product-objective.md) — objetivo de produto aprovado.
- [Requirements](requirements.md) — requisitos aprovados e critérios de aceitação.
- [Users and Roles](users-and-roles.md) — tipos de conta e permissões aprovados.
- [Decision resolution register](open-decisions.md) — resolução dos antigos OD-01 a OD-14.

## Incluído no MVP

### Experiências e consultas

- NEWS e EVENT AGENDA são experiências de primeira classe.
- As consultas são iniciadas pela pessoa usuária sob demanda; não há rastreamento agendado.
- Ambos os modos oferecem o catálogo de categorias aprovado e busca opcional por texto livre, com a semântica de interseção definida nos requisitos.
- NEWS usa a janela móvel das 24 horas anteriores à consulta, baseada exclusivamente no instante original de publicação verificado.
- EVENT AGENDA exige intervalo de datas inicial e final selecionado pela pessoa usuária, sem intervalo padrão.
- Cada modo permite selecionar um máximo de 5, 10, 15 ou 20 resultados, com padrão 10.
- NEWS é ordenado por relevância. EVENT AGENDA usa ordem cronológica ascendente por início como padrão e oferece ordenação por relevância.

### Geografia, idioma e apresentação

- Mapa mundial interativo e clicável com navegação mundo > continente > país > estado/região > cidade > bairro. A seleção pode terminar em qualquer nível e inclui sub-regiões elegíveis.
- A UI e o conteúdo conciso gerado suportam português brasileiro e inglês; a língua de exibição segue a língua selecionada na interface.
- A descoberta pode considerar fontes públicas em qualquer idioma.
- Limites e relações geográficas precisam ser verificáveis. O sistema não inventa bairros nem contenção geográfica quando as referências são insuficientes e informa a limitação.
- NEWS apresenta título fundamentado, teaser de aproximadamente duas linhas, descrição curta distinta, fonte identificável e link original verificado.
- EVENT AGENDA apresenta nome, data/horário verificado quando disponível, local real, descrição breve e link da fonte original.
- A atribuição e os limites de localização/tópico são preservados; resultados insuficientes e falhas de descoberta são distinguidos.

### Fontes e verificação

- A descoberta usa fontes públicas da internet.
- NEWS usa evidência de uma fonte jornalística identificável e confiável ou fonte primária/oficial autoritativa, sob as condições de verificação dos requisitos.
- EVENT AGENDA pode usar anúncios de organizadores, terceiros, pessoas comuns e redes sociais como pistas. A publicação de um evento requer a evidência proporcional definida nos requisitos.
- Notícias são relevantes à área quando ocorrem nela ou têm impacto direto verificável nela; endereço do publisher não basta.
- Eventos físicos e híbridos exigem venue físico verificado dentro da área selecionada. Eventos totalmente online só se qualificam quando a seleção geográfica é WORLD.
- Conteúdo, fatos, horários, venues, fontes e URLs não são inventados.

### Contas, permissões e uso de IA

- Há exatamente dois papéis do portal: Consumer/User e Administrator; cadastro e login são obrigatórios e mantêm e-mail e Google como opções.
- Novas contas de consumidores começam inativas e sem permissões NEWS ou EVENT AGENDA até aprovação administrativa.
- Administradores ativam/desativam contas e concedem/revogam independentemente cada permissão de modo. A autorização deve ser aplicada no backend.
- O primeiro administrador é provisionado manualmente por processo seguro e controlado, a ser implementado em etapa posterior.
- A pessoa usuária vê tokens e custo estimado, quando disponível, em cada geração de conteúdo. Administradores consultam relatórios por usuário de uso de IA e custo estimado.
- Uso de busca Serper/Tavily não é contabilizado como tokens de LLM; eventual custo de busca é identificado separadamente.

### Desempenho, cache e desenvolvimento

- Meta inicial de validação: p95 de até 120 segundos para no máximo 10 resultados, até cinco usuários concorrentes, em condições normais de teste, avaliada separadamente por modo. É uma meta de validação, não SLA.
- Cache de busca/resultados por 10 minutos, com revalidação temporal e de elegibilidade, isolamento por idioma/filtros e controles de acesso preservados. Cache hit não é contabilizado como nova geração DeepSeek.
- Serper.dev é o provedor de busca primário e Tavily é fallback para erro ou indisponibilidade do Serper. Falha parcial é informada; descoberta incompleta não é apresentada como ausência confirmada de resultados.
- DeepSeek é o LLM primário na direção técnica planejada com Pydantic AI. Chamadas reais de geração registram usuário, módulo, modelo, tokens de entrada/saída/total e custo estimado quando há dados de preços disponíveis.
- O ambiente de desenvolvimento do MVP é runtime local com Supabase PostgreSQL.

## Limites e itens fora do MVP

- Aplicativos móveis nativos.
- Rede social integrada, comentários, envio de eventos por consumidores ou venda de ingressos.
- Recomendações personalizadas com histórico.
- RAG, workflows LangGraph e artigos jornalísticos completos gerados.
- Crawling ou busca executados em agenda sem solicitação da pessoa usuária.
- Administração de moderação, configuração de provedores, cotas ou configurações operacionais gerais.
- Preços, credenciais, limites de gasto ou garantias de latência inventados ou codificados como premissas.
- Hospedagem ou operação em Vercel nesta atividade. Eventual hospedagem futura pertence a OPERATIONS e permanece sob responsabilidade humana.

Posts sociais podem servir como pistas de descoberta de eventos; isso não inclui rede social integrada nem publicação de fatos de evento sem verificação.

Os itens fora do MVP não são compromissos para versões futuras; qualquer inclusão posterior exige decisão e aprovação próprias.

## Direção técnica e fronteiras

Python/Django, Django Ninja, HTMX, MapLibre GL JS, PostgreSQL/PostGIS, Pydantic AI com DeepSeek, Serper.dev primário, Tavily como fallback, Redis opcional e API antes do frontend são direção técnica aprovada para planejamento, não arquitetura detalhada. LangGraph está adiado e RAG não está planejado para o MVP.

Seleção de fontes de mapas/geocodificação, decomposição de componentes, algoritmos, heurísticas de verificação e desenho de cache pertencem à arquitetura de CONSTRUCTION. Vercel e demais decisões de hospedagem/monitoramento permanecem em OPERATIONS, exclusivamente humana.
