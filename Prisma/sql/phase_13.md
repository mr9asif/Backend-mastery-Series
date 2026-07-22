# 📚 Phase 13 - PostgreSQL Architecture & Advanced Data Types

> PostgreSQL is a powerful, open-source Relational Database Management System (RDBMS) known for its reliability, extensibility, and advanced features.

---

# PostgreSQL Architecture

## What is PostgreSQL Architecture?

PostgreSQL Architecture describes **how PostgreSQL stores, manages, and processes data**.

Basic Architecture

```
Application

↓

PostgreSQL Server

↓

Parser

↓

Query Planner

↓

Executor

↓

Storage Manager

↓

Database Files
```

### Main Components

- Client
- PostgreSQL Server
- Query Parser
- Query Planner
- Query Executor
- Storage Manager
- Database Files

### Real-world Flow

```
React

↓

Node.js

↓

Prisma

↓

PostgreSQL

↓

Disk
```

---

# Schemas

## What is a Schema?

A **Schema** is a logical container that groups database objects.

Objects include

- Tables
- Views
- Functions
- Sequences

Think of a schema like a folder inside a database.

### Example

```sql
CREATE SCHEMA ecommerce;
```

Create a table inside it.

```sql
CREATE TABLE ecommerce.users (

id SERIAL PRIMARY KEY,

name TEXT

);
```

### Access

```sql
SELECT *

FROM ecommerce.users;
```

### Where to Use

- Multi-tenant applications
- Large projects
- Separate modules
- Better organization

---

# Sequences

## What is a Sequence?

A Sequence generates unique numbers automatically.

### Example

```sql
CREATE SEQUENCE order_seq;
```

Get next value

```sql
SELECT nextval('order_seq');
```

Output

```
1

2

3

4
```

### Where to Use

- Order Numbers
- Invoice Numbers
- Ticket Numbers

---

# SERIAL

## What is SERIAL?

`SERIAL` is a shortcut that creates

- Integer column
- Sequence
- Default next value

Automatically.

### Example

```sql
CREATE TABLE users (

id SERIAL PRIMARY KEY,

name TEXT

);
```

Insert

```sql
INSERT INTO users(name)

VALUES('Rahim');
```

Output

| id  | name  |
| --- | ----- |
| 1   | Rahim |

### Benefit

Automatic incrementing IDs.

---

# IDENTITY

## What is IDENTITY?

`IDENTITY` is the SQL-standard replacement for `SERIAL`.

### Example

```sql
CREATE TABLE users (

id INT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,

name TEXT

);
```

### Advantages over SERIAL

- SQL Standard
- Better control
- Preferred in modern PostgreSQL

### Where to Use

New PostgreSQL projects.

---

# UUID

## What is UUID?

UUID (Universally Unique Identifier) is a 128-bit unique identifier.

Example

```
550e8400-e29b-41d4-a716-446655440000
```

### Example

```sql
CREATE TABLE users (

id UUID PRIMARY KEY

);
```

Generate UUID

```sql
SELECT gen_random_uuid();
```

### Advantages

- Globally unique
- Hard to guess
- Good for distributed systems

### Real-world Use

- APIs
- Microservices
- Public IDs
- Authentication Systems

---

# Arrays

## What are Arrays?

Arrays allow multiple values in a single column.

### Example

```sql
CREATE TABLE users (

skills TEXT[]

);
```

Insert

```sql
INSERT INTO users(skills)

VALUES

(ARRAY['JavaScript','TypeScript','Node.js']);
```

Output

```
{JavaScript,TypeScript,Node.js}
```

### Where to Use

- Skills
- Tags
- Categories
- Phone Numbers (small fixed lists)

---

# JSON

## What is JSON?

JSON stores structured data as plain text.

### Example

```sql
CREATE TABLE products (

details JSON

);
```

Insert

```sql
INSERT INTO products(details)

VALUES(

'{

"brand":"Apple",

"color":"Black"

}'

);
```

### Advantages

- Flexible
- Easy to read
- Good for changing data

---

# JSONB

## What is JSONB?

`JSONB` stores JSON in a binary format.

It supports indexing and is much faster for searching.

### Example

```sql
CREATE TABLE products (

details JSONB

);
```

Query

```sql
SELECT *

FROM products

WHERE details->>'brand'='Apple';
```

### JSON vs JSONB

| JSON                 | JSONB                              |
| -------------------- | ---------------------------------- |
| Stores text          | Stores binary format               |
| Slower search        | Faster search                      |
| No indexing          | Supports indexing                  |
| Preserves formatting | Reorders internally for efficiency |

