![Static Badge](https://img.shields.io/badge/Ariel%20Spencer-Readme%20Templates-%239377be) ![GitHub License](https://img.shields.io/github/license/arielspencer/readme-templates) [![Traduzir para Português](https://img.shields.io/badge/Traduzir%20Para-🇧🇷%20Portuguese-%23f5bb55)](api-rest-pt-br.md)

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

# Project Name API

**Brief description**: RESTful API for [project purpose] with JWT authentication and complete CRUD operations.

## 🚀 API Status

![API Status](https://img.shields.io/badge/API-Online-success)
![Version](https://img.shields.io/badge/Version-1.0.0-blue)
![Coverage](https://img.shields.io/badge/Coverage-95%25-brightgreen)

**Base URL**: `https://api.example.com/v1`

## 📚 Index

- [Description](#-description)
- [Features](#-features)
- [Technologies](#-technologies)
- [Installation and Usage](#-installation-and-usage)
- [API Documentation](#-api-documentation)
- [Authentication](#-authentication)
- [Database Schema](#-database-schema)
- [Error Handling](#-error-handling)
- [Rate Limiting](#-rate-limiting)
- [Monitoring](#-monitoring)
- [Testing](#-testing)
- [Deployment](#-deployment)
- [Contributions](#-contributions)
- [License](#-license)

## ✏️ Description

A robust RESTful API built with Node.js and Express.js, featuring JWT authentication, input validation, rate limiting, and comprehensive error handling. This API provides endpoints for [describe main functionality].

## ✨ Features

- JWT-based authentication
- Input validation with Joi
- Rate limiting and security headers
- Comprehensive error handling
- Request/Response logging
- API documentation with Swagger
- Unit and integration tests
- Database migrations and seeds
- Health check endpoints
- CORS configuration

## 👾 Technologies

**Backend Framework:**
- Node.js (v18+)
- Express.js
- TypeScript

**Database & ORM:**
- PostgreSQL
- Prisma ORM

**Authentication & Security:**
- JWT (JSON Web Tokens)
- bcrypt
- helmet
- express-rate-limit

**Validation & Documentation:**
- Joi (input validation)
- Swagger/OpenAPI 3.0

**Testing:**
- Jest
- Supertest

**Development Tools:**
- ESLint
- Prettier
- Husky (Git hooks)

## 🤖 Installation and Usage

### Prerequisites

- [Node.js](https://nodejs.org/) (v18.17.1 or higher)
- [PostgreSQL](https://www.postgresql.org/) (v14 or higher)
- [Docker](https://www.docker.com/) (optional)

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/username/project-name.git
    cd project-name
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

3. Set up environment variables:
    ```bash
    cp .env.example .env
    # Edit .env with your configuration
    ```

4. Set up the database:
    ```bash
    npm run db:migrate
    npm run db:seed
    ```

5. Start the development server:
    ```bash
    npm run dev
    ```

### Environment Variables

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

### Available Scripts

- **`npm run dev`**: Start development server with hot reload
- **`npm start`**: Start production server
- **`npm run build`**: Build TypeScript to JavaScript
- **`npm test`**: Run test suite
- **`npm run test:watch`**: Run tests in watch mode
- **`npm run test:coverage`**: Run tests with coverage report
- **`npm run db:migrate`**: Run database migrations
- **`npm run db:seed`**: Seed database with sample data
- **`npm run db:reset`**: Reset database (migrate + seed)
- **`npm run lint`**: Run ESLint
- **`npm run format`**: Format code with Prettier

## 📡 API Documentation

### Base Information

- **Base URL**: `/api/v1`
- **Authentication**: Bearer Token (JWT)
- **Content-Type**: `application/json`

### Authentication Endpoints

#### Register User
```http
POST /api/v1/auth/register
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "securePassword123"
}
```

**Response (201):**
```json
{
  "success": true,
  "data": {
    "user": {
      "id": 1,
      "name": "John Doe",
      "email": "john@example.com",
      "createdAt": "2023-01-01T00:00:00.000Z"
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
  }
}
```

#### Login User
```http
POST /api/v1/auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "securePassword123"
}
```

### User Management Endpoints

#### Get All Users
```http
GET /api/v1/users
Authorization: Bearer {token}
```

#### Get User by ID
```http
GET /api/v1/users/{id}
Authorization: Bearer {token}
```

#### Update User
```http
PUT /api/v1/users/{id}
Authorization: Bearer {token}
Content-Type: application/json

{
  "name": "Jane Doe",
  "email": "jane@example.com"
}
```

#### Delete User
```http
DELETE /api/v1/users/{id}
Authorization: Bearer {token}
```

### Health Check
```http
GET /api/v1/health
```

**Response:**
```json
{
  "status": "ok",
  "timestamp": "2023-01-01T00:00:00.000Z",
  "database": "connected",
  "uptime": "2h 30m 45s"
}
```

### Interactive Documentation

Access the Swagger UI at: `http://localhost:3000/api-docs`

## 🔐 Authentication

This API uses JWT (JSON Web Tokens) for authentication. Include the token in the Authorization header:

```bash
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
```

### Token Flow
1. Register or login to receive a JWT token
2. Include the token in the `Authorization` header for protected routes
3. Tokens expire after 7 days (configurable)

## 🎲 Database Schema

### Users Table
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

### Migrations

Run migrations to set up the database:
```bash
npm run db:migrate
```

## ❌ Error Handling

The API uses standardized error responses:

```json
{
  "success": false,
  "error": {
    "message": "Resource not found",
    "code": "RESOURCE_NOT_FOUND",
    "statusCode": 404
  }
}
```

### Common Error Codes

| Code | Status | Description |
|------|--------|-------------|
| `VALIDATION_ERROR` | 400 | Invalid input data |
| `UNAUTHORIZED` | 401 | Missing or invalid token |
| `FORBIDDEN` | 403 | Insufficient permissions |
| `RESOURCE_NOT_FOUND` | 404 | Resource does not exist |
| `CONFLICT` | 409 | Resource already exists |
| `RATE_LIMIT_EXCEEDED` | 429 | Too many requests |
| `INTERNAL_SERVER_ERROR` | 500 | Server error |

## ⚡ Rate Limiting

API endpoints are rate-limited to prevent abuse:

- **Window**: 15 minutes
- **Max Requests**: 100 per window per IP
- **Headers**: Rate limit info included in response headers

```http
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 95
X-RateLimit-Reset: 1640995200
```

## 📊 Monitoring

### Health Checks
- **Endpoint**: `GET /api/v1/health`
- **Database**: Connection status
- **Uptime**: Server uptime information

### Logging
- All requests and responses are logged
- Error tracking and monitoring
- Performance metrics collection

## 🧪 Testing

### Running Tests
```bash
# Run all tests
npm test

# Run tests in watch mode
npm run test:watch

# Run tests with coverage
npm run test:coverage
```

### Test Categories
- **Unit Tests**: Individual functions and modules
- **Integration Tests**: API endpoints and database operations
- **Authentication Tests**: JWT and security features

### Test Coverage
Maintain minimum 90% test coverage for:
- Controllers
- Services
- Middleware
- Utilities

## 🚢 Deployment

### Docker Deployment
```bash
# Build image
docker build -t project-name-api .

# Run container
docker run -p 3000:3000 --env-file .env project-name-api
```

### Production Checklist
- [ ] Environment variables configured
- [ ] Database migrations run
- [ ] SSL/HTTPS enabled
- [ ] Rate limiting configured
- [ ] Monitoring and logging set up
- [ ] Health checks implemented

## 🧑‍🤝‍🧑 Contributions

### Development Guidelines

1. Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification
2. Write tests for new features
3. Maintain code coverage above 90%
4. Use TypeScript for type safety
5. Follow ESLint and Prettier configurations

### Contribution Steps

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-feature`
3. Make changes and add tests
4. Run tests: `npm test`
5. Commit changes: `git commit -m "feat: add new feature"`
6. Push to branch: `git push origin feature/new-feature`
7. Open a Pull Request

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