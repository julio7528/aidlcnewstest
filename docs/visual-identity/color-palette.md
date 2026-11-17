# Propostas de paleta — GeophNews

**Estado: opção C escolhida e papéis da paleta definidos com o usuário em 2026-11-16.** As opções foram propostas a partir da direção aprovada: jornalística e geográfica, com equilíbrio, sobriedade e conexão entre lugares.

## Opções

### A — Cartografia editorial

| Papel conceitual | Cor | Intenção |
|---|---|---|
| Tinta azul-marinho | `#162B3A` | Base editorial, firme e confiável. |
| Papel quente | `#F3F0E8` | Superfícies acolhedoras com referência a mapas e páginas impressas. |
| Azul-petróleo suave | `#547A7A` | Ligações e elementos geográficos sem competir com o conteúdo. |
| Terracota discreta | `#B66D4D` | Destaques pontuais com calor visual moderado. |

**Implicação:** combina a linguagem editorial com referências cartográficas; o azul-petróleo dá a principal pista geográfica.

### B — Atlas terrestre

| Papel conceitual | Cor | Intenção |
|---|---|---|
| Verde profundo | `#203B35` | Sobriedade inspirada em território e paisagem. |
| Marfim | `#F4F1E8` | Superfície clara e neutra. |
| Verde-sálvia | `#658578` | Conexão, camadas e áreas geográficas. |
| Ocre fosco | `#B28A58` | Referência a relevo, papel e pontos de interesse. |

**Implicação:** torna a dimensão geográfica mais evidente e orgânica; reduz a associação imediata com a paleta tradicional de veículos jornalísticos.

### C — Redação contemporânea — escolhida como base

| Papel conceitual | Cor | Intenção |
|---|---|---|
| Grafite azulado | `#252E3B` | Estrutura editorial sólida e atual. |
| Cinza claro | `#F3F5F6` | Superfície limpa e neutra. |
| Azul de mapa | `#426D94` | Orientação geográfica e navegação. |
| Vermelho queimado | `#A24F4F` | Sinalização jornalística com menos intensidade que um vermelho vivo. |

**Implicação:** dá mais ênfase à leitura digital e à atualidade; a geografia aparece sobretudo pelo azul e pela aplicação em mapas.

## Papéis definidos

| Cor | Papel | Aplicação e limites |
|---|---|---|
| `#F3F5F6` — cinza claro | Fundo e superfície padrão da interface clara. | Base para páginas, áreas de leitura e superfícies de conteúdo. |
| `#252E3B` — grafite azulado | Texto principal, títulos e estrutura editorial; fundo de áreas escuras pontuais. | Em áreas grafite, usar `#F3F5F6` para texto. |
| `#426D94` — azul | Sinal geográfico. | Mapas, marcadores, regiões selecionadas e controles diretamente ligados à navegação geográfica. Não usar como cor padrão para todos os links e ações. Em mapas, seleção deve ter também contorno, rótulo ou outro sinal não cromático, pois as cores do mapa variam. |
| `#A24F4F` — vermelho queimado | Acento de marca. | Usar com moderação em detalhes de identidade e realces editoriais. Não codifica erro, aviso, sucesso ou ação destrutiva. |

Estados do sistema usam cores semânticas próprias, separadas das cores de marca. O usuário aprovou cinco tokens, apresentação suave e identificação textual em [semantic-colors.md](semantic-colors.md); estados e mensagens não dependem somente de cor, conforme RNF-001.

## Verificação de contraste

Razões calculadas para os pares de cor plana previstos. O usuário aprovou WCAG 2.2 AA: pelo menos 4,5:1 para texto comum, 3:1 para texto grande e 3:1 para informação visual necessária em controles e gráficos. Ver [semantic-colors.md](semantic-colors.md) para os pares semânticos aprovados.

| Primeiro plano | Fundo | Razão calculada | Uso previsto |
|---|---|---:|---|
| `#252E3B` | `#F3F5F6` | 12.53:1 | Texto principal e títulos na interface clara. |
| `#F3F5F6` | `#252E3B` | 12.53:1 | Texto em áreas grafite. |
| `#426D94` | `#F3F5F6` | 4.99:1 | Marcadores, contornos e controles geográficos em superfície clara. |
| `#F3F5F6` | `#426D94` | 4.99:1 | Texto em controle geográfico preenchido de azul, quando usado. |
| `#A24F4F` | `#F3F5F6` | 5.10:1 | Acento ou realce editorial em superfície clara. |

As razões cobrem apenas essas combinações planas; marcadores sobre tiles de mapas e outras imagens precisam de inspeção no contexto final. Contraste não substitui contorno, forma, rótulo, foco perceptível ou identificação textual.
