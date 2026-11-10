# Usuários e Papéis

> **Status: APPROVED — limitado aos tipos de conta, acesso ao portal e permissões descritos neste documento.**

## Propósito

Definir os dois tipos de conta do portal GeophNews e suas capacidades no MVP experimental. Esta definição cobre usuários do portal; agentes Codex de desenvolvimento não são papéis do produto.

## Perfis

### Usuário

- **Objetivo:** descobrir e consultar NEWS e EVENT AGENDA relevantes para uma localização.
- **Acesso:** somente pessoas com conta cadastrada podem utilizar o site. O cadastro de usuário pode ser feito com e-mail ou conta Google; o login pode ser feito por e-mail ou conta Google.
- **Interações esperadas:** utilizar NEWS e/ou EVENT AGENDA conforme as permissões concedidas à conta; pesquisar por localização, tópico e filtros de tempo apropriados; escolher a quantidade de resultados e consultar os resultados.
- **Necessidades mínimas:** ter uma conta e acesso autorizado às experiências que deseja utilizar.

### Administrador

- **Objetivo:** gerenciar o estado e as permissões de acesso das contas de usuário.
- **Interações esperadas:** definir se uma conta está ativa ou inativa e conceder acesso a NEWS, EVENT AGENDA ou ambos; desativar uma conta quando necessário.
- **Necessidades mínimas:** poder consultar e alterar o estado e as permissões de acesso das contas de usuário.
- **Limite de responsabilidade:** não é responsável por moderação, configuração de provedores, cotas ou painéis operacionais. A configuração de provedores cabe ao back-end.

## Matriz de papéis e capacidades

| Tipo de conta | NEWS | EVENT AGENDA |
|---|---|---|
| **Usuário** | Pode pesquisar e consultar quando a permissão NEWS estiver concedida à conta. | Pode pesquisar e consultar quando a permissão EVENT AGENDA estiver concedida à conta. |
| **Administrador** | Pode conceder ou retirar a permissão NEWS de uma conta de usuário. | Pode conceder ou retirar a permissão EVENT AGENDA de uma conta de usuário. |

O Administrador também pode definir uma conta de usuário como ativa ou inativa. Uma conta inativa não pode utilizar o site.

## Confirmado e ainda não definido

**Confirmado pelo proprietário:**

- Existem exatamente dois tipos de conta do portal: Usuário e Administrador.
- É necessário ter uma conta cadastrada para utilizar o site.
- O cadastro e o login podem usar e-mail ou uma conta Google.
- O Administrador controla o estado ativo/inativo das contas e o acesso de cada usuário a NEWS, EVENT AGENDA ou ambos; pode desativar usuários quando necessário.
- Moderação, configuração de provedores, cotas e painéis operacionais não são responsabilidades do Administrador. A configuração de provedores cabe ao back-end.
- Agentes Codex de frontend, backend e QA apoiam o desenvolvimento; não são contas nem papéis do portal.

**Ainda requer definição do proprietário:**

- Como uma conta de Administrador é criada ou recebe esse tipo de conta.
- Qual será o estado inicial de uma nova conta de usuário e quais permissões NEWS/EVENT AGENDA ela receberá por padrão.

## Verificações de aceite para a revisão de requisitos

- [ ] Permanecem exatamente dois tipos de conta: Usuário e Administrador.
- [ ] Uma pessoa sem conta cadastrada não pode utilizar o site.
- [ ] Cadastro e login por e-mail e por conta Google estão descritos como opções de acesso.
- [ ] O Usuário só utiliza NEWS e EVENT AGENDA conforme as permissões da sua conta.
- [ ] O Administrador pode alterar o estado ativo/inativo e conceder acesso a NEWS, EVENT AGENDA ou ambos por usuário.
- [ ] Uma conta inativa não pode utilizar o site.
- [ ] O escopo do Administrador não inclui moderação, configuração de provedores, cotas ou painéis operacionais.
- [ ] A criação de contas de Administrador e os valores padrão para novas contas de usuário são definidos antes de detalhar os requisitos correspondentes.
- [ ] Agentes Codex de frontend, backend e QA permanecem distintos dos papéis e contas do portal.
