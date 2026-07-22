# 📚 Phase 1 - Database Fundamentals

> Before learning SQL, PostgreSQL, or Prisma, you must understand how databases work.

---

# 📖 Topics Covered

- What is a Database?
- Why Databases are Needed
- Data vs Information
- Database Terminology
- DBMS vs Database
- Types of Databases
- Relational Database
- NoSQL Database
- SQL vs NoSQL
- Database Architecture
- Client → Server → Database Flow
- Real-world Examples

---

# 1. What is a Database?

## Definition

A **Database** is an organized collection of data that is stored electronically so it can be easily **stored, managed, updated, and retrieved**.

### Simple Definition

> A database is a place where an application stores its data.

---

## Example

A Facebook database stores:

- Users
- Posts
- Comments
- Likes
- Messages

Without a database, an application cannot save data permanently.

---

# 2. Why Databases are Needed

Imagine storing millions of users inside a text file.

Problems:

- Slow searching
- Duplicate data
- Difficult updates
- Poor security
- Difficult to manage

A database solves these problems by providing:

- Fast searching
- Easy updates
- Better security
- Data consistency
- Multi-user support
- Backup & Recovery

---

# 3. Data vs Information

## Data

Raw facts without context.

Example:

```
Rahim
22
Dhaka
```

## Information

Processed data that has meaning.

Example:

```
Rahim is 22 years old and lives in Dhaka.
```

---

# 4. Database Terminology

## Database

A collection of related tables.

---

## Table

A collection of rows and columns.

Example:

| id  | name  | age |
| --- | ----- | --- |
| 1   | Rahim | 22  |
| 2   | Karim | 25  |

---

## Row (Record)

A single entry in a table.

Example:

|1|Rahim|22|

---

## Column (Field)

A single attribute of a table.

Example:

- id
- name
- age

---

# 5. DBMS vs Database

## Database

Stores the actual data.

## DBMS

A **Database Management System (DBMS)** is software used to create, manage, update, and access databases.

### Examples

- PostgreSQL
- MySQL
- Oracle
- SQL Server
- SQLite

### Easy Analogy

```
Database = Books

DBMS = Librarian
```

The librarian manages the books.

---

# 6. Types of Databases

Common database types:

- Relational Database
- NoSQL Database
- Key-Value Database
- Graph Database
- Document Database

For backend development, you'll mainly use:

- Relational Database
- NoSQL Database

---

# 7. Relational Database

A Relational Database stores data inside **tables**.

## Users

| id  | name  |
| --- | ----- |
| 1   | Rahim |
| 2   | Karim |

## Posts

| id  | title       | userId |
| --- | ----------- | ------ |
| 1   | Hello World | 1      |

Here, `userId` connects the post to a user.

Tables are related to each other.

That's why it is called a **Relational Database**.

### Examples

- PostgreSQL
- MySQL
- SQLite
- Oracle
- SQL Server

---

# 8. NoSQL Database

NoSQL stores data in flexible formats like documents.

Example:

```json
{
  "name": "Rahim",
  "age": 22,
  "skills": ["Node.js", "React"]
}
```

Everything is stored inside one document.

### Examples

- MongoDB
- Redis
- Cassandra
- DynamoDB

---

# 9. SQL vs NoSQL

| SQL                   | NoSQL                                            |
| --------------------- | ------------------------------------------------ |
| Stores data in tables | Stores data as documents, key-value, graph, etc. |
| Fixed Schema          | Flexible Schema                                  |
| Supports JOIN         | Usually avoids JOIN                              |
| Structured data       | Flexible data                                    |
| Strong ACID support   | High scalability                                 |

## Which Should You Learn?

Recommended order:

1. PostgreSQL (SQL)
2. MongoDB (NoSQL)

Learning SQL first makes NoSQL much easier.

---

# 10. Database Architecture

```
Client

↓

Frontend

↓

Backend API

↓

Database

↓

Response
```

### Example

```
User logs in

↓

Frontend sends request

↓

Backend verifies user

↓

Database returns user data

↓

Backend sends response

↓

Frontend displays result
```

---

# 11. Client → Server → Database Flow

```
User clicks Login

↓

Frontend

↓

Backend

↓

SQL Query

↓

Database

↓

Result

↓

Backend

↓

Frontend
```

This is how almost every modern web application works.

---

# 12. Real-world Examples

## Social Media

- Users
- Posts
- Comments
- Followers

---

## E-commerce

- Customers
- Products
- Orders
- Payments

---

## Hospital

- Doctors
- Patients
- Appointments

---

## University

- Students
- Teachers
- Courses

---

# Key Takeaways

- A database stores application data permanently.
- A DBMS is software used to manage databases.
- Tables contain rows and columns.
- Relational databases store data in related tables.
- NoSQL databases store data in flexible structures.
- Most backend applications use PostgreSQL or MySQL.
- Every web application follows:

```
Client

↓

Frontend

↓

Backend

↓

Database
```

---

# Quick Revision

### What is a Database?

An organized collection of data.

---

### What is a DBMS?

Software used to create and manage databases.

---

### Difference between Data and Information?

- Data = Raw facts
- Information = Processed data

---

### What is a Table?

A collection of rows and columns.

---

### What is a Row?

A single record.

---

### What is a Column?

A single attribute.

---

### SQL Database Examples

- PostgreSQL
- MySQL
- SQLite

---

### NoSQL Database Examples

- MongoDB
- Redis
- Cassandra

---

### Recommended Learning Path

```
Database Fundamentals

↓

SQL

↓

PostgreSQL

↓

Advanced SQL

↓

Database Design

↓

Prisma ORM

↓

Backend Development
```
