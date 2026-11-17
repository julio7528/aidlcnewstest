# Cores semânticas — GeophNews

**Estado: aprovada pelo usuário em 2026-11-17.** O usuário aprovou WCAG 2.2 AA, os cinco tokens abaixo e a apresentação A (fundo suave com tinta escura). A paleta de marca e suas regras estão em [color-palette.md](color-palette.md). As cores de estado permanecem separadas do azul geográfico `#426D94` e do acento de marca `#A24F4F`.

## Padrão de contraste aprovado

Alvo aprovado: WCAG 2.2 nível AA, com pelo menos 4,5:1 para texto comum, 3:1 para texto grande e 3:1 para informação visual necessária em controles e gráficos. Os critérios correspondentes são [1.4.3 Contrast (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html) e [1.4.11 Non-text Contrast](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html).

## Tokens semânticos aprovados

| Estado | Tinta para texto, ícone e contorno | Fundo suave | Uso |
| --- | --- | --- | --- |
| Sucesso | `#276749` | `#E8F3EB` | Operação concluída ou resultado confirmado. |
| Atenção | `#805500` | `#FFF4D6` | Condição que requer atenção ou ação. |
| Erro | `#A32925` | `#FCE9E7` | Falha, bloqueio ou resultado indisponível. É diferente do acento de marca `#A24F4F`. |
| Informação | `#1D6170` | `#E7F2F4` | Atualização informativa sem sucesso ou falha implícitos. |
| Neutro | `#4F5D6B` | `#ECEFF2` | Estado em andamento, aguardando ou sem classificação positiva/negativa. |

Manter mensagem textual e ícone junto à cor; nenhum estado será comunicado somente pela cor. A cor semântica não substitui conteúdo, rótulo ou ação.

## Duas apresentações para comparação

- **A — Suave (aprovada):** fundo claro da tabela acima, com tinta escura para texto, ícone e contorno. Tem menor peso visual e combina com a direção editorial sóbria.
- **B — Preenchida:** alternativa considerada, mas não selecionada como apresentação padrão; usar a tinta semântica como fundo e `#F3F5F6` como texto/ícone somente se uma mensagem futura exigir ênfase adicional.

As duas apresentações usam os mesmos tokens. A seleção define a apresentação padrão; situações de alta prioridade ainda podem usar um bloco preenchido, sempre com rótulo e ícone.

## Verificação de contraste

Razões recalculadas para cores planas. A coluna “superfície” usa o fundo claro aprovado `#F3F5F6`; a coluna “preenchida” usa essa mesma cor como texto sobre a tinta semântica.

| Estado | Tinta/fundo suave | Tinta/superfície aprovada | Texto claro/tinta preenchida |
| --- | ---: | ---: | ---: |
| Sucesso | 5,91:1 | 6,15:1 | 6,15:1 |
| Atenção | 5,96:1 | 5,97:1 | 5,97:1 |
| Erro | 6,19:1 | 6,62:1 | 6,62:1 |
| Informação | 6,14:1 | 6,41:1 | 6,41:1 |
| Neutro | 5,85:1 | 6,17:1 | 6,17:1 |

Combinações aprovadas da paleta-base, também recalculadas:

| Primeiro plano | Fundo | Razão |
| --- | --- | ---: |
| Grafite `#252E3B` | Cinza claro `#F3F5F6` | 12,53:1 |
| Azul geográfico `#426D94` | Cinza claro `#F3F5F6` | 4,99:1 |
| Acento de marca `#A24F4F` | Cinza claro `#F3F5F6` | 5,10:1 |
| Cinza claro `#F3F5F6` | Grafite `#252E3B` | 12,53:1 |
| Cinza claro `#F3F5F6` | Azul geográfico `#426D94` | 4,99:1 |
| Cinza claro `#F3F5F6` | Acento `#A24F4F` | 5,10:1 |

Os pares de cor plana listados superam o alvo de texto comum. A sobreposição de marcadores a tiles de mapa e fotos precisa de validação contextual nos wireframes; os resultados acima não afirmam contraste para fundos de imagem variáveis.

## Decisões registradas

1. WCAG 2.2 AA.
2. Apresentação suave A.
3. Cinco estados e respectivos códigos aprovados pelo usuário.
