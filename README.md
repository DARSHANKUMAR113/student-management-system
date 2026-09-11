# student-management-system
Student Management REST API built with Spring Boot, JWT authentication, Spring Security, MySQL, JPA,.

# Student Management System API

A secure and scalable **Student Management System REST API** built with **Spring Boot**. The application provides user registration and login using **JWT authentication**, role-based authorization, and complete CRUD operations for managing students.

The project uses **Spring Security**, **Spring Data JPA**, **MySQL**, **JWT**, **Validation**.

## 🚀 Features

### Authentication & Security

* User registration
* User login
* JWT-based authentication
* Access token and refresh token support
* Password encryption
* Role-based authorization
* Protected REST endpoints using Spring Security

### Student Management

* Create a student
* Get student by ID
* Get all students
* Update student
* Delete student
* Search students by keyword
* Pagination and sorting
* Request validation
* Standardized API responses

### API Documentation

* Swagger/OpenAPI integration
* Interactive API documentation
* Easy API testing through Swagger UI

## 🛠️ Technologies Used

| Technology        | Purpose                        |
| ----------------- | ------------------------------ |
| Java 21           | Programming Language           |
| Spring Boot 4.1.0 | Backend Framework              |
| Spring Web MVC    | REST API                       |
| Spring Security   | Authentication & Authorization |
| JWT               | Token-based Authentication     |
| Spring Data JPA   | Database Access                |
| Hibernate         | ORM                            |
| MySQL             | Database                       |
| Lombok            | Reduce Boilerplate Code        |
| Bean Validation   | Request Validation             |
| Swagger / OpenAPI | API Documentation              |
| Maven             | Build & Dependency Management  |

## 📁 Project Structure

```text
student-management-system/
│
├── src/
│   ├── main/
│   │   ├── java/com/student/sms/
│   │   │
│   │   ├── config/
│   │   │   └── PasswordConfig.java
│   │   │
│   │   ├── controller/
│   │   │   ├── AuthController.java
│   │   │   └── StudentController.java
│   │   │
│   │   ├── dto/
│   │   │   ├── request/
│   │   │   └── response/
│   │   │
│   │   ├── entity/
│   │   │
│   │   ├── exception/
│   │   │
│   │   ├── repository/
│   │   │
│   │   ├── security/
│   │   │   ├── CustomUserDetailsService.java
│   │   │   ├── JwtAuthenticationFilter.java
│   │   │   └── JwtService.java
│   │   │
│   │   ├── service/
│   │   │   └── impl/
│   │   │
│   │   └── StudentManagementSystemApplication.java
│   │
│   └── resources/
│       └── application.properties
│
├── pom.xml
├── mvnw
├── mvnw.cmd
└── README.md
```

## 🔐 Authentication

The API uses **JWT (JSON Web Token)** authentication.

Authentication flow:

```text
Register
   ↓
Login
   ↓
JWT Access Token
   ↓
Send Token with API Request
   ↓
JWT Authentication Filter
   ↓
Spring Security
   ↓
Role-Based Authorization
   ↓
Protected Resource
```

## 👥 Roles

The application supports role-based access control.

### ADMIN

Administrators can:

* Create students
* View students
* Update students
* Delete students
* Search students

### TEACHER

Teachers can:

* View students
* Search students

Student modification operations are restricted to administrators.

## 🔗 API Endpoints

### Authentication

#### Register

```http
POST /api/v1/auth/register
```

#### Login

```http
POST /api/v1/auth/login
```

### Student Management

#### Create Student

```http
POST /api/v1/students
```

**Role:** ADMIN

#### Get Student

```http
GET /api/v1/students/{id}
```

**Role:** ADMIN, TEACHER

#### Get All Students

```http
GET /api/v1/students
```

**Role:** ADMIN, TEACHER

Supports pagination and sorting.

Example:

```http
GET /api/v1/students?page=0&size=10&sort=firstName
```

**Role:** ADMIN, TEACHER

#### Update Student

```http
PUT /api/v1/students/{id}
```

**Role:** ADMIN

#### Delete Student

```http
DELETE /api/v1/students/{id}
```

**Role:** ADMIN

## 🗄️ Database Configuration

This project uses **MySQL**.

Create the database:

```sql
CREATE DATABASE student_management;
```

Then configure your database connection in:

```text
src/main/resources/application.properties
```

Example:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/student_management
spring.datasource.username=root
spring.datasource.password=YOUR_PASSWORD
```

> **Important:** Do not commit your real database password or JWT secret to GitHub.

For a public repository, use environment variables instead of hardcoding credentials.

Example:

```properties
spring.datasource.url=${DB_URL}
spring.datasource.username=${DB_USERNAME}
spring.datasource.password=${DB_PASSWORD}

jwt.secret=${JWT_SECRET}
```

## ⚙️ Configuration

The application runs on:

```text
http://localhost:8081
```

The database schema is automatically updated using:

```properties
spring.jpa.hibernate.ddl-auto=update
```

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/student-management-system-api.git
```

### 2. Open the project

Open the project in IntelliJ IDEA, Eclipse, or another Java IDE.

### 3. Configure MySQL

Create the database:

```sql
CREATE DATABASE student_management;
```

Update the database credentials in `application.properties` or configure environment variables.

### 4. Build the project

Using Maven:

```bash
./mvnw clean install
```

On Windows:

```bash
mvnw.cmd clean install
```

### 5. Run the application

```bash
./mvnw spring-boot:run
```

On Windows:

```bash
mvnw.cmd spring-boot:run
```

The API will start at:

```text
http://localhost:8081
```

## 📚 Swagger API Documentation

After starting the application, Swagger UI can be accessed at:

```text
http://localhost:8081/swagger-ui/index.html
```

Swagger provides an interactive interface for testing the available REST APIs.

## 🧪 API Testing

You can test the APIs using:

* Swagger UI
* Postman
* Insomnia
* cURL

For protected endpoints, first authenticate using the login endpoint and then provide the JWT access token in the authorization header:

```http
Authorization: Bearer YOUR_ACCESS_TOKEN
```

## 📌 Future Improvements

Possible improvements for future versions:

* Student attendance management
* Course and subject management
* Teacher management
* Admin dashboard
* Email notifications
* Profile management
* Docker support
* Unit and integration tests
* CI/CD with GitHub Actions
* Production deployment
* Redis-based caching
* Centralized exception handling improvements

## 👨‍💻 Author

Takarwadiya Darshankumar Laxmanji

GitHub:github.com/DARSHANKUMAR113


