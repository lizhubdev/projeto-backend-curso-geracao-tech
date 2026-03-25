# API Backend - Sistema de Gerenciamento de Produtos

## Visão Geral

Este projeto é uma API RESTful desenvolvida com Node.js e Express para gerenciamento de usuários, produtos e categorias. Ele segue uma arquitetura em camadas, separando responsabilidades entre controllers, services, models e routes.

A API oferece suporte à autenticação, gerenciamento de produtos (incluindo opções e imagens) e organização por categorias. Foi projetada para ser escalável e de fácil manutenção, sendo adequada para aplicações reais como sistemas de e-commerce.

---

## Tecnologias

- Node.js
- Express.js
- PostgreSQL
- Sequelize (ORM)
- JWT (Autenticação)
- Jest (Testes)
- Swagger (Documentação da API)

---

## Instalação

### Pré-requisitos

- Node.js (recomendado v18 ou superior)
- PostgreSQL instalado e em execução
- npm ou yarn

### Passos

1. Clone o repositório ou extraia os arquivos do projeto:

```bash
git clone <url-do-repositorio>
cd project-root
Instale as dependências:
npm install
Crie um arquivo .env na raiz do projeto e configure as variáveis de ambiente:
PORT=3000
DB_HOST=localhost
DB_USER=seu_usuario
DB_PASS=sua_senha
DB_NAME=seu_banco
JWT_SECRET=sua_chave_secreta
Execute as migrations do banco (se configuradas):
npx sequelize-cli db:migrate
Inicie o servidor em modo de desenvolvimento:
npm run dev

A API estará disponível em:

http://localhost:3000
Uso
Autenticação

Rotas protegidas exigem um token JWT. Após o login, envie o token no header:

Authorization: Bearer <token>
Exemplos de Endpoints
Usuários
POST /users - Criar novo usuário
POST /login - Autenticar usuário
Categorias
GET /categories - Listar categorias
POST /categories - Criar categoria
Produtos
GET /products - Listar produtos
POST /products - Criar produto
PUT /products/:id - Atualizar produto
DELETE /products/:id - Remover produto
Estrutura do Projeto
project-root/
├── src/
│   ├── app.js                # Configuração do Express
│   ├── server.js             # Ponto de entrada da aplicação
│   ├── config/
│   │   └── database.js       # Configuração do banco de dados
│   ├── controllers/          # Controladores (camada de requisição)
│   │   ├── AuthController.js
│   │   ├── UserController.js
│   │   ├── ProductController.js
│   │   └── CategoryController.js
│   ├── models/               # Modelos do Sequelize
│   │   ├── User.js
│   │   ├── Product.js
│   │   ├── Category.js
│   │   ├── ProductImage.js
│   │   └── ProductOption.js
│   ├── routes/               # Definição das rotas
│   │   ├── userRoutes.js
│   │   ├── productRoutes.js
│   │   └── categoryRoutes.js
│   ├── middleware/
│   │   └── auth.js           # Middleware de autenticação
│   ├── services/
│   │   └── ProductService.js # Regras de negócio
│   └── database/
│       └── index.js          # Inicialização do banco
│
├── tests/                    # Testes automatizados
│   ├── user.test.js
│   ├── product.test.js
│   └── category.test.js
│
├── package.json
└── README.md
Scripts
npm run dev     # Executa com nodemon (desenvolvimento)
npm start       # Alias para dev
npm test        # Executa os testes com Jest
Documentação da API

A documentação com Swagger está disponível após iniciar o servidor:

http://localhost:3000/api-docs
Testes

O projeto utiliza Jest e Supertest para testes de integração.

Execute com:

npm test

Licença

Este projeto está sob a licença ISC.

Observações
Certifique-se de que o PostgreSQL esteja corretamente configurado antes de iniciar o servidor.
As variáveis de ambiente são essenciais para autenticação e conexão com o banco.
A arquitetura segue boas práticas de separação de responsabilidades e escalabilidade.