### Real-world Use

- Product Specifications
- API Responses
- User Preferences
- Settings

---

# ENUM

## What is ENUM?

ENUM allows only predefined values.

### Example

```sql
CREATE TYPE order_status AS ENUM(

'Pending',

'Processing',

'Completed',

'Cancelled'

);
```

Use

```sql
CREATE TABLE orders (

status order_status

);
```

### Valid

```
Pending
```

### Invalid

```
Delivered
```

Output

```
ERROR
```

### Where to Use

- Order Status
- User Roles
- Payment Status
- Ticket Status

---

# Extensions

## What are Extensions?

Extensions add extra features to PostgreSQL.

### View Installed Extensions

```sql
SELECT *

FROM pg_extension;
```

### Install an Extension

```sql
CREATE EXTENSION extension_name;
```

---

## Common Extensions

### uuid-ossp

Generate UUIDs.

```sql
CREATE EXTENSION "uuid-ossp";
```

Generate UUID

```sql
SELECT uuid_generate_v4();
```

---

### pgcrypto

Provides cryptographic functions.

```sql
CREATE EXTENSION pgcrypto;
```

Generate UUID

```sql
SELECT gen_random_uuid();
```

---

### pg_trgm

Improves text searching using similarity.

Useful for

- Search bars
- Autocomplete
- Fuzzy matching

---

### PostGIS

Adds geographic data support.

Used in

- Maps
- GPS
- Location-based services

---

# SERIAL vs IDENTITY vs UUID

| Feature               | SERIAL | IDENTITY | UUID      |
| --------------------- | ------ | -------- | --------- |
| Auto Increment        | ✅     | ✅       | ❌        |
| SQL Standard          | ❌     | ✅       | ✅        |
| Globally Unique       | ❌     | ❌       | ✅        |
| Best for Public APIs  | ❌     | ❌       | ✅        |
| Best for Internal IDs | ✅     | ✅       | Sometimes |

---

# JSON vs JSONB

| Feature            | JSON   | JSONB         |
| ------------------ | ------ | ------------- |
| Storage            | Text   | Binary        |
| Read Speed         | Normal | Faster        |
| Index Support      | ❌     | ✅            |
| Search Performance | Slower | Faster        |
| Preferred          | Rarely | ✅ Most cases |

---

# Real-World Example

## E-commerce Database

```sql
CREATE TABLE products (

id UUID PRIMARY KEY,

name TEXT,

status order_status,

tags TEXT[],

details JSONB

);
```

Benefits

- UUID for globally unique IDs
- ENUM for valid statuses
- Array for tags
- JSONB for flexible product specifications

---

# Quick Revision

| Topic                   | Purpose                                  |
| ----------------------- | ---------------------------------------- |
| PostgreSQL Architecture | Shows how PostgreSQL processes queries   |
| Schema                  | Logical container for database objects   |
| Sequence                | Generates unique numbers                 |
| SERIAL                  | Auto-increment shortcut using a sequence |
| IDENTITY                | SQL-standard auto-increment column       |
| UUID                    | Globally unique identifier               |
| Arrays                  | Store multiple values in one column      |
| JSON                    | Store structured text data               |
| JSONB                   | Binary JSON with indexing support        |
| ENUM                    | Restrict values to a predefined list     |
| Extensions              | Add extra PostgreSQL features            |

---

# Interview Questions

### Basic

1. What is a Schema in PostgreSQL?
2. What is a Sequence?
3. Difference between SERIAL and IDENTITY?
4. What is a UUID?
5. Difference between JSON and JSONB?

### Intermediate

6. When should you use UUID instead of SERIAL?
7. What are PostgreSQL Extensions?
8. What is an ENUM and where is it useful?
9. When would you use Arrays?

### Advanced

10. Explain the basic PostgreSQL Architecture.
11. Why is JSONB preferred over JSON in most applications?
12. What are the advantages of Schemas in large projects?
13. Name some commonly used PostgreSQL Extensions and their use cases.

> 💡 **Senior Developer Tip:**  
> For modern PostgreSQL applications, prefer **IDENTITY** over `SERIAL` for new schemas, use **UUID** for public-facing identifiers or distributed systems, choose **JSONB** instead of `JSON` for searchable semi-structured data, and leverage **Schemas** to organize large applications into logical modules. Extensions like **pgcrypto**, **pg_trgm**, and **PostGIS** unlock many of PostgreSQL's most powerful capabilities.
