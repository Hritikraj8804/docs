---
title: "Food Ordering System"
date: 2025-11-01
tags: ["Java", "Spring Boot", "MySQL", "Vue.js", "JWT"]
description: "Enterprise-grade Food Ordering System featuring JWT authentication, RBAC, and real-time order processing"
source: "https://github.com/Hritikraj8804/food-ordering-system"
featured: true
---

## Overview

**Food Ordering System** is a robust Spring Boot application designed to manage restaurant orders with enterprise-grade security and scalability. It features a complete ecosystem for users, restaurant owners, and delivery management.

## Key Features

- **🔐 Enterprise Security**: Implementation of JWT Authentication with Spring Security and BCrypt password encryption
- **👤 Role-Based Access (RBAC)**: Distinct panels for Users and Hotel Managers with strict resource ownership validation
- **🛒 Order Processing**: Atomic transaction management for reliable order handling and status tracking
- **🏨 Restaurant Management**: Complete CRUD operations for restaurants, menus, and image handling
- **📊 Enterprise Logging**: Structured logging with AOP (Aspect-Oriented Programming) integration

## Project Architecture

1. **Backend Layer**: Layered architecture (Controller → Service → Repository → Entity) ensuring separation of concerns
2. **Security Flow**: Request -> JWT Filter -> Spring Security Context -> Protected Resource
3. **Frontend Integration**: Built with Vue.js 3 and Vite, consuming RESTful APIs via Axios

## Tech Stack

| Technology | Purpose |
|------------|---------|
| **Java 17** | Core Language |
| **Spring Boot 3** | Backend Framework |
| **MySQL 8.0** | Relational Database |
| **Hibernate/JPA** | ORM & Data Access |
| **Vue.js 3** | Frontend (Composition API) |
| **JWT** | Stateless Authentication |

## Getting Started

```bash
# Clone the repository
git clone https://github.com/Hritikraj8804/food-ordering-system.git
cd food-ordering-system

# Configure Database
# Update src/main/resources/application.properties
# spring.datasource.url=jdbc:mysql://localhost:3306/food_ordering_db

# Run Backend
mvn spring-boot:run

# Run Frontend
cd frontend
npm install
npm run dev
```

---

*A comprehensive solution demonstrating modern enterprise application development with Spring Boot.*
