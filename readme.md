# Desafio 01 - NodeJs, Ignite

Esse é apenas um desafio realizado no curso de NodeJs do Ignite, basicamente é um CRUD de lista de tarefas (to-do list), porém, o armazenamento dos dados foi realizada sem banco de dados, armazenando os dados temporariamente na memória.

## Sobre o desafio

"Nesse desafio, você deverá criar uma aplicação para treinar o que aprendeu até agora no Node.js!

Essa será uma aplicação para gerenciar tarefas (em inglês _todos_). Será permitida a criação de um usuário com `name` e `username`, bem como fazer o CRUD de _todos_:

-   Criar um novo _todo_;
-   Listar todos os _todos_;
-   Alterar o `title` e `deadline` de um _todo_ existente;
-   Marcar um _todo_ como feito;
-   Excluir um _todo_;

Tudo isso para cada usuário em específico (o `username` será passado pelo header). A seguir veremos com mais detalhes o que e como precisa ser feito 🚀."

## Arquivos

Somente o arquivo **src/index.js** foi alterado, toda estrutura e os outros arquivos do projeto continuam seguindo a originalidade do template


## Switch to another file

All your files and folders are presented as a tree in the file explorer. You can switch from one to another by clicking a file in the tree.

## Requisitos

 - [x] Deve ser possível cadastrar um novo usuário
 - [x] Deve ser possível listar a lista de tarefa de um usuário especifico
 - [x] Deve ser possível inserir uma tarefa na lista de tarefa de um usuário
 - [x] Deve ser possível alterar as informações da tarefa de um usuário
 - [x] Deve ser possível alterar o status da tarefa de um usuário (concluída ou não)
 - [x] Deve ser possível deletar uma tarefa da lista de tarefas de um usuário

## Regras de negócio
### Regras de negócio dos usuários
 - [x] Deve permitir que um usuário seja criado e retorne um json com o usuário criado.
 - [x] Antes de criar um usuário você deve validar se outro usuário com o mesmo username já existe
### Regras de negócio da lista de tarefas
 - [x] Não deve ser possível listar a to-do list de um usuário que não existe, se caso o usuário tentar realizar essa ação deve retornar erro.
 - [x] Antes de manipular qualquer informação de uma tarefa, verificar se o usuário existe, caso não exista, deve retornar erro.
 - [x] Não deve ser possível atualizar a informação de uma tarefa que não existe.
 - [x] Não deve ser possível atualizar o status de uma tarefa que não existe.
 - [x] Não deve ser possível deletar uma tarefa que não existe.

## Rotas
**Url base:** http://localhost:3333
 - **Post - /users**
Realizar o cadastro de usuários.
**Instruções:**
Para consumir essa rota, é necessário passar os seguintes parâmetros:
	- name e username no body da requisição no formato Json.
```
{
	"name": "Marcos",
	"username": "marcosmj"
}
```
 - **GET - /todos**
Lista as tarefas de um usuário.
**Instruções:**
Para consumir essa rota, é necessário passar os seguintes parâmetros:
	- username do usuário que deseja visualizar a lista no header da requisição.
	
- **POST - /todos**
Cadastra uma nova tarefas a um usuário.
**Instruções:**
Para consumir essa rota, é necessário passar os seguintes parâmetros:
	- username do usuário que deseja inserir um item na lista no header da requisição.
	- title e deadline  no body da requisição no formato Json
``	{
	"title": "Terminar Nível 2 do Ignite",
		"deadline": "2021-04-02"
}``

- **PUT - /todos/{id}**
Altera as informações de uma tarefas de um usuário.
**Instruções:**
Para consumir essa rota, é necessário passar os seguintes parâmetros:
	- username do usuário que deseja alterar um item na lista no header da requisição.
	- title e deadline  no body da requisição no formato Json
``	{
	"title": "Terminar Nível 2 do Ignite",
		"deadline": "2021-04-05"
}``
	- Especificar qual o id da tarefa que deseja alterar na url
	
- **PATCH - /todos/{id}/done**
Alterao e status de uma tarefas de um usuário para concluído.
**Instruções:**
Para consumir essa rota, é necessário passar os seguintes parâmetros:
	- username do usuário que deseja concluir um item na lista no header da requisição.
	- title e deadline  no body da requisição no formato Json
	- Especificar qual o id da tarefa que deseja concluir na url
	
- **DELETE- /todos/{id}**
Deleta uma tarefas de um usuário.
**Instruções:**
Para consumir essa rota, é necessário passar os seguintes parâmetros:
	- username do usuário que deseja deletar um item na lista no header da requisição.
	- Especificar qual o id da tarefa que deseja alterar na url
	

 
