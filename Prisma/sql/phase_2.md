# 📚 DDL (Data Definition Language)

> Learn how to create and manage databases and tables.

---

# 📖 Topics Covered

- Creating Databases
- Creating Tables
- Altering Tables
- Dropping Tables
- Truncating Tables
- Renaming Tables

---

# What is DDL?

**DDL (Data Definition Language)** is used to create and modify the structure of a database.

DDL commands work on the **database structure**, not the data.

Common DDL Commands:

- CREATE DATABASE
- CREATE TABLE
- ALTER TABLE
- DROP TABLE
- TRUNCATE TABLE
- RENAME TABLE

---

# Project Scenario

Suppose we are building an **E-Commerce Website**.

We need:

- A Database
- Users Table
- Products Table

Let's build them step by step.

---

# 1. Creating Database

## Syntax

```sql
CREATE DATABASE ecommerce_db;
```

## Example

```sql
CREATE DATABASE ecommerce_db;
```

## Output

Database Created Successfully.

## Before

```text
PostgreSQL

├── postgres
├── template0
└── template1
```

## After

```text
PostgreSQL

├── postgres
├── template0
├── template1
└── ecommerce_db
```

## Explanation

A new database named **ecommerce_db** is created.

---

# 2. Creating Tables

A table stores related data in rows and columns.

## Syntax

```sql
CREATE TABLE table_name (
    column_name data_type,
    ...
);
```

## Example

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(255) UNIQUE,
    age INTEGER,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Column Explanation

| Column     | Purpose               |
| ---------- | --------------------- |
| id         | Unique User ID        |
| name       | User Name             |
| email      | User Email            |
| age        | User Age              |
| created_at | Account Creation Time |

---

## Table Structure

| id  | name | email | age | created_at |
| --- | ---- | ----- | --- | ---------- |

Currently, the table is empty.

---

## Verify

```sql
SELECT * FROM users;
```

## Output

```text
 id | name | email | age | created_at
----+------+-------+-----+------------
(0 rows)
```

---

# 3. Altering Tables

ALTER TABLE modifies an existing table.

---

## Example 1 - Add a New Column

Suppose the client says,

> "We also need users' phone numbers."

SQL:

```sql
ALTER TABLE users
ADD COLUMN phone VARCHAR(20);
```

### Before

| id  | name | email | age |
| --- | ---- | ----- | --- |

### After

| id  | name | email | age | phone |
| --- | ---- | ----- | --- | ----- |

---

## Example 2 - Rename a Column

```sql
ALTER TABLE users
RENAME COLUMN phone TO mobile;
```

### Before

| id  | name | mobile |
| --- | ---- | ------ |

### After

| id  | name | mobile |
| --- | ---- | ------ |

The column name changes from **phone** to **mobile**.

---

## Example 3 - Change Data Type

Suppose 20 characters are not enough.

```sql
ALTER TABLE users
ALTER COLUMN mobile TYPE VARCHAR(30);
```

Now the column can store up to 30 characters.

---

# 4. Dropping Tables

DROP TABLE permanently deletes a table.

## Syntax

```sql
DROP TABLE table_name;
```

## Example

```sql
DROP TABLE users;
```

## Before

```text
Database

├── users
├── products
└── orders
```

## After

```text
Database

├── products
└── orders
```

The **users** table is permanently deleted.

⚠️ Warning:

All data inside the table is also permanently deleted.

---

# 5. Truncating Tables

TRUNCATE removes **all rows** but keeps the table.

Suppose the table contains:

| id  | name  | age |
| --- | ----- | --- |
| 1   | Rahim | 22  |
| 2   | Karim | 25  |
| 3   | Hasan | 19  |

SQL

```sql
TRUNCATE TABLE users;
```

## Output

```text
TRUNCATE TABLE
```

## Table After

| id  | name | age |
| --- | ---- | --- |

The table still exists.

Only the rows are deleted.

---

## Difference

DROP TABLE

```text
Table Deleted

❌ Structure Deleted

❌ Data Deleted
```

TRUNCATE TABLE

```text
Table Exists

✅ Structure Exists

❌ Data Deleted
```

---

# 6. Renaming Tables

Rename an existing table.

## Syntax

```sql
ALTER TABLE old_name
RENAME TO new_name;
```

## Example

```sql
ALTER TABLE users
RENAME TO customers;
```

## Before

```text
users
```

## After

```text
customers
```

Only the table name changes.

All data remains.

---

# Complete Real-world Example

Let's build a small Blog Database.

## Step 1

```sql
CREATE DATABASE blog_db;
```

---

## Step 2

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(255)
);
```

---

## Step 3

```sql
CREATE TABLE posts (
    id SERIAL PRIMARY KEY,
    title VARCHAR(255),
    content TEXT,
    author_id INTEGER
);
```

---

## Database Structure

```text
blog_db

├── users
└── posts
```

---

## Later in Prisma

```prisma
model User {
  id    Int    @id @default(autoincrement())
  name  String
  email String
}

model Post {
  id        Int    @id @default(autoincrement())
  title     String
  content   String
  author_id Int
}
```

---

# Best Practices

- Use meaningful table names.
- Always create a PRIMARY KEY.
- Choose appropriate data types.
- Use NOT NULL where required.
- Avoid DROP TABLE in production.
- Use TRUNCATE only when you want to delete all rows.

---

# Interview Questions

## Beginner

1. What is DDL?
2. What is CREATE DATABASE?
3. What is CREATE TABLE?
4. What is ALTER TABLE?
5. What is DROP TABLE?
6. What is TRUNCATE TABLE?
7. What is the difference between DROP and TRUNCATE?

---

## Intermediate

1. Why should every table have a PRIMARY KEY?
2. Why is VARCHAR used instead of TEXT sometimes?
3. What happens if you DROP a table?
4. When should you use TRUNCATE instead of DELETE?

---

# Practice

## Task 1

Create a database named `school_db`.

---

## Task 2

Create a table named `students`.

Columns:

- id
- name
- email
- age

---

## Task 3

Add a `phone` column.

---

## Task 4

Rename `phone` to `mobile`.

---

## Task 5

Change the data type of `mobile` to `VARCHAR(30)`.

---

## Task 6

Remove all rows without deleting the table.

---

## Task 7

Delete the table permanently.

---

# Summary

- CREATE DATABASE → Creates a new database.
- CREATE TABLE → Creates a new table.
- ALTER TABLE → Modifies an existing table.
- DROP TABLE → Deletes the table permanently.
- TRUNCATE TABLE → Deletes all rows but keeps the table.
- RENAME TABLE → Changes the table name.
