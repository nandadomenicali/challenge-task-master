# Desafio: Desenvolvimento de uma API REST para Gerenciamento de Tarefas ✅

## 📌 Objetivo
O desafio consiste em desenvolver uma API REST para um **sistema de gerenciamento de tarefas**. A API permitirá que os usuários criem, atualizem, excluam e listem tarefas de forma simples.

## 🎯 Requisitos Funcionais
- Criar endpoints para:
  - Criar uma nova tarefa.
  - Listar todas as tarefas.
  - Atualizar uma tarefa existente.
  - Excluir uma tarefa.
  - Buscar uma tarefa pelo ID.

## 🛠️ Tecnologias e Ferramentas
- **Linguagem:** Java 21
- **Framework:** Spring Boot 3
- **Banco de Dados:** H2 (banco em memória para facilitar o aprendizado)
- **Gerenciador de Dependências:** Maven ou Gradle
- **Documentação:** Swagger / OpenAPI
- **Testes:** JUnit 5
- **Spring Data JPA** – Para facilitar a manipulação do banco de dados.
- **Spring Validation** – Para validar dados da requisição, como obrigatoriedade de título.
- **Spring Actuator** – Para visualizar métricas básicas da aplicação.
- **Spring DevTools** – Para facilitar o desenvolvimento com reload automático.
- **Spring Boot Exception Handling** – Para personalizar mensagens de erro.

## 🗄️ Como Instalar o Banco de Dados H2
1. O H2 já vem configurado no Spring Boot e não exige instalação separada.
2. No `application.properties`, configure a conexão com o H2:
   ```properties
   spring.datasource.url=jdbc:h2:mem:testdb
   spring.datasource.driverClassName=org.h2.Driver
   spring.datasource.username=sa
   spring.datasource.password=
   spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
   spring.h2.console.enabled=true
   ```
3. Para acessar o console do banco H2, inicie a aplicação e acesse:
   ```
   http://localhost:8080/h2-console
   ```
   Use os seguintes dados para login:
   - **JDBC URL:** `jdbc:h2:mem:testdb`
   - **User:** `sa`
   - **Password:** (deixe em branco)

## 📡 Endpoints da API
### 1️⃣ Criar uma nova tarefa
```http
POST /api/tarefas
```
**Corpo da requisição:**
```json
{
  "titulo": "Estudar Spring Boot",
  "descricao": "Ler a documentação oficial e fazer exercícios."
}
```
**Resposta:**
```json
{
  "id": 1,
  "titulo": "Estudar Spring Boot",
  "descricao": "Ler a documentação oficial e fazer exercícios."
}
```

### 2️⃣ Listar todas as tarefas
```http
GET /api/tarefas
```
**Resposta:**
```json
[
  {
    "id": 1,
    "titulo": "Estudar Spring Boot",
    "descricao": "Ler a documentação oficial e fazer exercícios."
  }
]
```

### 3️⃣ Atualizar uma tarefa existente
```http
PUT /api/tarefas/{id}
```
**Corpo da requisição:**
```json
{
  "titulo": "Estudar Spring Boot - Parte 2",
  "descricao": "Fazer mais exercícios."
}
```
**Resposta:**
```json
{
  "id": 1,
  "titulo": "Estudar Spring Boot - Parte 2",
  "descricao": "Fazer mais exercícios."
}
```

### 4️⃣ Excluir uma tarefa
```http
DELETE /api/tarefas/{id}
```
**Resposta:**
```json
{
  "mensagem": "Tarefa excluída com sucesso!"
}
```

### 5️⃣ Buscar uma tarefa pelo ID
```http
GET /api/tarefas/{id}
```
**Resposta:**
```json
{
  "id": 1,
  "titulo": "Estudar Spring Boot",
  "descricao": "Ler a documentação oficial e fazer exercícios."
}
```

## 🏆 Regras do Sistema
- Cada tarefa deve conter um título e uma descrição.
- O sistema deve permitir listar, atualizar e excluir tarefas.

## 🧪 Testes
- Utilize o Postman ou Insomnia para testar os endpoints.
- Escreva testes unitários utilizando **JUnit 5**.

## 📢 Regras do Desafio
- Código deve estar versionado no GitHub.
- Aplicação deve seguir boas práticas de organização.
- Implementação de tratamento de erros simples para respostas adequadas.

## 🍴 Faça um fork do repositório:
- Faça um fork e realize as mudanças criando PRs e branches

- Descreva no PR o que foi implementado.

## 📂 Estrutura do projeto
![](image/imagem.png)
