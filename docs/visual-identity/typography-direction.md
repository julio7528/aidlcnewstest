# Direção tipográfica — GeophNews

## Direção e famílias escolhidas

- **Data das escolhas:** 2026-11-17.
- **Direção:** Editorial — títulos serifados e leitura/interface em sem serifa.
- **Source Serif 4:** H1 em 700; H2 e títulos de cards em 600.
- **Source Sans 3:** corpo em 400; navegação em 500; botões em 600. Subtítulos, rótulos, filtros e metadados usam 400 por padrão, salvo quando a hierarquia exigir papel já definido de navegação ou botão.
- **Itálico:** reservado a citações; aplicar à família do trecho citado.
- **Espaçamento entre letras:** padrão, sem tracking adicional.

## Hierarquia e escala

| Nível | Família e peso | Telas maiores | Celular |
|---|---|---:|---:|
| H1 / título de página | Source Serif 4 700 | 40–48 px | 32–36 px |
| H2 / título de seção | Source Serif 4 600 | 28–32 px | 24–28 px |
| Título de notícia/evento | Source Serif 4 600 | 20–24 px | 18–22 px |
| Corpo | Source Sans 3 400 | 16–18 px | 16 px |
| Navegação | Source Sans 3 500 | A refinar em wireframes | A refinar em wireframes |
| Botões | Source Sans 3 600 | A refinar em wireframes | A refinar em wireframes |
| Subtítulos, rótulos, filtros e metadados | Source Sans 3 400 por padrão | A refinar em wireframes | A refinar em wireframes |

Os valores móveis enviados como “3236”, “2428” e “1822” foram interpretados como intervalos 32–36, 24–28 e 18–22 px. São pontos de partida e podem ser refinados nos wireframes. Altura de linha, quebras de título e tamanhos de navegação/botões também serão verificados nos wireframes.

## Idiomas e fallbacks

- **Idiomas:** usar as mesmas famílias e escala em pt-BR e en-US; permitir que as linhas quebrem naturalmente.
- **Glifos:** incluir a cobertura Latin Extended para caracteres de português, como acentos e cedilha, e validar textos nos dois idiomas.
- **Fallback serifado aprovado:** `"Source Serif 4", Georgia, "Times New Roman", serif`.
- **Fallback sem serifa aprovado:** `"Source Sans 3", system-ui, -apple-system, "Segoe UI", Arial, sans-serif`.

## Distribuição, pesos e licenças

- **Hospedagem:** local no projeto, em arquivos WOFF2.
- **Carregamento:** incluir somente os pesos efetivamente usados e configurar `font-display: swap`.
- **Pesos iniciais previstos:** Source Serif 4 600 e 700; Source Sans 3 400, 500 e 600. Incluir itálico apenas quando necessário para citações.
- **Citações:** Source Serif 4 Italic 400.
- **Tamanho óptico:** usar automaticamente o eixo `opsz` do Source Serif 4 quando compatível.
- **Metadados oficiais consultados em 2026-11-17:** ambas as famílias declaram licença SIL Open Font License 1.1 e subset `latin-ext`. Source Serif 4 publica eixo de peso 200–900 e eixo óptico; Source Sans 3 publica eixo de peso 200–900.
- **Fontes oficiais:** [Source Serif 4 — metadados](https://github.com/google/fonts/blob/main/ofl/sourceserif4/METADATA.pb), [Source Serif 4 — licença](https://github.com/google/fonts/blob/main/ofl/sourceserif4/OFL.txt), [Source Sans 3 — metadados](https://github.com/google/fonts/blob/main/ofl/sourcesans3/METADATA.pb), [Source Sans 3 — licença](https://github.com/google/fonts/blob/main/ofl/sourcesans3/OFL.txt).
- **Estado da validação:** seis WOFF2 foram obtidos das fontes oficiais, inspecionados quanto à assinatura, família, eixos e cobertura de acentos pt-BR; as licenças OFL estão junto aos arquivos em [fonts/](fonts/README.md). Expor somente os pesos aprovados. O tamanho óptico automático e Source Serif 4 Italic 400 para citações foram aprovados.

## Estado

As escolhas de direção, famílias, pesos principais, itálico, tamanho óptico, escala inicial, fallbacks, idiomas e carregamento estão registradas. Os WOFF2 regulares e itálicos foram validados. A aplicação tipográfica mostrada nos wireframes foi aprovada pelo usuário em 2026-11-17; a revisão final do pacote de identidade visual continua pendente.
