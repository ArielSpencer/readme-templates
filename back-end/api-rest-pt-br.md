![Static Badge](https://img.shields.io/badge/Ariel%20Spencer-Readme%20Templates-%239377be) ![GitHub License](https://img.shields.io/github/license/arielspencer/readme-templates) [![English Translation](https://img.shields.io/badge/Translate%20To-🇺🇸%20English-%23f5bb55)](api-rest-en.md)

<br/><br/>
<p align="center">
    <img src="../images/logo.png" width="200px">
</p>
<br/>
<p align="center">
    <img alt="Node.js" src="https://img.shields.io/badge/Node.js-%23339933?style=for-the-badge&logo=nodedotjs&logoColor=%23FFFFFF">
    <img alt="Express.js" src="https://img.shields.io/badge/Express.js-%23000000?style=for-the-badge&logo=express&logoColor=%23FFFFFF">
    <img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-%23336791?style=for-the-badge&logo=postgresql&logoColor=%23FFFFFF">
    <img alt="JWT" src="https://img.shields.io/badge/JWT-%23000000?style=for-the-badge&logo=jsonwebtokens&logoColor=%23FFFFFF">
    <img alt="Swagger" src="https://img.shields.io/badge/Swagger-%2385EA2D?style=for-the-badge&logo=swagger&logoColor=%23000000">
</p>
<br/><br/>

# API do Projeto

**Breve descrição**: API RESTful para [propósito do projeto] com autenticação JWT e operações CRUD completas.

## 🚀 Status da API

![Status da API](https://img.shields.io/badge/API-Online-success)
![Versão](https://img.shields.io/badge/Versão-1.0.0-blue)
![Cobertura](https://img.shields.io/badge/Cobertura-95%25-brightgreen)

**URL Base**: `https://api.example.com/v1`

## 📚 Índice

- [Descrição](#📝-descrição)
- [Funcionalidades](#✨-funcionalidades)
- [Tecnologias](#👾-tecnologias)
- [Instalação e Uso](#🚀-instalação-e-uso)
- [Documentação da API](#📡-documentação-da-api)
- [Autenticação](#🔐-autenticação)
- [Schema do Banco de Dados](#🎲-schema-do-banco-de-dados)
- [Tratamento de Erros](#❌-tratamento-de-erros)
- [Limitação de Taxa](#⚡-limitação-de-taxa)
- [Monitoramento](#📊-monitoramento)
- [Testes](#🧪-testes)
- [Deploy](#🚢-deploy)
- [Contribuições](#🧑‍🤝‍🧑-contribuições)
- [Licença](#📝-licença)

## ✏️ Descrição

Uma API RESTful robusta construída com Node.js e Express.js, apresentando autenticação JWT, validação de entrada, limitação de taxa e tratamento abrangente de erros. Esta API fornece endpoints para [descrever funcionalidade principal].

## ✨ Funcionalidades

- Autenticação baseada em JWT
- Validação de entrada com Joi
- Limitação de taxa e cabeçalhos de segurança
- Tratamento abrangente de erros
- Log de requisições/respostas
- Documentação da API com Swagger
- Testes unitários e de integração
- Migrações e seeds do banco de dados
- Endpoints de verificação de saúde
- Configuração CORS

## 👾 Tecnologias

**Framework Backend:**
- Node.js (v18+)
- Express.js
- TypeScript

**Banco de Dados & ORM:**
- PostgreSQL
- Prisma ORM

**Autenticação & Segurança:**
- JWT (JSON Web Tokens)
- bcrypt
- helmet
- express-rate-limit

**Validação & Documentação:**
- Joi (validação de entrada)
- Swagger/OpenAPI 3.0

**Testes:**
- Jest
- Supertest

**Ferramentas de Desenvolvimento:**
- ESLint
- Prettier
- Husky (Git hooks)

## 🤖 Instalação e Uso

### Pré-requisitos

- [Node.js](https://nodejs.org/) (v18.17.1 ou superior)
- [PostgreSQL](https://www.postgresql.org/) (v14 ou superior)
- [Docker](https://www.docker.com/) (opcional)

### Instalação

1. Clone o repositório:
    ```bash
    git clone https://github.com/username/project-name.git
    cd project-name
    ```

2. Instale as dependências:
    ```bash
    npm install
    ```

3. Configure as variáveis de ambiente:
    ```bash
    cp .env.example .env
    # Edite o .env com sua configuração
    ```

4. Configure o banco de dados:
    ```bash
    npm run db:migrate
    npm run db:seed
    ```

5. Inicie o servidor de desenvolvimento:
    ```bash
    npm run dev
    ```

### Variáveis de Ambiente

```env
NODE_ENV=development
PORT=3000
DATABASE_URL=postgresql://username:password@localhost:5432/database_name
JWT_SECRET=your_super_secret_jwt_key
JWT_EXPIRES_IN=7d
BCRYPT_ROUNDS=12
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100
CORS_ORIGIN=http://localhost:3000
```

### Scripts Disponíveis

- **`npm run dev`**: Iniciar servidor de desenvolvimento com hot reload
- **`npm start`**: Iniciar servidor de produção
- **`npm run build`**: Compilar TypeScript para JavaScript
- **`npm test`**: Executar suíte de testes
- **`npm run test:watch`**: Executar testes em modo de observação
- **`npm run test:coverage`**: Executar testes com relatório de cobertura
- **`npm run db:migrate`**: Executar migrações do banco de dados
- **`npm run db:seed`**: Popular banco de dados com dados de exemplo
- **`npm run db:reset`**: Resetar banco de dados (migrar + popular)
- **`npm run lint`**: Executar ESLint
- **`npm run format`**: Formatar código com Prettier

## 📡 Documentação da API

### Informações Base

- **URL Base**: `/api/v1`
- **Autenticação**: Bearer Token (JWT)
- **Content-Type**: `application/json`

### Endpoints de Autenticação

#### Registrar Usuário
```http
POST /api/v1/auth/register
Content-Type: application/json

{
  "name": "João Silva",
  "email": "joao@example.com",
  "password": "senhaSegura123"
}
```

**Resposta (201):**
```json
{
  "success": true,
  "data": {
    "user": {
      "id": 1,
      "name": "João Silva",
      "email": "joao@example.com",
      "createdAt": "2023-01-01T00:00:00.000Z"
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
  }
}
```

#### Login do Usuário
```http
POST /api/v1/auth/login
Content-Type: application/json

{
  "email": "joao@example.com",
  "password": "senhaSegura123"
}
```

### Endpoints de Gerenciamento de Usuário

#### Obter Todos os Usuários
```http
GET /api/v1/users
Authorization: Bearer {token}
```

#### Obter Usuário por ID
```http
GET /api/v1/users/{id}
Authorization: Bearer {token}
```

#### Atualizar Usuário
```http
PUT /api/v1/users/{id}
Authorization: Bearer {token}
Content-Type: application/json

{
  "name": "Maria Silva",
  "email": "maria@example.com"
}
```

#### Deletar Usuário
```http
DELETE /api/v1/users/{id}
Authorization: Bearer {token}
```

### Verificação de Saúde
```http
GET /api/v1/health
```

**Resposta:**
```json
{
  "status": "ok",
  "timestamp": "2023-01-01T00:00:00.000Z",
  "database": "connected",
  "uptime": "2h 30m 45s"
}
```

### Documentação Interativa

Acesse a UI do Swagger em: `http://localhost:3000/api-docs`

## 🔐 Autenticação

Esta API usa JWT (JSON Web Tokens) para autenticação. Inclua o token no cabeçalho Authorization:

```bash
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

### Fluxo do Token
1. Registre-se ou faça login para receber um token JWT
2. Inclua o token no cabeçalho `Authorization` para rotas protegidas
3. Tokens expiram após 7 dias (configurável)

## 🎲 Schema do Banco de Dados

### Tabela Users
```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    role VARCHAR(50) DEFAULT 'user',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Migrações

Execute as migrações para configurar o banco de dados:
```bash
npm run db:migrate
```

## ❌ Tratamento de Erros

A API usa respostas de erro padronizadas:

```json
{
  "success": false,
  "error": {
    "message": "Recurso não encontrado",
    "code": "RESOURCE_NOT_FOUND",
    "statusCode": 404
  }
}
```

### Códigos de Erro Comuns

| Código | Status | Descrição |
|--------|--------|-----------|
| `VALIDATION_ERROR` | 400 | Dados de entrada inválidos |
| `UNAUTHORIZED` | 401 | Token ausente ou inválido |
| `FORBIDDEN` | 403 | Permissões insuficientes |
| `RESOURCE_NOT_FOUND` | 404 | Recurso não existe |
| `CONFLICT` | 409 | Recurso já existe |
| `RATE_LIMIT_EXCEEDED` | 429 | Muitas requisições |
| `INTERNAL_SERVER_ERROR` | 500 | Erro do servidor |

## ⚡ Limitação de Taxa

Os endpoints da API têm limite de taxa para prevenir abuso:

- **Janela**: 15 minutos
- **Max Requisições**: 100 por janela por IP
- **Cabeçalhos**: Informações de limite incluídas nos cabeçalhos de resposta

```http
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 95
X-RateLimit-Reset: 1640995200
```

## 📊 Monitoramento

### Verificações de Saúde
- **Endpoint**: `GET /api/v1/health`
- **Banco de Dados**: Status da conexão
- **Uptime**: Informações de tempo de atividade do servidor

### Logging
- Todas as requisições e respostas são logadas
- Rastreamento e monitoramento de erros
- Coleta de métricas de performance

## 🧪 Testes

### Executando Testes
```bash
# Executar todos os testes
npm test

# Executar testes em modo de observação
npm run test:watch

# Executar testes com cobertura
npm run test:coverage
```

### Categorias de Teste
- **Testes Unitários**: Funções e módulos individuais
- **Testes de Integração**: Endpoints da API e operações do banco de dados
- **Testes de Autenticação**: JWT e recursos de segurança

### Cobertura de Testes
Manter cobertura mínima de 90% para:
- Controllers
- Services
- Middleware
- Utilities

## 🚢 Deploy

### Deploy com Docker
```bash
# Construir imagem
docker build -t project-name-api .

# Executar container
docker run -p 3000:3000 --env-file .env project-name-api
```

### Checklist de Produção
- [ ] Variáveis de ambiente configuradas
- [ ] Migrações do banco de dados executadas
- [ ] SSL/HTTPS habilitado
- [ ] Limitação de taxa configurada
- [ ] Monitoramento e logging configurados
- [ ] Verificações de saúde implementadas

## 🧑‍🤝‍🧑 Contribuições

### Diretrizes de Desenvolvimento

1. Siga a especificação [Conventional Commits](https://www.conventionalcommits.org/)
2. Escreva testes para novas funcionalidades
3. Mantenha cobertura de código acima de 90%
4. Use TypeScript para segurança de tipos
5. Siga as configurações ESLint e Prettier

### Passos para Contribuição

1. Faça fork do repositório
2. Crie uma branch de feature: `git checkout -b feature/nova-funcionalidade`
3. Faça alterações e adicione testes
4. Execute testes: `npm test`
5. Commit das alterações: `git commit -m "feat: adicionar nova funcionalidade"`
6. Push para a branch: `git push origin feature/nova-funcionalidade`
7. Abra um Pull Request

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