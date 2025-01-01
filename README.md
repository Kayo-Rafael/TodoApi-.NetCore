# Todo API

### **Descrição**

Esta API foi desenvolvida em **C#** utilizando o framework **ASP.NET Core** e o **Entity Framework Core**. Ela permite a criação, leitura, atualização e exclusão (CRUD) de itens de uma lista de tarefas (To-Do list).

---

## **Recursos da API**

### **Endpoints**

1. **GET /api/TodoItems**

   - Retorna todos os itens da lista de tarefas.
   - **Resposta:**
     ```json
     [
       {
         "id": 1,
         "name": "Exemplo",
         "isComplete": false
       }
     ]
     ```

2. **GET /api/TodoItems/{id}**

   - Retorna um item específico da lista de tarefas pelo `id`.
   - **Resposta:**
     ```json
     {
       "id": 1,
       "name": "Exemplo",
       "isComplete": false
     }
     ```

3. **POST /api/TodoItems**

   - Adiciona um novo item à lista de tarefas.
   - **Requisição:**
     ```json
     {
       "name": "Nova Tarefa",
       "isComplete": false
     }
     ```
   - **Resposta:**
     ```json
     {
       "id": 2,
       "name": "Nova Tarefa",
       "isComplete": false
     }
     ```

4. **PUT /api/TodoItems/{id}**

   - Atualiza um item existente da lista de tarefas pelo `id`.
   - **Requisição:**
     ```json
     {
       "id": 1,
       "name": "Tarefa Atualizada",
       "isComplete": true
     }
     ```
   - **Resposta:** 204 No Content

5. **DELETE /api/TodoItems/{id}**

   - Remove um item da lista de tarefas pelo `id`.
   - **Resposta:** 204 No Content

---

## **Como Executar o Projeto**

### **Pré-requisitos**

1. .NET SDK instalado (versão 6.0 ou superior).
2. Banco de dados configurado para uso com **Entity Framework Core**.

### **Passos**

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/seu-usuario/todo-api.git
   cd todo-api
   ```

2. **Configure o Banco de Dados:**

   - Verifique a string de conexão no arquivo `appsettings.json` e ajuste conforme necessário:
     ```json
     "ConnectionStrings": {
       "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=TodoDb;Trusted_Connection=True;"
     }
     ```

3. **Execute as Migrações:**

   ```bash
   dotnet ef database update
   ```

4. **Inicie o Projeto:**

   ```bash
   dotnet run
   ```

5. **Teste a API:**

   - Acesse a API via `http://localhost:5000/api/TodoItems`.
   - Use ferramentas como **Postman** ou **Insomnia** para realizar testes nos endpoints.

---

## **Estrutura do Projeto**

- **Controllers/TodoItemsController.cs**: Contém os endpoints principais da API.
- **Models/TodoItem.cs**: Define o modelo de dados do item de tarefa.
- **Data/TodoContext.cs**: Configuração do contexto do Entity Framework Core para o banco de dados.
