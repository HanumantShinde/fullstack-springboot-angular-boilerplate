# Full Stack Spring Boot + Angular Boilerplate

A personal full-stack boilerplate I built to eliminate repetitive project setup. Authentication, security, database connection, and frontend routing are already configured so you can focus on building features.

## Tech Stack

| Layer          | Technology            |
| -------------- | --------------------- |
| Backend        | Spring Boot 3.5       |
| Frontend       | Angular 19            |
| Database       | MySQL                 |
| Authentication | JWT (JSON Web Tokens) |
| Security       | Spring Security       |
| ORM            | JPA / Hibernate       |
| Build Tool     | Maven                 |

---

## What's Already Built

* JWT-based stateless authentication
* Spring Security with public and protected routes
* Login API that returns JWT tokens
* User entity with JPA and MySQL integration
* Complete CRUD REST API
* Layered architecture (Controller → Service → Repository)
* Angular frontend with routing
* HTTP service integration
* CORS configuration
* Automatic 401 Unauthorized responses for invalid or missing tokens

---

## Architecture

```text
Angular Frontend (localhost:4200)
            ↓
Spring Boot Backend (localhost:8080)
            ↓
      Controller Layer
            ↓
       Service Layer
            ↓
     Repository Layer
            ↓
       MySQL Database
```

---

## Project Structure

```text
fullstack-springboot-angular-boilerplate
│
├── .mvn/
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   ├── angular.json
│   └── README.md
│
├── src/
│   ├── main/
│   │   ├── java/com/starter/fullstack/
│   │   │   ├── controller/
│   │   │   │   ├── AuthController.java
│   │   │   │   └── UserController.java
│   │   │   ├── service/
│   │   │   │   └── UserService.java
│   │   │   ├── repository/
│   │   │   │   └── UserRepository.java
│   │   │   ├── model/
│   │   │   │   └── User.java
│   │   │   ├── security/
│   │   │   │   ├── SecurityConfig.java
│   │   │   │   ├── JwtUtil.java
│   │   │   │   └── JwtFilter.java
│   │   │   ├── FullstackStarterApplication.java
│   │   │   └── TestController.java
│   │   │
│   │   └── resources/
│   │
│   └── test/
│
├── pom.xml
├── mvnw
└── mvnw.cmd
```

---

## Getting Started

### Prerequisites

* Java 17+
* Node.js 18+
* MySQL 8+
* Maven

---

## Backend Setup

```bash
git clone https://github.com/HanumantShinde/fullstack-springboot-angular-boilerplate.git

cd fullstack-springboot-angular-boilerplate

# Configure application.properties

spring.datasource.url=jdbc:mysql://localhost:3306/your_database
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update

# Run Spring Boot

mvn spring-boot:run
```

Backend runs on:

```text
http://localhost:8080
```

---

## Frontend Setup

```bash
cd frontend

npm install

ng serve
```

Frontend runs on:

```text
http://localhost:4200
```

---

## API Endpoints

### Authentication (Public)

| Method | Endpoint        | Description                 |
| ------ | --------------- | --------------------------- |
| POST   | /api/auth/login | Login and receive JWT token |

### Users (Protected)

| Method | Endpoint        |
| ------ | --------------- |
| GET    | /api/users      |
| POST   | /api/users      |
| PUT    | /api/users/{id} |
| DELETE | /api/users/{id} |

---

## Authentication Flow

```text
1. POST /api/auth/login
2. Validate credentials
3. Generate JWT token
4. Return token to client
5. Include token in Authorization header

Authorization: Bearer <token>

6. Protected APIs validate token
7. Invalid token → 401 Unauthorized
```

---

## Why I Built This

Every project starts with the same setup:

* Spring Security configuration
* JWT authentication
* MySQL connection
* Angular routing
* CORS setup

This boilerplate removes that repetitive work so developers can immediately start building business features.

---

## Built With

* Spring Boot
* Angular
* MySQL
* Spring Security
* JJWT

---

## Author

**Hanumant Shinde**

If this project helps you, consider giving it a ⭐ on GitHub.
