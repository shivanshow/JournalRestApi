# JournalRestApi

A secure and stateless REST API for managing personal journal entries. Built with **Spring Boot**, **MongoDB**, and **Spring Security**.

## ✨ Features

- User registration and authentication
- Secure journal entry creation, retrieval, and listing
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

> All `/journal/**` routes require HTTP Basic Auth.

| Method | Endpoint                  | Description                         |
|--------|---------------------------|-------------------------------------|
| POST   | `/register`               | Register a new user                 |
| POST   | `/journal/{username}`     | Add journal entry for user          |
| GET    | `/journal/{username}`     | Get all entries for user            |
| GET    | `/journal/id/{id}`        | Fetch specific journal by ID        |

## 🔐 Authentication

- Basic Auth
- Passwords are stored securely using BCrypt
- Stateless session policy (no cookies/sessions)

## 📂 Sample JSON Payload (Journal Entry)

```json
{
  "title": "My First Entry",
  "content": "This is what I wrote today."
}
```
