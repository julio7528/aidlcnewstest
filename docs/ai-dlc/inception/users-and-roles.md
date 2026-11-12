# Usuários e Papéis

> **Status: APPROVED — tipos de conta, autenticação, estados, permissões e limites administrativos descritos neste documento.** A aprovação das decisões aplicáveis foi confirmada em 2026-11-10.

## Propósito

Definir os dois tipos de conta do portal GeophNews e suas capacidades no MVP experimental. Esta definição cobre usuários do portal; agentes Codex de desenvolvimento não são papéis do produto.

## Perfis

### Usuário

- **Objetivo:** descobrir e consultar NEWS e EVENT AGENDA relevantes para uma localização.
- **Acesso:** somente pessoas cadastradas e autenticadas podem utilizar o portal. Cadastro e login estão disponíveis por e-mail ou conta Google. Toda nova conta começa INACTIVE e sem permissões NEWS ou EVENT AGENDA até aprovação do Administrador.
- **Interações esperadas:** utilizar NEWS e/ou EVENT AGENDA conforme as permissões concedidas à conta; pesquisar por localização, tópico e filtros de tempo apropriados; escolher a quantidade de resultados e consultar os resultados.
- **Necessidades mínimas:** ter uma conta ativa e permissão independente para cada experiência que deseja utilizar. A autorização é aplicada no backend, além da interface.

### Administrador

- **Objetivo:** gerenciar o estado e as permissões de acesso das contas de usuário.
- **Interações esperadas:** ativar ou desativar individualmente uma conta e conceder ou revogar de forma independente NEWS e EVENT AGENDA, inclusive ambos ou nenhum; consultar relatórios por usuário de uso de IA, tokens e custo estimado.
- **Necessidades mínimas:** poder consultar e alterar o estado e as permissões de acesso das contas e consultar relatórios de uso/custo por usuário.
- **Limite de responsabilidade:** não é responsável por moderação jornalística, configuração de provedores, cotas ou configurações operacionais gerais. OPERATIONS permanece sob responsabilidade humana.

## Matriz de papéis e capacidades

| Tipo de conta | NEWS | EVENT AGENDA |
|---|---|---|
| **Usuário** | Pode pesquisar e consultar quando a permissão NEWS estiver concedida à conta. | Pode pesquisar e consultar quando a permissão EVENT AGENDA estiver concedida à conta. |
| **Administrador** | Pode conceder ou retirar a permissão NEWS de uma conta de usuário. | Pode conceder ou retirar a permissão EVENT AGENDA de uma conta de usuário. |

O Administrador também pode definir uma conta como ativa ou inativa. Uma conta inativa não pode utilizar o portal, mesmo que permissões de módulo estejam registradas. O primeiro Administrador deve ser criado manualmente por processo ou comando de gerenciamento seguro e controlado; isso descreve o comportamento esperado e não implementa esse processo.

## Decisões confirmadas e detalhes para CONSTRUCTION

**Confirmado pelo proprietário:**

- Existem exatamente dois tipos de conta do portal: Usuário e Administrador.
- É necessário ter uma conta cadastrada para utilizar o site.
- O cadastro e o login podem usar e-mail ou uma conta Google.
- Novas contas de Usuário iniciam INACTIVE, sem permissão para nenhum dos módulos até aprovação administrativa.
- O Administrador pode ativar/desativar cada conta e conceder/revogar independentemente NEWS e EVENT AGENDA, inclusive ambas ou nenhuma.
- A autorização dos módulos e o estado ativo são impostos no backend, não apenas na interface.
- O primeiro Administrador é criado manualmente por processo ou comando de gerenciamento seguro e controlado.
- Administradores podem consultar relatórios de uso/tokens/custo estimado de IA por usuário; usuários podem ver uso da geração associada ao próprio resultado conforme os requisitos.
- Moderação jornalística, configuração de provedores, cotas e configurações operacionais gerais não são responsabilidades administrativas do produto.
- Agentes Codex de frontend, backend e QA apoiam o desenvolvimento; não são contas nem papéis do portal.

**Detalhes adiados para CONSTRUCTION:** o procedimento técnico seguro de bootstrap, os mecanismos de autenticação, o armazenamento das permissões e a forma de aplicar autorização no backend devem ser detalhados na etapa de arquitetura; os comportamentos acima já estão aprovados.

## Resumo de aceite das regras aprovadas

- [x] Permanecem exatamente dois tipos de conta: Usuário e Administrador.
- [x] Uma pessoa sem conta cadastrada e autenticada não pode utilizar o site.
- [x] Cadastro e login por e-mail e por conta Google estão descritos como opções de acesso.
- [x] O Usuário só utiliza NEWS e EVENT AGENDA conforme as permissões da sua conta.
- [x] Novas contas começam inativas e sem permissão para qualquer módulo.
- [x] O Administrador pode alterar o estado ativo/inativo e conceder ou revogar independentemente NEWS e EVENT AGENDA por usuário.
- [x] Uma conta inativa ou sem permissão para o módulo solicitado não pode usar esse módulo; o backend impõe a regra.
- [x] O primeiro Administrador é inicializado por processo manual controlado.
- [x] O Administrador pode consultar relatórios por usuário de tokens e custo estimado de IA, sem capacidades operacionais ou de moderação excluídas.
- [x] Agentes Codex de frontend, backend e QA permanecem distintos dos papéis e contas do portal.
