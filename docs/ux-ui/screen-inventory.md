# Inventário de telas — GeophNews

**Etapa:** Fase 01, Etapa 01.02.
**Status geral:** 14 owner decisions recorded; consolidated inventory reviewed and approved by owner.
**Em pt-BR:** 14 decisões do proprietário registradas; inventário consolidado revisado e aprovado pelo proprietário em 2026-11-17.

As 14 decisões individuais abaixo foram confirmadas explicitamente pelo proprietário em um único lote, com o vetor **1B, 2A, 3B, 4B, 5A, 6B, 7A, 8A, 9A, 10A, 11A, 12A, 13A, 14A**. A confirmação não foi coletada tela por tela. O status **APPROVED** em cada linha se aplica à decisão daquela entrada; o proprietário também revisou e aprovou o inventário consolidado em 2026-11-17.

Este documento define somente nomes, públicos, propósitos, domínios de informação em alto nível e fronteiras entre experiências. A indicação de público e os limites expressamente aprovados para as experiências públicas e de conta não definem política detalhada de acesso. Rotas, redirecionamentos e fronteiras detalhadas de acesso ficam para a Etapa 01.03; rótulos finais, formulários, layouts, responsividade, interações do mapa e wireframes ficam para as etapas de design correspondentes. Não há contrato de API, esquema ou decisão de implementação neste inventário.

## Resumo e mapeamento das decisões

Cada ID está listado uma vez. A coluna “Fronteira” identifica a experiência como autônoma, agrupada ou embutida; a justificativa registra a razão concreta da decisão confirmada.

