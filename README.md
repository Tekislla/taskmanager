## Task Manager
Gerenciador de tarefas utilizando Java e Vue

A aplicação estará rodando na porta 9000
<br>
<br>
**Tecnologias utilizadas**
<br>

* Java e spring boot para o backend
* Liquibase para realizar a migration do banco de dados
* Vue.js e quasar para o frontend
* PostgreSQL para o banco de dados
* Docker para facilitar na hora de rodar a aplicação

<br>

**Setup do projeto**
<br>
<br>
Requisitos:
* Docker
<br>
Na pasta raiz, onde se encontra o docker-compose.yaml, rodar o comando:
<br>
<br>

    docker compose up -d
    
Isso criará as imagens do banco de dados postgres, do backend e do frontend, e subirá tudo junto em um compose, fazendo o sistema ser acessível através da url http://localhost:9000/
    
  
<br>
Para rodar os testes unitários localmente, é necessário trocar a url do banco no application.yml de:
<br>
<br>

      jdbc:postgresql://database:5432/taskmanager
para:

      jdbc:postgresql://localhost:5432/taskmanager
    
<br>
Diagrama de classes:
<br>
<br>

![Diagrama de Classes](assets/diagrama_de_classe.png)
<br>
<br>
**Pontos de melhoria e observações**
<br>
* Classes Squad e User: gostaria de ter tido mais tempo para implementar estas classes, para relacionar um projeto à uma squad e atribuir uma tarefa à um user
* Campos adicionais na tarefa: seria interessante adicionar campos adicionais às tarefas, como: data de criação, estimativa de entrega, data de entrega, etc
* Status dinâmicos das tarefas: com essa adição, o próprio usuário criaria os boards (ex: done, in progress, etc.) ao invés de utilizar os que foram previamente criados
