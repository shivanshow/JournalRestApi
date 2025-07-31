# JournalRestApi

A secure and stateless REST API for managing personal journal entries. Built with **Spring Boot**, **MongoDB**, and **Spring Security**.

## ✨ Features

- User registration and authentication
- Secure journal entry creation, retrieval, update, and deletion
- MongoDB integration with `@DBRef` relations
- Role-based authorization (`User`, `Admin`, etc.)
- Passwords hashed with BCrypt
- Designed for Postman testing

## ☁️ Database

This project uses **MongoDB Atlas (Cloud)** as the backend database, enabling:

- Cloud-hosted database access
- Scalable and secure data storage
- Easy remote access without local setup

Make sure to configure your `application.properties` (or `.yml`) with your MongoDB URI:

```properties
spring.data.mongodb.uri=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/journalApp
```

## 🛠️ Tech Stack

- Java 17+
- Spring Boot
- Spring Security
- Spring Data MongoDB
- Lombok
- Maven

## 🚀 Endpoints Overview

> All `/journal/**` and `PUT /user/**` routes require **HTTP Basic Auth**.

### 📘 Journal Endpoints

| Method | Endpoint                            | Description                                  |
|--------|-------------------------------------|----------------------------------------------|
| POST   | `/journal/{username}`               | Create a new journal entry for a user        |
| GET    | `/journal/{username}`               | Get all journal entries for a user           |
| GET    | `/journal/id/{id}`                  | Get a journal entry by its ID                |
| PUT    | `/journal/id/{username}/{id}`       | Update a specific journal entry by ID        |
| DELETE | `/journal/id/{username}/{id}`       | Delete a specific journal entry by ID        |

### 👤 User Endpoints

| Method | Endpoint           | Description                          |
|--------|--------------------|--------------------------------------|
| POST   | `/register`        | Register a new user                  |
| POST   | `/user`            | Create a new user (alternate path)   |
| PUT    | `/user/{username}` | Update user info (requires auth)     |

## 🔐 Authentication

- Basic Auth required for protected endpoints
- Passwords are stored securely using BCrypt
- Stateless session policy (no cookies/sessions)

## 📂 Sample JSON Payloads

### Journal Entry

```json
{
  "title": "My First Entry",
  "content": "This is what I wrote today."
}
```

### User Registration

```json
{
  "userName": "john_doe",
  "password": "securepassword123"
}
```
