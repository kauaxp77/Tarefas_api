# API de Tarefas (Estágio)

Esta é uma API REST desenvolvida em Spring Boot para o gerenciamento de tarefas.

22 Endpoints

Abaixo estão os endpoints disponíveis na aplicação e exemplos de uso.

### 1. Cadastrar Tarefa
- **Rota:** `POST /tarefas`
- **Descrição:** Cria uma nova tarefa.
- **Corpo da Requisição (JSON):**
  ```json
  {
    "titulo": "Estudar Spring Boot",
    "descricao": "Revisar conceitos de injeção de dependência e JPA",
    "responsavel": "Wendell",
    "dataEntrega": "2026-10-15",
    "concluida": false
  }
  ```
- **Resposta de Sucesso:** `201 Created`

### 2. Listar Tarefas
- **Rota:** `GET /tarefas`
- **Descrição:** Retorna a lista de todas as tarefas cadastradas. Pode ser filtrada pelo nome do responsável.
- **Parâmetros de Query (Opcionais):**
  - `responsavel` (String): Filtra as tarefas que contêm o nome do responsável especificado.
- **Exemplo de Uso:** `/tarefas?responsavel=Wendell`
- **Resposta de Sucesso:** `200 OK` (Retorna uma lista de tarefas em formato JSON)

### 3. Buscar Tarefas por Data
- **Rota:** `GET /tarefas/data`
- **Descrição:** Retorna as tarefas agendadas para uma data de entrega específica.
- **Parâmetros de Query (Obrigatórios):**
  - `data` (String - Formato: YYYY-MM-DD): Data de entrega para buscar.
- **Exemplo de Uso:** `/tarefas/data?data=2026-10-15g
- **Resposta de Sucesso:** `200 OK`

### 4. Listar Tarefas Pendentes
- **Rota:** `GET /tarefas/pendentes`
- **Descrição:** Retorna todas as tarefas onde o status `concluida` é `false`. Também pode ser filtrada pelo responsável.
- **Parâmetros de Query (Opcionais):**
  - `responsavel` (String): Filtra as tarefas pendentes do responsável especificado.
- **Exemplo de Uso:** `/tarefas/pendentes?responsavel=Wendell`
- **Resposta de Sucesso:** `200 OK`