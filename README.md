# Online Poll Application

A simple **Spring Boot** application that allows users to create polls, share them with others via a link or API, and collect votes in real time. Ideal for gathering quick opinions, feedback, or survey data using a RESTful backend.

---


## Tech Stack

- **Java:** 17  
- **Framework:** Spring Boot  
- **Build Tool:** Maven  
- **Database:** PostgreSQL  
- **API Style:** REST  

---

## ✨ Features

- User authentication
- Create polls with multiple options
- Share polls using unique links (slugs)
- Vote on polls
- View poll results
- RESTful APIs

---

## 📋 Prerequisites

Make sure you have:

- Java 17 (JDK)
- Maven 3.8+
- PostgreSQL 13+

Verify installation:

```bash
java -version
mvn -version
psql --version
```

---

## 🚀 Getting Started

### Clone the Repository

```bash
git clone <repository-url>
cd <project-directory>
```

## Configuration

Configuration files:

* `src/main/resources/application.properties`

Common settings:

* Database url (host, port, name)
* Database username
* Database password

---

## Database Setup (PostgreSQL)

Login to postgres:

```bash
psql -U postgres
```

Create the database (match with application.properties):

```bash
CREATE DATABASE 'database_name';
```

Create a dedicated user (match with application.properties):

```bash
CREATE USER 'username' WITH PASSWORD 'password';
GRANT ALL PRIVILEGES ON DATABASE 'database_name' TO 'username';
```

Exit:

```bash
\q
```

---

### Build the Application

```bash
mvn clean install
```

### Run the Application

```bash
mvn spring-boot:run
```

---

## 🌐 API Endpoints

Below are the main REST API endpoints used by the Online Poll Application.

### 🔐 Authentication

- **Sign In**

```http
GET /user/signing?username={username}&password={password}
```

> Authenticates a user with username and password.

---

### 📊 Polls

- **Get All Polls**

```http
GET /poll/find-all
```

- **Get Poll by Link (Slug)**

```http
GET /poll/find-by-link/{pollSlug}
```

- **Create a Poll**

```http
POST /poll/create
```

- **Edit a Poll**

```http
PUT /poll/edit/{pollSlug}
```

- **Delete a Poll**

```http
DELETE /poll/delete/{pollSlug}
```

---

### 🗳️ Voting

- **Vote on a Poll**

```http
POST /participant/create?selectedOptionsId={options}
```

> `selectedOptionsId` may contain one or multiple option IDs depending on poll configuration.

