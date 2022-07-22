# CashbackBeer

Esta API foi desenvolvida no contexto do Teste de Desenvolvimento da Talto Sistemas, onde foi requisitado a criação de um serviço de back-end que fosse 
responsável por efetuar vendas de cerveja e calcular o cashback para o cliente, respeitando regras preestabelidas. Para isso, foi utilizado a linguagem C#, a 
ORM Entity Framework Core e o banco de dados SQLServer

Para buildar e executar a aplicação. É necessário estabelecer uma string de conexão para o banco de dados local na appsettings.json. Exemplo: 

![image](https://user-images.githubusercontent.com/95765339/180358225-5bca2196-9e90-4de0-be52-21bd60e8d31b.png)

Depois disso, é necessário abrir o Console do Gerenciador de Pacotes e digitar o comando "Update-Database". Com isso, é possível executar a API, que funcionará na porta 7270.

## :hammer: Funcionalidades do projeto

- `Consultar Cervejas por Nome`: É possível consultar o catálogo de cervejas de forma paginada, filtrando por nome e ordenando de forma crescente. Um exemplo da utilização desta funcionalidade é através do link: https://localhost:7270/api/Beer?Page=1&Limit=2&name=skol.
Abaixo temos um exemplo da utilização deste endpoint no Postman:

![image](https://user-images.githubusercontent.com/95765339/180359638-eb84ab02-0225-4ca5-aa38-a027a8caa021.png)

Caso o usuário não informe nenhum nome, a API retorna todas as cervejas de forma paginada e organizadas de forma crescente.

- `Consulta por Id`: É possível consultar uma cerveja específica através do seu Id, que é um identificador único. Para isso é nec
- `Funcionalidade 2a`: descrição da funcionalidade 2a relacionada à funcionalidade 2
- `Funcionalidade 3`: descrição da funcionalidade 3
