DNCommerce API
Desafio 02 — Banco de Dados e API REST | Formação DNC
Este projeto tem como objetivo desenvolver uma API RESTful para simular o funcionamento de um sistema de e-commerce, incluindo o gerenciamento de clientes, produtos, pedidos e vendas. O back-end foi construído em Node.js com Express e utiliza um banco de dados relacional (PostgreSQL) modelado conforme o diagrama abaixo.
Objetivos do Desafio

- Criar um banco de dados relacional completo com entidades e relacionamentos adequados.
- Desenvolver uma API REST para operações CRUD (Create, Read, Update, Delete) nas principais entidades.
- Organizar a estrutura do projeto de forma limpa e modular.
- Documentar o projeto com instruções claras para execução e testes.

Estrutura de Pastas

backend-dncommerce/
│
├── src/
│   ├── config/          # Configurações (ex: conexão com banco de dados)
│   ├── controllers/     # Lógica das rotas (clientes, produtos, pedidos, vendas)
│   ├── models/          # Definições das entidades e relacionamentos
│   ├── routes/          # Definição das rotas REST
│   ├── db/              # Scripts SQL, migrations e seeds
│   └── server.js        # Ponto de entrada da aplicação
│
├── .env.example         # Variáveis de ambiente (modelo)
├── package.json
├── README.md
└── Diagrama_ER.jpg      # Diagrama Entidade-Relacionamento do banco

Modelagem do Banco de Dados

Entidades principais:
- Clientes — informações pessoais e de contato.
- Produtos — catálogo de itens disponíveis para compra.
- Pedidos — solicitações feitas por clientes.
- Itens do Pedido / Vendas — produtos associados a cada pedido.

Relacionamentos:
- Um cliente pode ter muitos pedidos.
- Um pedido pode conter muitos produtos.
- Um produto pode estar em muitos pedidos (relação N:N com tabela intermediária itens_pedido).

Tecnologias Utilizadas

- Node.js
- Express
- PostgreSQL
- Sequelize ou Knex.js (para ORM/migrations)
- dotenv (para variáveis de ambiente)
- Nodemon (para ambiente de desenvolvimento)

Como Executar o Projeto
1️⃣ Clonar o repositório:
git clone https://github.com/patycamper/RID176780_Desafio02_Banco-de-Dados.git
cd backend-dncommerce
2️⃣ Instalar as dependências:

npm install

3️⃣ Configurar o banco de dados:
Crie um arquivo .env com base no exemplo:

DB_HOST=localhost
DB_USER=postgres
DB_PASS=sua_senha
DB_NAME=dncommerce
DB_PORT=5432
PORT=3000

4️⃣ Criar o banco e rodar migrations:

npx sequelize db:create
npx sequelize db:migrate
npx sequelize db:seed:all
5️⃣ Iniciar o servidor:

npm run dev

Servidor disponível em: http://localhost:3000
Rotas da API
Clientes:
GET /clientes
GET /clientes/:id
POST /clientes
PUT /clientes/:id
DELETE /clientes/:id
Produtos:
GET /produtos
GET /produtos/:id
POST /produtos
PUT /produtos/:id
DELETE /produtos/:id
Pedidos:
GET /pedidos
GET /pedidos/:id
POST /pedidos
PUT /pedidos/:id
DELETE /pedidos/:id

Autora
👩‍💻 Patrícia Amâncio
GitHub: https://github.com/patycamper
LinkedIn: https://www.linkedin.com/in/patycamper
