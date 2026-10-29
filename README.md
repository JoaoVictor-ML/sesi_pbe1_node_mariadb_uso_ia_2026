# Backend — Catálogo de Usos de Inteligência Artificial

## Sobre o projeto

O **Backend de Usos de Inteligência Artificial** é um projeto acadêmico desenvolvido no curso técnico de Desenvolvimento de Sistemas do SENAI. A proposta consiste em criar uma API para catalogar e monitorar aplicações de Inteligência Artificial utilizadas por empresas, escolas e outras organizações.

O sistema permite registrar informações sobre os sistemas de IA, suas finalidades, tecnologias utilizadas, níveis de risco e a existência de revisão humana. O objetivo é organizar esses dados e facilitar pesquisas sobre a utilização da Inteligência Artificial em diferentes contextos.

## Objetivos

- Desenvolver uma API para gerenciamento de usuários e registros de uso de IA.
- Implementar operações CRUD para usuários e aplicações de Inteligência Artificial.
- Implementar autenticação por login.
- Classificar os registros conforme o nível de risco.
- Identificar se existe revisão humana nas aplicações cadastradas.
- Apresentar um resumo quantitativo dos registros classificados por nível de risco.
- Modelar a estrutura do sistema por meio de diagramas de banco de dados e de classes.

## Requisitos funcionais

| Código | Requisito | Descrição |
|---|---|---|
| RF001 | CRUD de usuários | Cadastrar, consultar, atualizar e excluir usuários. |
| RF002 | Login | Permitir a autenticação de usuários cadastrados. |
| RF003 | CRUD de usos de IA | Gerenciar os registros de aplicações de Inteligência Artificial. |
| RF004 | Resumo de riscos | Exibir a contagem total de registros com níveis de risco Alto, Médio e Baixo. |

## Requisito não funcional

**NF001 — Diagrama de Classes:** elaborar o diagrama utilizando o [draw.io](https://app.diagrams.net/) e salvar a imagem no formato PNG dentro da pasta `docs`.

## Modelagem do banco de dados

O banco de dados utilizado é o `usos_ia`, composto por duas tabelas principais:

- **usuario:** armazena o identificador, nome, e-mail e senha dos usuários cadastrados.
- **usoia:** armazena o usuário responsável pelo registro, o nome do sistema de IA, o tipo de organização, a finalidade, a tecnologia utilizada, o nível de risco e a indicação de revisão humana.

A tabela `usoia` possui uma chave estrangeira (`usuarioId`) que estabelece o relacionamento entre cada registro e seu respectivo usuário.

### Classificação dos registros

| Campo | Valores ou finalidade |
|---|---|
| Tipo | Empresa, Escola ou Outros |
| Finalidade | Descreve o objetivo da aplicação de IA |
| Tecnologia | Identifica a tecnologia utilizada |
| Nível de risco | Baixo, Médio ou Alto |
| Revisão humana | Indica se existe revisão humana na aplicação |

## Tecnologias e ferramentas

- **JavaScript** — desenvolvimento da lógica do back-end.
- **Node.js** — ambiente de execução.
- **Express** — criação do servidor e gerenciamento das rotas da API.
- **MySQL** — gerenciamento do banco de dados relacional.
- **SQL** — criação, relacionamento e população das tabelas.
- **Visual Studio Code** — ambiente de desenvolvimento.
- **draw.io** — elaboração dos diagramas do sistema.
- **Postman** — ferramenta para testar as requisições HTTP.

## Estrutura do projeto

```text
backend_usos_ia/
├── db/
│   └── script.sql
├── docs/
│   ├── der_uso_ia.png
│   └── diagrama_classes.png
├── src/
│   ├── controllers/
│   │   ├── usoia.js
│   │   └── usuario.js
│   ├── db.js
│   └── routes.js
└── server.js
```

## Como executar

1. Instale o [Node.js](https://nodejs.org/) e o [MySQL](https://dev.mysql.com/downloads/).
2. Clone o repositório e acesse a pasta do projeto.
3. Execute o script `db/script.sql` no MySQL para criar e popular o banco de dados.
4. Configure a conexão com o banco de dados no arquivo `src/db.js`.
5. Instale as dependências necessárias:

   ```bash
   npm init -y
   npm install express mysql2
   ```

6. Inicie o servidor:

   ```bash
   node server.js
   ```

7. Utilize o Postman ou outra ferramenta compatível para testar as rotas da API.

> **Observação:** os comandos pressupõem uma implementação com Express e o driver `mysql2`. A configuração pode variar conforme o código desenvolvido.



**Projeto acadêmico — SENAI | Desenvolvimento de Sistemas**  
**Tema:** catalogação e monitoramento de aplicações de Inteligência Artificial.
