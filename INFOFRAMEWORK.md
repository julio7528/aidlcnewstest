# Informações do Framework

Este arquivo define a ordem de trabalho para configurar o framework e seguir
Spec-Driven Development com o AI DLC.

- Para a entrevista inicial que preenche os arquivos do projeto, seguir a sequência de `Setup.md`.

## Ordem de Execução

### 1. Definir a estrutura e o problema

- Definir a estrutura de `C:\dev\projeto\.codex` para configuração e agentes do Codex.
- Definir a estrutura de `C:\dev\projeto\contracts` para os contratos do projeto.
- Definir a estrutura de `C:\dev\projeto\.agents` para as skills do projeto.
- Preencher primeiro `C:\dev\projeto\docs\context.md` com o problema, o requisito principal e o objetivo do projeto.
- Registrar requisitos e decisões conforme a configuração do projeto começar, de acordo com `docs/decision-log.md`.

### 2. Definir a arquitetura

- Definir a arquitetura em `C:\dev\projeto\docs\context.md` antes de implementar funcionalidades.
- Atualizar o contexto de implementação usando evidências de `C:\dev\projeto\src`.
- Marcar como desconhecidos os detalhes ainda sem decisão ou evidência.

### 3. Executar o ciclo incremental

- Atualizar `C:\dev\projeto\docs\project-roadmap.md` com fases, funcionalidades e steps em tópicos, sem texto descritivo.
- Criar uma spec para uma fase do roadmap em `C:\dev\projeto\spec`.
- Indicar na spec quais estágios do AI DLC se aplicam àquela entrega.
- Solicitar a execução indicando quais steps da spec serão executados e o máximo de subagents simultâneos.
- Implementar somente os steps selecionados.
- Executar testes e validação para o trabalho de Construction solicitado.
- Apresentar o resultado final, incluindo os steps executados e as evidências de validação.
- Atualizar o roadmap e o contexto conforme o trabalho concluído.
- Repetir esse ciclo incremental conforme novas funcionalidades forem solicitadas.

## Estágios do AI DLC

1. **INCEPTION** - Requisitos, objetivos e definição do problema.
2. **CONSTRUCTION** - Arquitetura, implementação, testes e validação.
3. **OPERATIONS** - Implantação, monitoramento e evolução; etapa 100% humana.

Cada spec deve deixar claro quais estágios são usados e quais ficam fora do
escopo daquela entrega. Não é necessário executar todos os estágios em cada
incremento. Todas as decisões e ações de Operations pertencem às pessoas; o
Codex não executa tarefas dessa etapa.
