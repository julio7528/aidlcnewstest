# Prompt para prancha de ícones — GeophNews

## Direção aprovada e uso

- Estilo preenchido, escolhido pelo usuário.
- Tamanho de uso definido: 24×24 px na interface e 32×32 px nos controles do mapa.
- Gerar uma prancha transparente 4×4 com 16 células iguais; recortar os símbolos depois.
- Grafite `#252E3B` é a cor principal; azul `#426D94` aparece somente em elementos geográficos. Vermelho `#A24F4F` é um acento de marca, não uma cor para ícones funcionais ou estados.

## Prompt

```text
Crie uma única prancha quadrada de ícones para o GeophNews, com fundo realmente transparente e canal alfa. Organize exatamente 16 ícones preenchidos em uma grade regular 4×4, em ordem de leitura, da esquerda para a direita e de cima para baixo. Cada célula deve ter o mesmo tamanho; centralize um ícone por célula, com dimensões ópticas consistentes, a mesma margem interna ampla e sem encostar ou cruzar os limites das outras células. Não desenhe linhas de grade, caixas ou separadores. A imagem será recortada depois, então mantenha cada ícone isolado no centro de sua célula.

Desenhe, nesta ordem: 1) globo/world; 2) continente em um quadro cartográfico; 3) mapa de região com uma área selecionada; 4) marcador de localização; 5) cidade com edifícios; 6) bairro com casas e quadras; 7) rota conectando pontos geográficos; 8) camadas de mapa; 9) artigo de notícia; 10) calendário de evento; 11) relógio/faixa de horário; 12) local de evento em um edifício; 13) busca; 14) filtros; 15) documento com link para a fonte original; 16) perfil de usuário.

Use um estilo de ícones preenchidos, sólido, geométrico, simples e contemporâneo, com recortes negativos limpos e reconhecimento fácil em tamanho pequeno. Todos devem ter o mesmo peso visual, escala, alinhamento e acabamento. Use grafite azulado #252E3B como cor principal; use azul #426D94 somente em formas que representem geografia ou localização. Não use vermelho queimado #A24F4F nos ícones funcionais nem invente cores de estado. Nenhuma informação deve depender somente da cor. Sem contornos finos, gradientes, sombras, brilho, relevo, textura, perspectiva, texto, letras, números, nomes, logos ou ícones duplicados.

Exporte uma única imagem PNG quadrada em alta resolução, com transparência alfa real em todo o fundo e entre os ícones. Não simule transparência com fundo branco, preto ou quadriculado. Evite detalhes minúsculos; cada símbolo deve poder ser recortado como arquivo separado e usado normalmente a 24×24 px, com opção de 32×32 px nos controles do mapa.
```

Salvar a prancha original e, após o recorte, os arquivos individuais em `generated-images/icons/`.
