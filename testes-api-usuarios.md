# 🧪 Plano e Casos de Teste — API de Gestão de Usuários (REST)

Este documento apresenta a suíte de testes funcionais e de validação de contrato para os endpoints de autenticação e gerenciamento de usuários, aplicando técnicas de **Particionamento de Equivalência** e **Análise de Valor Limite**.

- **Base URL:** `https://reqres.in/api`
- **Formato:** `JSON`
- **Autora:** Camila Almeida
- **Ferramentas sugeridas:** Postman / Robot Framework / Cypress

---

## 🎯 Escopo e Objetivo

Validar o comportamento esperado das operações CRUD (`GET`, `POST`, `PUT`, `DELETE`) e do fluxo de autenticação (`POST /login`), garantindo que os códigos de status HTTP, a estrutura do payload de resposta e o tratamento de erros estejam em conformidade com a especificação da API.

---

## 📋 Cenários de Teste

### CT-001: Listar usuários com paginação válida (Caminho Feliz)
- **Endpoint:** `GET /users?page=2`
- **Pré-condição:** Serviço disponível e acessível.
- **Passos:**
  1. Enviar uma requisição `GET` para `/users` informando o parâmetro `page=2`.
- **Resultado Esperado:**
  - Status Code: `200 OK`.
  - O corpo da resposta deve retornar o campo `"page": 2`.
  - A lista `"data"` deve conter objetos de usuário com os campos obrigatórios: `id`, `email`, `first_name`, `last_name` e `avatar`.

---

### CT-002: Buscar usuário específico inexistente (Teste Negativo)
- **Endpoint:** `GET /users/9999`
- **Pré-condição:** O ID `9999` não deve estar cadastrado na base.
- **Passos:**
  1. Enviar uma requisição `GET` para `/users/9999`.
- **Resultado Esperado:**
  - Status Code: `404 Not Found`.
  - O corpo da resposta deve retornar um objeto vazio `{}`.

---

### CT-003: Criar novo usuário com dados válidos
- **Endpoint:** `POST /users`
- **Payload:**
  ```json
  {
    "name": "Camila Almeida",
    "job": "QA Analyst"
  }