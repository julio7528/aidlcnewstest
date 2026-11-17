# Especificação: Fase 01, etapa 01.01 — Identidade visual inicial

## Referência e estágios

- **Roadmap:** [Fase 01, feature Initial visual identity, etapa 01.01](../docs/project-roadmap.md).
- **INCEPTION:** excluído; requisitos e escopo aprovados são entradas.
- **CONSTRUCTION:** incluído; a etapa produz e valida artefatos de identidade visual.
- **OPERATIONS:** excluído e de responsabilidade humana.

## Objetivo e escopo

Estabelecer a identidade visual inicial do GeophNews. Esta especificação cobre exclusivamente a etapa 01.01; as demais etapas da Fase 01 serão tratadas em outro documento.

Inclui documentação e artefatos reutilizáveis em [docs/visual-identity](../docs/visual-identity/README.md). Exclui código de interface, contratos de API e implantação. A implementação das interfaces dependentes nas fases 10–14 exige aprovação separada dos designs detalhados pelo usuário.

## Processo de decisão da identidade visual

O usuário decide cada ponto da identidade. Antes de fechar cada tema, apresentar alternativas concretas ou referências pertinentes, explicar suas implicações e registrar a escolha expressa. Trabalhar por tema, permitindo revisão e iteração; não presumir aprovação por silêncio. Perguntas relacionadas podem ser agrupadas quando isso facilitar a decisão. O usuário pode fornecer referências e alterar decisões anteriores; atualizar a documentação e registrar os efeitos da revisão. Uma proposta permanece identificada como proposta até ser aprovada explicitamente.

Para cada decisão, registrar o tema, alternativas ou referências consideradas, escolha e justificativa informada, data, estado e vínculos com os arquivos pertinentes. Marcar lacunas como pendentes. A aprovação final do pacote depende de revisão explícita do usuário após todos os temas estarem documentados.

## Etapas

### 01.01 — Identidade visual inicial

- **Estágio:** CONSTRUCTION.
- **Objetivo:** produzir um pacote completo, documentado e reutilizável, decidido pelo usuário.
- **Trabalho:** definir com o usuário os atributos e direção da marca; paleta de cores e papéis, valores e combinações; direção de imagens, exemplos e assets; conceitos e variantes de logotipo, proporções, área de proteção, tamanhos e usos; famílias de fontes, pesos, alternativas e hierarquia tipográfica; estilo e conjunto de ícones, tamanhos e usos. Documentar aplicações, exemplos, restrições, acessibilidade, origem e condições de uso dos recursos externos, quando aplicáveis. Organizar os arquivos e suas versões em `docs/visual-identity/`, com índice e registro das decisões.
- **Dependências:** requisitos, escopo e arquitetura aprovados; escolhas do usuário para cada tema. A ordem dos temas pode ser ajustada com ele, preservando dependências entre escolhas.
- **Critérios de aceite:** todos os temas acima têm decisões explícitas do usuário, documentação e exemplos suficientes para uso posterior; assets acordados e referências estão acessíveis a partir do índice; pendências e direitos de uso são identificados; combinações de cores destinadas a texto e controles têm contraste verificado segundo os requisitos aprovados; o usuário revisou e aprovou o pacote final. Nenhum design é apresentado como aprovado antes da decisão expressa.
- **Validação:** revisar cobertura e rastreabilidade das decisões, abrir os links e inspecionar os assets, conferir os valores e combinações documentados e registrar resultados de contraste e limitações. Apresentar o pacote ao usuário para revisão e aprovação; corrigir e repetir as verificações após alterações relevantes. Registrar o resultado no log de decisões quando a etapa estiver concluída.
- **Estado:** concluída em 2026-11-17 após aprovação do usuário do pacote visual,
  incluindo os quatro logos PNG, as dez imagens geradas, os ícones e os
  wireframes desktop/mobile. A revisão final conferiu a presença e os metadados
  dos assets, os seis WOFF2 e suas licenças, os links da documentação e os
  contrastes registrados. O usuário identificou o ChatGPT como ferramenta de
  geração das imagens e logos; os termos aplicáveis não foram revisados e essa
  limitação está identificada em
  [image-assets.md](../docs/visual-identity/image-assets.md).

## Parâmetros de execução

Cada pedido de execução deve indicar as etapas ou sua quantidade e o máximo de subagentes simultâneos; zero significa nenhum. Executar somente etapas selecionadas e elegíveis, respeitando dependências e decisões do usuário. A criação desta especificação não inicia sua execução.
