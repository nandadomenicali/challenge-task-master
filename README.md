# Desafio: Desenvolvimento de uma API REST para Gerenciamento de Tarefas ✅

## 📌 Objetivo
O desafio consiste em desenvolver uma API REST para um **sistema de gerenciamento de tarefas**. A API permitirá que os usuários criem, atualizem, excluam e listem tarefas de forma simples.

## 📢 Avisos antes de começar
- Leia com atenção este documento todo e tente seguir ao máximo as instruções;
- Realize um `fork` desse repositório e realize suas mudanças;

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
- **Gerenciador de Dependências:** Maven
- **Testes:** JUnit 5
- **Spring Data JPA** – Para facilitar a manipulação do banco de dados.
- **Spring DevTools** – Para facilitar o desenvolvimento com reload automático.
- **Spring Web** - Para facilitar o desenvolvimento de aplicações web seguindo o padrão Model-View-Controller (MVC)

## 🗄️ Como Instalar o Banco de Dados H2
1. O H2 já vem configurado e não exige instalação separada.
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
POST /api/task
```
**Corpo da requisição:**
```json
{
  "title": "Estudar Spring Boot",
  "description": "Ler a documentação oficial e fazer exercícios."
}
```
**Resposta:**
```json
{
  "id": 1,
  "title": "Estudar Spring Boot",
  "description": "Ler a documentação oficial e fazer exercícios."
}
```

### 2️⃣ Listar todas as tarefas
```http
GET /api/tasks
```
**Resposta:**
```json
[
  {
    "id": 1,
    "title": "Estudar Spring Boot",
    "description": "Ler a documentação oficial e fazer exercícios."
  }
]
```

### 3️⃣ Atualizar uma tarefa existente
```http
PUT /api/task/{id}
```
**Corpo da requisição:**
```json
{
  "title": "Estudar Spring Boot - Parte 2",
  "description": "Fazer mais exercícios."
}
```
**Resposta:**
```json
{
  "id": 1,
  "title": "Estudar Spring Boot - Parte 2",
  "description": "Fazer mais exercícios."
}
```

### 4️⃣ Excluir uma tarefa
```http
DELETE /api/task/{id}
```
**Resposta:**
```json
{
  "message": "Tarefa excluída com sucesso!"
}
```

### 5️⃣ Buscar uma tarefa pelo ID
```http
GET /api/task/{id}
```
**Resposta:**
```json
{
  "id": 1,
  "title": "Estudar Spring Boot",
  "description": "Ler a documentação oficial e fazer exercícios."
}
```

## 🏆 Regras do Sistema
- Cada tarefa deve conter um título e uma descrição.
- O sistema deve permitir listar, atualizar e excluir tarefas.

## 🧪 Testes
- Utilize o Postman para testar os endpoints.
- Escreva testes unitários utilizando **JUnit 5**.

## 🚀 Regras do Desafio
- Código deve estar versionado no GitHub.
- Aplicação deve seguir boas práticas de organização.

## 📂 Estrutura do projeto
![](image/imagem.png)
