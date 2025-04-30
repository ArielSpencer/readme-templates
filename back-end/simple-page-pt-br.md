![Static Badge](https://img.shields.io/badge/Ariel%20Spencer-Readme%20Templates-%239377be) ![GitHub License](https://img.shields.io/github/license/arielspencer/readme-templates) [![English Translation](https://img.shields.io/badge/Translate%20To-🇺🇸%20English-%23f5bb55)](simple-page-en.md)

<br/><br/>
<p align="center">
    <img src="../images/logo.png" width="200px">
</p>
<br/>
<p align="center">
    <img alt="Node.js" src="https://img.shields.io/badge/Node.js-%23339933?style=for-the-badge&logo=nodedotjs&logoColor=%23FFFFFF">
    <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-%233178C6?style=for-the-badge&logo=typescript&logoColor=%23FFFFFF">
    <img alt="Express.js" src="https://img.shields.io/badge/Express.js-%23000000?style=for-the-badge&logo=express&logoColor=%23FFFFFF">
    <img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-%23336791?style=for-the-badge&logo=postgresql&logoColor=%23FFFFFF">
    <img alt="Docker" src="https://img.shields.io/badge/Docker-%232496ED?style=for-the-badge&logo=docker&logoColor=%23FFFFFF">
</p>
<br/><br/>

# Nome do Projeto

**Breve descrição**: Resumo sobre o projeto (o que faz e qual problema ele resolve).

## 🎯 Visão Geral da API

<p align="center">
    <img src="../images/screenshot.png" alt="Arquitetura da API" width="600px">
</p>

## 📚 Índice

- [Descrição](#📝-descrição)
- [Tecnologias](#👾-tecnologias)
- [Instalação e Uso](#🚀-instalação-e-uso)
- [Endpoints da API](#📡-endpoints-da-api)
- [Variáveis de Ambiente](#🔧-variáveis-de-ambiente)
- [Schema do Banco de Dados](#🎲-schema-do-banco-de-dados)
- [Autenticação](#🔐-autenticação)
- [Testes](#🧪-testes)
- [Docker](#🐳-docker)
- [Contribuições](#🧑‍🤝‍🧑-contribuições)
- [Licença](#📝-licença)

## ✏️ Descrição

Explicação mais detalhada sobre o projeto e seu propósito.

## 👾 Tecnologias

Lista de tecnologias e ferramentas utilizadas no desenvolvimento do projeto.  
Exemplo:

- Node.js
- TypeScript
- Express.js
- PostgreSQL
- Prisma ORM
- Autenticação JWT
- Docker
- Redis
- Jest

## 🤖 Instalação e Uso

### Pré-requisitos

Lista de dependências e ferramentas necessárias para rodar o projeto.  
Exemplo:
- [Node.js](https://nodejs.org/en/docs/) (versão: 18.17.1)
- [PostgreSQL](https://www.postgresql.org/) (versão: 14+)
- [Docker](https://docs.docker.com/) (opcional)

### Instalação

1. Clone o repositório:
    ```bash
    git clone https://github.com/ArielSpencer/readme-templates.git
    ```

2. Navegue até o diretório do projeto:
    ```bash
    cd readme-templates
    ```

3. Instale as dependências necessárias:
    ```bash
    npm install
    ```

4. Configure as variáveis de ambiente:
    ```bash
    cp .env.example .env
    ```

5. Configure o banco de dados:
    ```bash
    npm run db:migrate
    npm run db:seed
    ```

6. Inicie a aplicação em modo de desenvolvimento:
    ```bash
    npm run dev
    ```

### Scripts disponíveis

Detalhes sobre scripts úteis:

- **`npm start`**: Inicia a aplicação em modo de produção.
- **`npm run dev`**: Inicia a aplicação em modo de desenvolvimento com hot reload.
- **`npm run build`**: Cria uma versão otimizada da aplicação para produção.
- **`npm run test`**: Executa a suíte de testes.
- **`npm run db:migrate`**: Executa as migrações do banco de dados.
- **`npm run db:seed`**: Popula o banco de dados com dados iniciais.

## 📡 Endpoints da API

### Autenticação
- `POST /auth/login` - Login do usuário
- `POST /auth/register` - Registro de usuário
- `POST /auth/refresh` - Renovar token de acesso

### Usuários
- `GET /users` - Listar todos os usuários
- `GET /users/:id` - Obter usuário por ID
- `PUT /users/:id` - Atualizar usuário
- `DELETE /users/:id` - Deletar usuário

### Exemplo de Requisição/Resposta

```bash
POST /auth/login
Content-Type: application/json

{
  "email": "user@example.com",
  "password": "password123"
}
```

```json
{
  "user": {
    "id": 1,
    "email": "user@example.com",
    "name": "Ariel Spencer"
  },
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

## 🔧 Variáveis de Ambiente

Crie um arquivo `.env` no diretório raiz com as seguintes variáveis:

```env
NODE_ENV=development
PORT=3000
DATABASE_URL=postgresql://username:password@localhost:5432/database_name
JWT_SECRET=your_jwt_secret_key
REDIS_URL=redis://localhost:6379
```

## 🎲 Schema do Banco de Dados

### Tabela Users
| Coluna    | Tipo      | Descrição                |
|-----------|-----------|--------------------------|
| id        | INTEGER   | Chave primária           |
| email     | VARCHAR   | Email do usuário (único) |
| password  | VARCHAR   | Senha criptografada      |
| name      | VARCHAR   | Nome completo do usuário |
| created_at| TIMESTAMP | Data de criação          |
| updated_at| TIMESTAMP | Data da última atualização |

## 🔐 Autenticação

Esta API utiliza JWT (JSON Web Tokens) para autenticação. Inclua o token no cabeçalho Authorization:

```bash
Authorization: Bearer your_jwt_token_here
```

## 🧪 Testes

Executar a suíte de testes:

```bash
npm run test
```

Executar testes com cobertura:

```bash
npm run test:coverage
```

## 🐳 Docker

### Executando com Docker

1. Construir a imagem:
    ```bash
    docker build -t project-name .
    ```

2. Executar o container:
    ```bash
    docker run -p 3000:3000 project-name
    ```

### Usando Docker Compose

```bash
docker-compose up -d
```

## 🧑‍🤝‍🧑 Contribuições

Diretrizes sobre como contribuir para o projeto com *forks*, *pull requests*, etc.

### Passos para contribuição:

1. Clone o repositório:

    ```bash
    git clone https://github.com/ArielSpencer/readme-templates.git
    ```

2. Crie uma nova branch:

    ```bash
    git checkout -b feature/NAME
    ```

3. Siga os padrões de commit do [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).

    ```bash
    git commit -m "feat(api): adicionar endpoint de autenticação de usuário"
    ```

4. Abra um Pull Request explicando o problema resolvido ou a funcionalidade adicionada. Se houver modificações visuais, anexe uma captura de tela e aguarde a revisão!

    [Mais detalhes de como criar uma solicitação de pull](https://docs.github.com/pt/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

## ☕️ Desenvolvido por

<div align="center">
    <div style="display: inline-block; margin: 0 30px;">
        <a href="https://github.com/ArielSpencer">
            <img src="https://github.com/ArielSpencer.png" alt="Ariel Spencer" width="130px" style="border-radius:50%">
        </a>
        <p>Ariel Spencer</p>
        <a href="https://arielspencer.com.br">
            <img alt="Site Ariel Spencer" src="https://img.shields.io/badge/arielspencer.com.br-%239377be">
        </a>
    </div>
</div>

## 📝 Licença

Este projeto está sob a [Licença MIT](https://opensource.org/licenses/MIT).