| ID | Escolha | Nome canônico | Público-alvo | Propósito principal | Domínio de informação em alto nível | Fronteira / agrupamento | Justificativa da decisão | Status individual |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| S01 | 1B | Página inicial pública | Visitante público | Apresentar GeophNews, NEWS, EVENT AGENDA e descoberta geográfica por exemplos das experiências. | Apresentação do serviço, dos dois módulos e da relação com geografia; exemplos ilustrativos. | Autônoma e informativa; exemplos não são resultados públicos reais e não contêm alegações jornalísticas inventadas nem dão acesso não autenticado a recursos protegidos. | Explicar o produto sem confundir material de apresentação com resultados de consulta ou fabricar informação. | APPROVED |
| S02 | 2A | Login | Consumer/User e Administrator | Oferecer uma entrada compartilhada de autenticação e abrigar as experiências associadas de cadastro e recuperação. | Supabase Auth; autenticação por e-mail/senha ou Google; domínios de cadastro e recuperação. | Autônoma; agrupa as experiências de cadastro e recuperação, que mantêm IDs de inventário próprios. | Manter um ponto comum de autenticação para os dois papéis e organizar nele as experiências de conta relacionadas. | APPROVED |
| S03 | 3B | Cadastro | Consumer/User (nova conta) | Permitir que uma nova conta Consumer/User inicie o cadastro dentro da experiência de Login. | Criação de conta Consumer/User; estado inicial da conta e permissões NEWS/EVENT AGENDA. | Agrupada em S02; ID distinto para rastreabilidade, sem página autônoma; novas contas iniciam INACTIVE e sem permissão de módulo até ativação por Administrator; não há cadastro público de Administrator. | Preservar uma decisão rastreável para cadastro sem criar página própria e manter o estado inicial aprovado para novas contas. | APPROVED |
| S04 | 4B | Recuperação de senha | Consumer/User e Administrator | Permitir iniciar a recuperação de senha vinculada ao Supabase Auth dentro da experiência de Login. | Recuperação de acesso à conta vinculada ao Supabase Auth. | Agrupada em S02; ID distinto sem página autônoma; formulários, callbacks e rotas não são definidos aqui. | Registrar recuperação como experiência própria do inventário e mantê-la junto à entrada de autenticação que ela complementa. | APPROVED |
| S05 | 5A | Aguardando aprovação | Consumer/User com conta INACTIVE aguardando ativação por Administrator | Informar que a conta inativa do Consumer/User aguarda ativação por Administrator. | Estado inativo da conta e pendência de ativação administrativa. | Autônoma e informativa; não expõe informação protegida nem permite busca não autorizada. | Distinguir a espera por ativação da conta de uma restrição a um módulo em uma conta ativa. | APPROVED |
| S06 | 6B | Sem permissão para o módulo | Consumer/User ativo sem permissão para NEWS e/ou EVENT AGENDA solicitado | Informar, dentro do painel do usuário, que o módulo solicitado não está disponível para a conta ativa sem revelar conteúdo restrito. | Disponibilidade de módulo solicitada e informação de indisponibilidade. | Estado informativo embutido em S07 (Painel do usuário); não é autônomo, não se confunde com conta INACTIVE e não substitui a autorização obrigatória no backend; tratamento detalhado de acesso administrativo não é definido aqui. | Manter a explicação junto ao contexto do painel, sem vazar conteúdo, e separar permissão de módulo da ativação da conta. | APPROVED |
| S07 | 7A | Painel do usuário e mapa geográfico | Consumer/User | Reunir a exploração geográfica em mapa e os pontos de entrada para NEWS e EVENT AGENDA autorizados. | Mapa interativo, região selecionada, níveis geográficos de mundo, continente, país, estado/região, cidade ou bairro e disponibilidade conforme cobertura verificável. | Autônoma; contém o estado informativo de indisponibilidade de módulo. A interação detalhada do mapa fica para etapa posterior. | Colocar a geografia no centro da experiência de Consumer/User e permitir que ela seja o contexto dos módulos autorizados sem presumir cobertura não verificada. | APPROVED |
| S08 | 8A | Notícias — pesquisa e resultados | Consumer/User com permissão NEWS | Permitir consulta geográfica NEWS sob demanda e consulta de resultados verificados com atribuição à fonte original e transparência de uso por geração. | Contexto geográfico, consulta e resultados NEWS, janela móvel aprovada das últimas 24 horas, filtros aprovados, fonte original e tokens/custo estimado de LLM por geração. | Autônoma; mantém NEWS como experiência separada e preserva suas regras temporais e semântica de filtros aprovadas. | Tratar NEWS como experiência de primeira classe com critérios temporais próprios, contexto geográfico, rastreabilidade da fonte e transparência de geração. | APPROVED |
| S09 | 9A | Agenda de eventos — pesquisa e resultados | Consumer/User com permissão EVENT AGENDA | Permitir consulta geográfica sob demanda de eventos verificados em andamento ou futuros dentro do intervalo escolhido pelo usuário. | Intervalo de datas escolhido sem intervalo padrão, contexto geográfico, eventos atuais/futuros verificados, fonte original e uso de geração. | Autônoma; preserva as regras temporais e geográficas aprovadas de EVENT AGENDA, sem desenhar controles ou filtros. | Separar a experiência de eventos porque ela depende de um intervalo escolhido sem padrão e tem critérios temporais próprios, distintos de NEWS. | APPROVED |
| S10 | 10A | Painel do administrador | Administrator | Dar uma visão geral de contas pendentes, pontos de entrada para gestão de permissões e relatórios de uso de IA. | Contas aguardando aprovação, gestão de permissões e relatórios de uso de IA. | Autônoma; não inclui moderação editorial, configuração de provedores, quotas ou operações gerais. | Concentrar a visão geral administrativa nas responsabilidades aprovadas de contas, permissões e relatórios. | APPROVED |
| S11 | 11A | Lista de usuários | Administrator | Permitir consultar contas registradas e seus estados em uma visão geral separada do detalhe de cada conta. | Contas registradas e estados de conta em nível alto. | Autônoma e separada da experiência de detalhes e permissões. | Manter a consulta geral de contas distinta das decisões aplicadas a uma conta específica. | APPROVED |
| S12 | 12A | Detalhes e permissões do usuário | Administrator | Permitir consultar uma conta selecionada e gerenciar sua ativação e as permissões independentes de NEWS e EVENT AGENDA. | Informações da conta, estado ativo/inativo e permissões dos dois módulos. | Autônoma; não adiciona papéis ou configurações além das decisões aprovadas. | Reunir as decisões autorizadas por conta sem ampliar os papéis ou controles administrativos definidos. | APPROVED |
| S13 | 13A | Relatório agregado de consumo de IA | Administrator | Permitir analisar de forma agregada o uso de gerações DeepSeek por usuário e os tokens e custos estimados disponíveis. | Agregados por usuário de gerações DeepSeek, tokens e custo estimado quando disponível; uso/custo Serper/Tavily identificado separadamente. | Autônoma e agregada; não mistura tokens de LLM com chamadas ou custos de provedores de busca. | Dar uma visão agregada do consumo administrativo permitido sem confundir metering de modelo e de busca. | APPROVED |
| S14 | 14A | Detalhamento de consumo de IA por usuário | Administrator | Permitir consultar o uso de gerações de um usuário, por módulo, com tokens e custo estimado quando disponível. | Gerações de uma conta, módulos associados, tokens e custo estimado quando disponível; distinção entre uso de LLM e de busca. | Autônoma e individual; permanece separada do relatório agregado. | Oferecer detalhamento por usuário como consulta distinta da visão agregada e manter a atribuição do uso identificável. | APPROVED |

## Contagem aprovada

**14 IDs de inventário e experiências rastreáveis; 11 telas autônomas; duas experiências agrupadas no Login; um estado embutido no Painel do usuário.** Cadastro e recuperação são decisões rastreáveis dentro da experiência de Login; a indisponibilidade de módulo é um estado do painel, não uma página. Nenhuma experiência foi excluída ou duplicada.

## Referências aprovadas

- [Especificação da Etapa 01.02](<../../spec/p01-St01_02-screen-inventory(Done).md>)
- [Roadmap do projeto](../project-roadmap.md)
- [Usuários e Papéis](../ai-dlc/inception/users-and-roles.md)
- [Escopo do MVP](../ai-dlc/inception/mvp-scope.md)
- [Requisitos](../ai-dlc/inception/requirements.md)
- [Objetivo do Produto](../ai-dlc/inception/product-objective.md)
- [Arquitetura](../ai-dlc/architecture/architecture.md)
- [Identidade visual aprovada, dependência da Etapa 01.01](../visual-identity/README.md)

## Revisão final do artefato

- [x] As 14 decisões individuais foram explicitamente confirmadas pelo proprietário em lote e estão registradas como APPROVED.
- [x] A contagem distingue 11 telas autônomas de três experiências agrupadas ou embutidas.
- [x] O proprietário revisou o inventário consolidado e aprovou o artefato final.
- [x] A aprovação final do artefato foi registrada no decision log.

Status final: **14 owner decisions recorded; consolidated inventory reviewed and approved by owner**. A Etapa 01.02 está concluída.
