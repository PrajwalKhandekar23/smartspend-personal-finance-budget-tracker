# 💰 SmartSpend – Personal Finance & Budget Tracker

SmartSpend is a full-stack personal finance management application developed by **Prajwal Khandekar**. It helps users manage their income and expenses, create monthly category-wise budgets, and monitor their financial activities through an interactive dashboard.

Built using **Java, Spring Boot, Spring MVC, Spring Security, Hibernate, Spring Data JPA, Thymeleaf, and PostgreSQL**, this project demonstrates practical full-stack development, secure authentication, database management, and financial data visualization.

---

## 🚀 Features

### 🔐 Authentication & Security

- Secure user registration and login using Spring Security.
- Password encryption using BCrypt.
- Role-based user structure (`USER`, `ADMIN`).
- Custom `UserDetailsService` implementation for database-backed authentication.
- Secure session-based authentication.

### 💸 Transaction Management

- Add, edit, and delete income and expense transactions.
- Manage transactions using predefined categories.
- Support for categories such as Food, Rent, Travel, Salary, EMI, Medical, and Entertainment.
- Automatically classify transactions as income or expense.
- View transaction history for the logged-in user.

### 📊 Budget Management

- Create monthly budgets for individual expense categories.
- Update existing budgets without creating duplicate records.
- View all budgets in an organized interface.
- Delete budgets when they are no longer required.
- Maintain category-wise budget records for each user.

### 📈 Interactive Dashboard

- Display monthly Total Income, Total Expenses, and Balance.
- Visualize category-wise expenses using interactive pie charts.
- Integrate Chart.js for dynamic data visualization.
- Calculate financial summaries using custom JPQL aggregate queries.
- Handle users with no transaction history gracefully.

---

## 🛠️ Technology Stack

| Layer                | Technologies                      |
| -------------------- | --------------------------------- |
| Programming Language | Java                              |
| Backend Framework    | Spring Boot                       |
| Web Framework        | Spring MVC                        |
| Security             | Spring Security, BCrypt           |
| ORM                  | Hibernate                         |
| Persistence          | Spring Data JPA                   |
| Database             | PostgreSQL                        |
| Frontend             | Thymeleaf, HTML, CSS, Bootstrap 5 |
| Data Visualization   | Chart.js                          |
| Build Tool           | Maven                             |

---

## 🏗️ Project Architecture

SmartSpend follows a layered architecture that separates application responsibilities and improves maintainability.

text

```text
Controller → Service → Repository → Database
```

### Architecture Layers

- **Controller Layer:** Handles HTTP requests and manages application routing.
- **Service Layer:** Contains business logic, budget management, password encoding, and financial calculations.
- **Repository Layer:** Handles database operations using Spring Data JPA and custom JPQL queries.
- **Entity Layer:** Defines database entities and their relationships.
- **Configuration Layer:** Manages application security and configuration.
- **DTO Layer:** Transfers user-related data between application layers.

### Project Structure

text

```text
com.smartSpend
│
├── controller
│   ├── UserController
│   ├── TransactionController
│   └── BudgetController
│
├── service
│   └── Business logic and service interfaces
│
├── repository
│   └── Spring Data JPA repositories
│
├── entity
│   ├── User
│   ├── Transaction
│   ├── Category
│   └── Budget
│
├── enums
│   ├── Role
│   └── CategoryType
│
├── config
│   └── SecurityConfig
│
└── dto
    └── CustomUserDetails
```

---

## 🗄️ Database Design

The application uses PostgreSQL as its relational database.

The database consists of four primary entities:

| Entity      | Description                                 |
| ----------- | ------------------------------------------- |
| User        | Stores registered user information          |
| Transaction | Stores income and expense records           |
| Category    | Stores predefined transaction categories    |
| Budget      | Stores monthly category-wise budget details |

### Entity Relationships

text

```text
User (1) ───────── (Many) Transaction

User (1) ───────── (Many) Budget

Category (1) ───── (Many) Transaction

Category (1) ───── (Many) Budget
```

### Database Highlights

- Entity relationships managed using Hibernate/JPA.
- Foreign key relationships maintain data integrity.
- Categories are automatically initialized using `data.sql`.
- Supports income and expense category types.
- Prevents duplicate budgets for the same user, category, and month through service-layer validation.

---

## 📸 Screenshots

### Dashboard

\!SmartSpend Dashboard

The dashboard provides an overview of monthly financial activities, including income, expenses, balance, and category-wise spending distribution.

---

## ⚙️ Installation & Setup

Follow these steps to run SmartSpend locally.

### Prerequisites

Make sure you have installed:

- Java JDK 17 or compatible project-required version.
- Apache Maven.
- PostgreSQL.
- IntelliJ IDEA / Eclipse / Spring Tool Suite / VS Code.

### Step 1: Clone the Repository

bash

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

bash

```bash
cd SmartSpend
```

### Step 2: Configure PostgreSQL

Create a PostgreSQL database:

sql

```sql
CREATE DATABASE smartspend;
```

### Step 3: Configure Database Connection

Update your `application.properties` file:

properties

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/smartspend
spring.datasource.username=YOUR_DATABASE_USERNAME
spring.datasource.password=YOUR_DATABASE_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

spring.thymeleaf.cache=false
```

Replace the database username and password with your PostgreSQL credentials.

### Step 4: Run the Application

Using Maven:

bash

```bash
mvn spring-boot:run
```

Alternatively, run the main Spring Boot application class from your IDE.

### Step 5: Access the Application

Open your browser and visit:

text

```text
http://localhost:8080
```

---

## 📌 Key Technical Highlights

- Implemented secure authentication using Spring Security and BCrypt password encoding.
- Developed a custom `UserDetailsService` for database-backed user authentication.
- Used Spring Data JPA and Hibernate for object-relational mapping.
- Implemented custom JPQL aggregate queries for monthly income and expense calculations.
- Developed a custom Spring Converter to map submitted category IDs to Category entities.
- Implemented duplicate budget handling based on user, category, and month.
- Integrated Chart.js for interactive financial data visualization.
- Used defensive null handling to display zero values for users without transaction history.
- Followed a layered MVC architecture for clean code organization and maintainability.

---

## 🎯 Project Objectives

The primary objective of SmartSpend is to demonstrate practical knowledge of Java Full Stack Development through a real-world application.

This project showcases:

- Java and Spring Boot application development.
- Spring MVC architecture and RESTful/web request handling.
- Authentication and authorization using Spring Security.
- Database design and relational mapping.
- CRUD operations using Spring Data JPA and Hibernate.
- Custom JPQL queries and business logic implementation.
- Frontend development using Thymeleaf and Bootstrap.
- Data visualization using Chart.js.

---

## 👨‍💻 Developer

**Prajwal Khandekar**

Java Full Stack Developer

- **GitHub:** [Visit My GitHub Profile](https://github.com/PrajwalKhandekar23)

---

## 📄 License

This project is open source and available for educational and portfolio purposes.

---
