# Database Fundamentals

> Before learning SQL, PostgreSQL, MySQL, Prisma, or MongoDB, you must understand what a database is and why we use it.

---

# Table of Contents

1. What is a Database?
2. Relational Database vs NoSQL
3. SQL Basics
4. CRUD Operations

---

# 1. What is a Database?

## Definition

A **Database** is an organized collection of data that is stored electronically so it can be accessed, managed, updated, and retrieved efficiently.

In simple words,

> A database is a place where an application stores its data.

---

## Why Do We Need a Database?

Imagine you're building a social media application like Facebook.

You need to store:

- Users
- Posts
- Comments
- Likes
- Messages
- Followers

Where should all this information be stored?

The answer is:

**Database**

Without a database, your application cannot permanently save data.

---

## Real World Example

Suppose a user signs up.

```
Name: Soikat
Email: soikat@gmail.com
Password: ********
```

This information is saved inside a database.

Later, when the user logs in, the application asks the database:

```
Does this email exist?
```

The database returns the matching user.

---

## Database Structure

```
Database

│

├── Users Table

├── Posts Table

├── Comments Table

├── Messages Table

└── Likes Table
```

A database usually contains multiple tables.

---

## Popular Databases

| Database   | Type       |
| ---------- | ---------- |
| PostgreSQL | Relational |
| MySQL      | Relational |
| SQLite     | Relational |
| SQL Server | Relational |
| Oracle     | Relational |
| MongoDB    | NoSQL      |
| Redis      | Key-Value  |
| Cassandra  | NoSQL      |

---

# 2. Relational Database vs NoSQL

There are two major types of databases.

- Relational Database (SQL)
- NoSQL Database

---

# Relational Database

A Relational Database stores data inside **tables**.

Example:

Users Table

| id  | name   | email            |
| --- | ------ | ---------------- |
| 1   | Soikat | soikat@gmail.com |
| 2   | Rahim  | rahim@gmail.com  |

Posts Table

| id  | title    | authorId |
| --- | -------- | -------- |
| 1   | Hello    | 1        |
| 2   | Database | 2        |

Notice that:

The **authorId** connects a post to a user.

Tables are related to each other.

That is why it is called a **Relational Database**.

---

## Examples

- PostgreSQL
- MySQL
- SQLite
- Oracle
- SQL Server

---

# NoSQL Database

NoSQL stores data differently.

Instead of tables, it often stores documents.

Example:

```json
{
  "name": "Soikat",
  "email": "soikat@gmail.com",
  "skills": ["Node.js", "Prisma", "React"]
}
```

Everything is stored inside one document.

---

## Examples

- MongoDB
- Cassandra
- Redis
- DynamoDB

---

# SQL vs NoSQL

| SQL                      | NoSQL                                            |
| ------------------------ | ------------------------------------------------ |
| Stores data in tables    | Stores data as documents, key-value, graph, etc. |
| Fixed schema             | Flexible schema                                  |
| Uses SQL language        | Uses different query languages                   |
| Supports JOIN            | Usually avoids JOIN                              |
| Best for structured data | Best for flexible or changing data               |
| ACID support             | Often prioritizes scalability                    |

---

## Which One Should You Learn?

For backend development:

✅ PostgreSQL

After PostgreSQL:

✅ MongoDB

Learning SQL first makes NoSQL much easier.

---

# 3. SQL Basics

SQL stands for

> Structured Query Language

SQL is the language used to communicate with relational databases.

Example:

```
Application

↓

SQL

↓

Database

↓

Result
```

Using SQL, we can:

- Create tables
- Read data
- Insert data
- Update data
- Delete data

---

## Example

```
SELECT * FROM users;
```

Meaning:

Return all users.

---

```
INSERT INTO users (...);
```

Meaning:

Create a new user.

---

```
UPDATE users ...
```

Meaning:

Modify existing data.

---

```
DELETE FROM users ...
```

Meaning:

Remove data.

---

# 4. CRUD Operations

Every application performs four basic operations.

CRUD means

```
C = Create

R = Read

U = Update

D = Delete
```

---

## Create

Add new data.

Example

```
Create User

Name: Soikat

Email: soikat@gmail.com
```

SQL

```sql
INSERT INTO users(name,email)
VALUES('Soikat','soikat@gmail.com');
```

---

## Read

Read existing data.

SQL

```sql
SELECT *
FROM users;
```

---

## Update

Modify existing data.

SQL

```sql
UPDATE users
SET name='Asif'
WHERE id=1;
```

---

## Delete

Remove existing data.

SQL

```sql
DELETE FROM users
WHERE id=1;
```

---

# CRUD Flow

```
User clicks Register

↓

Backend receives request

↓

INSERT query

↓

Database stores data

↓

Success Response
```

---

```
User opens Profile

↓

Backend

↓

SELECT query

↓

Database

↓

User Information
```

---

```
User changes Name

↓

Backend

↓

UPDATE query

↓

Database

↓

Updated Successfully
```

---

```
User deletes Account

↓

Backend

↓

DELETE query

↓

Database

↓

Account Removed
```

---

# Summary

## Database

Stores application data permanently.

---

## Relational Database

Stores data inside related tables.

Examples:

- PostgreSQL
- MySQL

---

## NoSQL Database

Stores data as documents or other flexible structures.

Example:

- MongoDB

---

## SQL

The language used to communicate with relational databases.

---

## CRUD

Every application performs:

- Create
- Read
- Update
- Delete

These are the four fundamental operations of any database application.

---

# What's Next?

Next chapter:

- SELECT
- INSERT
- UPDATE
- DELETE
- WHERE
- ORDER BY

These are the most frequently used SQL commands in real-world projects.
