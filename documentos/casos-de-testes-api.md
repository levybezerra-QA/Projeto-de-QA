## 🔌 Testes de API / Back-end

Foi utilizado o [Fake store API](https://fakestoreapi.com/) para obtenção de API e Postman para testes da API.

### 👥 Endpoint (POST): `https://fakestoreapi.com/users`

#### 1. Caso de Uso: Criar um usuário com sucesso

* **Objetivo:** Garantir que um usuário seja cadastrado.
* **Verificações:**
  * Status Code deve ser `201 Created`.
* **Passos:**
  1. Digitar o endpoint ( https://fakestoreapi.com/users) no campo URL.
  2. Colocar o metodo: POST
  3. Vá no caminho body -> raw -> selecione a opção: JSON, copie esse bloco de código e altere apenas os valores.
  ```json
    {
      "id": 0,
      "username": "string",
      "email": "string",
      "password": "string"
    }
  ```
  3. Clicar em "Send"
* **Estrutura do Retorno Esperado (JSON):**

```json
{
  "id": 0,
  "username": "string",
  "email": "string",
  "password": "string"
}
```

* **Estrutura do Resultado Obtido (JSON):**

```json
{
  "id": 0,
  "username": "string",
  "email": "string",
  "password": "string"
}
```

**Observação:** Após testes com a API, não é mais possível criar novos usuários, só utilizamos os que já estão criados. Deixei o tópico anterior conforme a documentação.

### 👥 Endpoint (GET): `https://fakestoreapi.com/users/{id}`

#### 2. Caso de Uso: Pesquisar usuário

* **Objetivo:** fazer pesquisas de um usuário cadastrado.
* **Verificações:**
  * Status Code deve ser `200 OK`.
  <!-- * A resposta deve conter uma propriedade `token`. -->
* **Passos:**
  1. Digitar o endpoint ( https://fakestoreapi.com/users/{id} ) no campo URL.
  2. Colocar o metodo: GET
  3. Vá no caminho body -> raw  -> selecione a opção: javascript, copie esse bloco de código e cole no campo, modifique o {id} para algum usuário cadastrado.

  ```javascript
    fetch('https://fakestoreapi.com/users/{id}')
      .then(response => response.json())
      .then(data => console.log(data));
  ```

  4. Clicar em "Send"

* **Estrutura do Retorno Esperado (JSON):**

```json
{
  "id": 0,
  "username": "string",
  "email": "string",
  "password": "string"
}
```

* **Estrutura do Resultado Obtido (JSON):**

```json
{
  "address": {
      "geolocation": {
          "lat": "-37.3159",
          "long": "81.1496"
      },
      "city": "kilcoole",
      "street": "new road",
      "number": 7682,
      "zipcode": "12926-3874"
  },
  "id": 1,
  "email": "john@gmail.com",
  "username": "johnd",
  "password": "m38rmF$",
  "name": {
      "firstname": "john",
      "lastname": "doe"
  },
  "phone": "1-570-236-7033",
  "__v": 0
}
```

**Observação:** Conforme dito anteriormente, os retornos estão diferentes do que está na documentação oficial. Mas a feature está funcionando.

### 👥 Endpoint (POST): `https://fakestoreapi.com/auth/login`

#### 3. Caso de Uso: Login com sucesso

* **Objetivo:** Garantir que um usuário cadastrado consiga se autenticar.
* **Verificações:**
  * Status Code deve ser `200 OK`.
  * A resposta deve conter uma propriedade `token`.
* **Passos:**
  1. Digitar o endpoint ( https://fakestoreapi.com/auth/login ) no campo URL.
  2. Colocar o metodo: POST
  3. Vá no caminho body -> raw  -> selecione a opção: json, copie esse bloco de código e cole no campo, e modifique com informações do usuario anteriormente cadastrado.
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```
  3. Clicar em "Send"
* **Estrutura do Retorno Esperado (JSON):**

```json
{
  "token": "string"
}
```

* **Estrutura do Resultado Obtido (JSON):**

```json
{
  "token": "string"
}
```

### 👥 Endpoint (GET): `https://fakestoreapi.com/users/`

#### 4. Caso de Uso: Pesquisar por todos os usuários

* **Objetivo:** fazer pesquisas de todos os usuários cadastrados.
* **Verificações:**
  * Status Code deve ser `200 OK`.
  <!-- * A resposta deve conter uma propriedade `token`. -->
* **Passos:**
  1. Digitar o endpoint ( https://fakestoreapi.com/users/ ) no campo URL.
  2. Colocar o metodo: GET
  3. Vá no caminho body -> raw  -> selecione a opção: javascript, copie esse bloco de código e cole no campo.

  ```javascript
    fetch('https://fakestoreapi.com/users')
      .then(response => response.json())
      .then(data => console.log(data));
  ```

  4. Clicar em "Send"

* **Estrutura do Retorno Esperado (JSON):**

```json
[
  {
    "id": 0,
    "username": "string",
    "email": "string",
    "password": "string"
  }
]
```

* **Estrutura do Resultado Obtido (JSON):**

```json
[
  {
    "id": 0,
    "username": "string",
    "email": "string",
    "password": "string"
  }
]
```

**Observação:** Conforme dito anteriormente, os retornos estão diferentes do que está na documentação oficial. Mas a feature está funcionando.