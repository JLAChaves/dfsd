# CashbackBeer

Esta API foi desenvolvida no contexto do Teste de Desenvolvimento da Talto Sistemas, onde foi requisitado a criação de um serviço de back-end que fosse 
responsável por efetuar vendas de cerveja e calcular o cashback para o cliente, respeitando regras preestabelidas. Para isso, foi utilizado a linguagem C#, a 
ORM Entity Framework Core e o banco de dados SQLServer

Para buildar e executar a aplicação. É necessário estabelecer uma string de conexão para o banco de dados local na appsettings.json. Exemplo: 

![image](https://user-images.githubusercontent.com/95765339/180358225-5bca2196-9e90-4de0-be52-21bd60e8d31b.png)

Depois disso, é necessário abrir o Console do Gerenciador de Pacotes e digitar o comando "Update-Database". Com isso, é possível executar a API, que funcionará na porta 7270.

## :hammer: Banco de Dados

Ao iniciar o banco de dados, a tabela de cervejas já contará com todas as cervejas cadastradas com seus respestivos cashbacks, como na imagem abaixo:

![image](https://user-images.githubusercontent.com/95765339/180362032-20ac780e-1ae0-40a1-81a0-a1060e872329.png)


## :hammer: Funcionalidades do projeto

- `Consultar Cervejas por Nome`: É possível consultar o catálogo de cervejas de forma paginada, filtrando por nome e ordenando de forma crescente. Um exemplo da utilização desta funcionalidade é através do link: https://localhost:7270/api/Beer?Page=1&Limit=2&name=skol.
Abaixo temos um exemplo da utilização deste endpoint no Postman:

![image](https://user-images.githubusercontent.com/95765339/180359638-eb84ab02-0225-4ca5-aa38-a027a8caa021.png)

Caso o usuário não informe nenhum nome, a API retorna todas as cervejas de forma paginada e organizadas de forma crescente.

- `Consulta cerveja por Id`: É possível consultar uma cerveja específica através do seu Id, que é um identificador único. Um exemplo da utilização desta funcionalidade é através do link: https://localhost:7270/api/Beer/SearchId/2. Este endpoint retorna o seguinte JSON: ![image](https://user-images.githubusercontent.com/95765339/180360510-0c6112d5-a874-4664-bcc1-d9da043b3e07.png)

- `Consulta de Vendas por Data`: É possível consultar todas as vendas efetuadas de forma paginada, filtrando pelo range de datas da venda e ordenando de forma descrescente pela data da venda. Um exemplo da utilização desta funcionalidade é através do link: https://localhost:7270/api/FinalSale/SearchDate?Page=1&Limit=7&minDate=2022%2F07%2F18&maxDate=2022%2F07%2F20. O retorno dessa requisição pode ser vista abaixo:
![image](https://user-images.githubusercontent.com/95765339/180362447-82938024-2179-421c-a5a9-26eaa5dd5a4b.png)


Como são muitos dados, não coube no print, mas em suma, a API retorna uma lista de vendas, com seus valores totais, seus cashbacks totais e também traz uma lista de vendas parciais que compõem a venda final.

- `Consultar venda por Id`: É possível consultar uma venda através do seu identificador. Um exemplo é através do link: https://localhost:7270/api/FinalSale/SearchId/14 que retorna:
- ![image](https://user-images.githubusercontent.com/95765339/180361244-b5487bfe-09dc-4f9e-85ed-71e86670a5a0.png)

- `Cadastrar venda de uma ou várias cervejas`: É possível cadastrar a venda de uma ou várias cervejas, onde a API faz todo o cálculo de cashback das vendas parciais e da venda final. Para isso é necessário usar o método post no link https://localhost:7270/api/FinalSale e depois passar a lista de compras no body da requisição, como abaixo: 

![image](https://user-images.githubusercontent.com/95765339/180361717-8deed8de-2312-4dbd-838b-a234a51b0e84.png)

Isso é o suficiente para fazer todos os cálculos e todos os registros necessários.

## :hammer: Observação

Os dados apresentados nos prints de exemplo não estarão presentes no projeto no momento do build, apenas estarão presentes os dados relacionados às cervejas, todo o resto deverá ser cadastrado pelo usuário.
