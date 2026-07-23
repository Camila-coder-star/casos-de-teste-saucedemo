# Casos de Teste - SauceDemo

## Desafio 03 - Escrevendo Casos de Teste no Formato Step-by-Step

**Sistema sob teste:** https://www.saucedemo.com

---

# TC-001

## Funcionalidade
Login

### Título
Realizar login com credenciais válidas

### Pré-condições
- Estar na página inicial do SauceDemo.
- Possuir as credenciais:
  - Usuário: **standard_user**
  - Senha: **secret_sauce**

### Prioridade
Alta

### Passos

1. Acessar https://www.saucedemo.com.
2. Informar **standard_user** no campo **Username**.
3. Informar **secret_sauce** no campo **Password**.
4. Clicar no botão **Login**.

### Resultado esperado

- O login deverá ser realizado com sucesso.
- O sistema deverá redirecionar o usuário para a página **Products**.
- A lista de produtos deverá ser exibida.

### Técnica de Design

**Particionamento de Equivalência**

**Justificativa:** Este cenário representa a partição de credenciais válidas, na qual o sistema deve permitir o acesso.

---

# TC-002

## Funcionalidade
Login

### Título
Validar login com usuário bloqueado

### Pré-condições

- Estar na página inicial do SauceDemo.
- Possuir as credenciais:
  - Usuário: **locked_out_user**
  - Senha: **secret_sauce**

### Prioridade

Alta

### Passos

1. Acessar https://www.saucedemo.com.
2. Informar **locked_out_user** no campo **Username**.
3. Informar **secret_sauce** no campo **Password**.
4. Clicar no botão **Login**.

### Resultado esperado

- O login não deverá ser realizado.
- O sistema deverá exibir a mensagem:

> Epic sadface: Sorry, this user has been locked out.

### Técnica de Design

**Particionamento de Equivalência**

**Justificativa:** Este cenário representa a partição de usuários bloqueados, onde o sistema deve impedir a autenticação.

---

# TC-003

## Funcionalidade
Login

### Título
Validar login sem informar o usuário

### Pré-condições

- Estar na página inicial do SauceDemo.

### Prioridade

Alta

### Passos

1. Acessar https://www.saucedemo.com.
2. Deixar o campo **Username** em branco.
3. Informar **secret_sauce** no campo **Password**.
4. Clicar no botão **Login**.

### Resultado esperado

- O login não deverá ser realizado.
- O sistema deverá exibir a mensagem:

> Epic sadface: Username is required.

### Técnica de Design

**Particionamento de Equivalência**

**Justificativa:** Este cenário representa a partição de dados obrigatórios não informados.

---

# TC-004

## Funcionalidade
Carrinho de Compras

### Título
Adicionar produto ao carrinho

### Pré-condições

- Usuário autenticado utilizando **standard_user**.

### Prioridade

Alta

### Passos

1. Efetuar login no sistema.
2. Localizar o produto **Sauce Labs Fleece Jacket**.
3. Clicar no botão **Add to cart**.
4. Verificar se o botão foi alterado para **Remove**.
5. Clicar no ícone do carrinho.

### Resultado esperado

- O produto deverá estar listado no carrinho.
- O contador do carrinho deverá apresentar o número **1**.

---

# TC-005

## Funcionalidade
Carrinho de Compras

### Título
Remover produto do carrinho

### Pré-condições

- Usuário autenticado.
- Possuir pelo menos um produto adicionado ao carrinho.

### Prioridade

Alta

### Passos

1. Acessar o carrinho de compras.
2. Confirmar que existe um produto listado.
3. Clicar no botão **Remove**.

### Resultado esperado

- O produto deverá ser removido do carrinho.
- O contador do carrinho não deverá mais ser exibido, caso não existam outros produtos.

---

# TC-006

## Funcionalidade
Carrinho de Compras

### Título
Validar atualização do contador do carrinho

### Pré-condições

- Usuário autenticado utilizando **standard_user**.

### Prioridade

Alta

### Passos

1. Efetuar login.
2. Adicionar cinco produtos ao carrinho.
3. Observar o contador exibido no ícone do carrinho.
4. Acessar o carrinho.

### Resultado esperado

- O contador do carrinho deverá apresentar o número **5**.
- Os cinco produtos deverão estar listados no carrinho.

---

# TC-007

## Funcionalidade
Ordenação de Produtos

### Título
Ordenar produtos por Nome (A → Z)

### Pré-condições

- Usuário autenticado e posicionado na página **Products**.

### Prioridade

Alta

### Passos

1. Localizar o menu de ordenação de produtos.
2. Selecionar a opção **Name (A to Z)**.
3. Observar a ordem dos produtos apresentados.

### Resultado esperado

- Os produtos deverão ser exibidos em ordem alfabética crescente.
- O primeiro produto deverá ser **Sauce Labs Backpack**.

---

# TC-008

## Funcionalidade
Ordenação de Produtos

### Título
Ordenar produtos por Preço (Menor → Maior)

### Pré-condições

- Usuário autenticado e posicionado na página **Products**.

### Prioridade

Alta

### Passos

1. Localizar o menu de ordenação de produtos.
2. Selecionar a opção **Price (Low to High)**.
3. Observar a ordem dos preços apresentados.

### Resultado esperado

- Os produtos deverão ser exibidos em ordem crescente de preço.
- O primeiro produto deverá ser o de menor valor disponível no catálogo.

---

# Considerações Finais

Os casos de teste foram elaborados seguindo o formato **Step-by-Step**, garantindo clareza, objetividade e reprodutibilidade.

Nos cenários da funcionalidade **Login** foi aplicada a técnica de **Particionamento de Equivalência**, contemplando um cenário positivo e dois cenários negativos, conforme solicitado no desafio.

As funcionalidades de **Carrinho de Compras** e **Ordenação de Produtos** foram cobertas com cenários representativos dos principais fluxos de utilização do sistema.
