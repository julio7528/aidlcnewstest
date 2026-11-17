# Arquivos de fontes — GeophNews

## WOFF2 validados

Arquivos obtidos em 2026-11-17 pelo CSS oficial do Google Fonts para Source Serif 4 e Source Sans 3. Os binários são fontes variáveis; a configuração futura deve expor somente Source Serif 4 em 600 e 700 e Source Sans 3 em 400, 500 e 600. O usuário aprovou o tamanho óptico automático e Source Serif 4 Italic 400 para citações.

| Arquivo | Família e subset | Eixos lidos do arquivo | Tamanho |
| --- | --- | --- | ---: |
| `source-sans-3-latin.woff2` | Source Sans 3, Latin | `wght` 200–900 | 28.2 KiB |
| `source-sans-3-latin-ext.woff2` | Source Sans 3, Latin Extended | `wght` 200–900 | 58.7 KiB |
| `source-serif-4-latin.woff2` | Source Serif 4, Latin | `wght` 200–900; `opsz` 8–60 | 119.5 KiB |
| `source-serif-4-latin-ext.woff2` | Source Serif 4, Latin Extended | `wght` 200–900; `opsz` 8–60 | 98.5 KiB |
| `source-serif-4-italic-latin.woff2` | Source Serif 4 Italic 400, Latin | itálico 400; `opsz` 8–60 | 49.4 KiB |
| `source-serif-4-italic-latin-ext.woff2` | Source Serif 4 Italic 400, Latin Extended | itálico 400; `opsz` 8–60 | 42.9 KiB |

## Resultado da validação

- Os seis arquivos têm a assinatura WOFF2 `wOF2` e foram analisados com FontTools.
- O CSS oficial associa os binários às famílias aprovadas. A instância nomeada dentro do Source Sans 3 é “ExtraLight”; seu eixo variável `wght` cobre 200–900, então o CSS futuro deve declarar os pesos escolhidos explicitamente. Source Serif 4 contém os eixos `wght` e `opsz`.
- A união dos subsets Latin e Latin Extended contém as letras acentuadas necessárias ao texto pt-BR de validação nos estilos regular e itálico. O conjunto também cobre o alfabeto latino usado em en-US.
- Os pesos selecionados pela identidade estão disponíveis nos eixos; o binário variável inclui outros pesos, que não precisam ser expostos no CSS.
- As licenças SIL Open Font License 1.1 foram preservadas em `OFL-source-sans-3.txt` e `OFL-source-serif-4.txt`.
- `font-display: swap` permanece a escolha aprovada para a implementação futura.

O tamanho óptico automático está aprovado para Source Serif 4 regular e itálico. Source Serif 4 Italic usa o eixo `opsz` 8–60 e peso fixo 400.

## Integridade

SHA-256 dos seis WOFF2 recebidos do Google Fonts:

| Arquivo | SHA-256 |
| --- | --- |
| `source-sans-3-latin.woff2` | `19143dca075972bc84e3fd9eab7416dd40cc565dccb2435a044bdfabe060c7d5` |
| `source-sans-3-latin-ext.woff2` | `a85a7459bdb3cdc1136751e151a506bae653fc29ada3ca86237477df6f1b59e6` |
| `source-serif-4-latin.woff2` | `f2ea9c12d2fe9bd3a9589b02ad2c0909da88f30938c91adc838c4f4098f9f9e0` |
| `source-serif-4-latin-ext.woff2` | `155f6e701097cc269cf8d5d7ac86795f263f1afbeb47c14d1d747108c9335389` |
| `source-serif-4-italic-latin.woff2` | `e940d556347366d68322f128c89b05a1840da4622c9872b5c2352e3a3410fe25` |
| `source-serif-4-italic-latin-ext.woff2` | `c753bdc17331492d80053b375764955f5983fe1818eeaaa108ed57142bdabb43` |

## Fontes oficiais

- [CSS oficial do Google Fonts para os pesos selecionados](https://fonts.googleapis.com/css2?family=Source+Serif+4:opsz,wght@8..60,600;8..60,700&family=Source+Sans+3:wght@400;500;600&display=swap)
- [CSS oficial do Google Fonts para Source Serif 4 Italic 400](https://fonts.googleapis.com/css2?family=Source+Serif+4:ital,opsz,wght@1,8..60,400&display=swap)
- [Source Serif 4 — metadados](https://github.com/google/fonts/blob/main/ofl/sourceserif4/METADATA.pb) e [licença OFL](https://github.com/google/fonts/blob/main/ofl/sourceserif4/OFL.txt).
- [Source Sans 3 — metadados](https://github.com/google/fonts/blob/main/ofl/sourcesans3/METADATA.pb) e [licença OFL](https://github.com/google/fonts/blob/main/ofl/sourcesans3/OFL.txt).
