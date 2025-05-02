![Static Badge](https://img.shields.io/badge/Ariel%20Spencer-Readme%20Templates-%239377be) ![GitHub License](https://img.shields.io/github/license/arielspencer/readme-templates) [![Traduzir para Português](https://img.shields.io/badge/Traduzir%20Para-🇧🇷%20Portuguese-%23f5bb55)](simple-page-pt-br.md)

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

# Project Name

**Brief description**: Summary about the project (what it does and what problem it solves).

## 🎯 API Overview

<p align="center">
    <img src="../images/screenshot.png" alt="API Architecture" width="600px">
</p>

## 📚 Index

- [Description](#-description)
- [Technologies](#-technologies)
- [Installation and Usage](#-installation-and-usage)
- [API Endpoints](#-api-endpoints)
- [Environment Variables](#-environment-variables)
- [Database Schema](#-database-schema)
- [Authentication](#-authentication)
- [Testing](#-testing)
- [Docker](#-docker)
- [Contributions](#-contributions)
- [License](#-license)

## ✏️ Description

A more detailed explanation of the project and its purpose.

## 👾 Technologies

A list of technologies and tools used to develop the project.  
Example:

- Node.js
- TypeScript
- Express.js
- PostgreSQL
- Prisma ORM
- JWT Authentication
- Docker
- Redis
- Jest

## 🤖 Installation and Usage

### Prerequisites

List of dependencies and tools needed to run the project.  
Example:
- [Node.js](https://nodejs.org/en/docs/) (version: 18.17.1)
- [PostgreSQL](https://www.postgresql.org/) (version: 14+)
- [Docker](https://docs.docker.com/) (optional)

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/ArielSpencer/readme-templates.git
    ```

2. Navigate to the project directory:
    ```bash
    cd readme-templates
    ```

3. Install the necessary dependencies:
    ```bash
    npm install
    ```

4. Configure environment variables:
    ```bash
    cp .env.example .env
    ```

5. Set up the database:
    ```bash
    npm run db:migrate
    npm run db:seed
    ```

6. Start the application in development mode:
    ```bash
    npm run dev
    ```

### Available Scripts

Details about useful scripts:

- **`npm start`**: Starts the application in production mode.
- **`npm run dev`**: Starts the application in development mode with hot reload.
- **`npm run build`**: Builds the application for production.
- **`npm run test`**: Runs the test suite.
- **`npm run db:migrate`**: Runs database migrations.
- **`npm run db:seed`**: Seeds the database with initial data.

## 📡 API Endpoints

### Authentication
- `POST /auth/login` - User login
- `POST /auth/register` - User registration
- `POST /auth/refresh` - Refresh access token

### Users
- `GET /users` - List all users
- `GET /users/:id` - Get user by ID
- `PUT /users/:id` - Update user
- `DELETE /users/:id` - Delete user

### Example Request/Response

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

## 🔧 Environment Variables

Create a `.env` file in the root directory with the following variables:

```env
NODE_ENV=development
PORT=3000
DATABASE_URL=postgresql://username:password@localhost:5432/database_name
JWT_SECRET=your_jwt_secret_key
REDIS_URL=redis://localhost:6379
```

## 🎲 Database Schema

### Users Table
| Column    | Type      | Description           |
|-----------|----------|-----------------------|
| id        | INTEGER  | Primary key           |
| email     | VARCHAR  | User email (unique)   |
| password  | VARCHAR  | Hashed password       |
| name      | VARCHAR  | User full name        |
| created_at| TIMESTAMP| Creation timestamp    |
| updated_at| TIMESTAMP| Last update timestamp |

## 🔐 Authentication

This API uses JWT (JSON Web Tokens) for authentication. Include the token in the Authorization header:

```bash
Authorization: Bearer your_jwt_token_here
```

## 🧪 Testing

Run the test suite:

```bash
npm run test
```

Run tests with coverage:

```bash
npm run test:coverage
```

## 🐳 Docker

### Running with Docker

1. Build the image:
    ```bash
    docker build -t project-name .
    ```

2. Run the container:
    ```bash
    docker run -p 3000:3000 project-name
    ```

### Using Docker Compose

```bash
docker-compose up -d
```

## 🧑‍🤝‍🧑 Contributions

Guidelines on how to contribute to the project with forks, pull requests, etc.

### Contribution Steps:

1. Clone the repository:

    ```bash
    git clone https://github.com/ArielSpencer/readme-templates.git
    ```

2. Create a new branch:

    ```bash
    git checkout -b feature/NAME
    ```

3. Follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) commit standards:

    ```bash
    git commit -m "feat(api): add user authentication endpoint"
    ```

4. Open a Pull Request explaining the issue resolved or the feature added. If there are visual modifications, attach a screenshot and await review!

    [More details on how to create a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

## ☕️ Developed by

<div align="center">
    <div style="display: inline-block; margin: 0 30px;">
        <a href="https://github.com/ArielSpencer">
            <img src="https://github.com/ArielSpencer.png" alt="Ariel Spencer" width="130px" style="border-radius:50%">
        </a>
        <p>Ariel Spencer</p>
        <a href="https://arielspencer.com.br">
            <img alt="Website Ariel Spencer" src="https://img.shields.io/badge/arielspencer.com.br-%239377be">
        </a>
    </div>
</div>

## 📝 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).