# 📚 Phase 8 - SQL Constraints

> **What is a Constraint?**
>
> A **Constraint** is a rule applied to a table column that controls what data can be stored. Constraints help maintain **data integrity**, **accuracy**, and **consistency**.

---

# Sample Table

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    age INT,
    country VARCHAR(50)
);
```

---

# Types of Constraints

- PRIMARY KEY
- FOREIGN KEY
- UNIQUE
- CHECK
- DEFAULT
- NOT NULL

---

# 1. PRIMARY KEY

## What is it?

A **PRIMARY KEY** uniquely identifies each row in a table.

Rules

- Cannot be NULL
- Cannot have duplicate values
- Only one Primary Key per table

### Example

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100)
);
```

### Output

| id  | name  |
| --- | ----- |
| 1   | Rahim |
| 2   | Karim |

❌ Invalid

```sql
INSERT INTO users(id,name)
VALUES(1,'Hasan');
```

Output

```
ERROR:
Duplicate Primary Key.
```

### Where to Use

- User ID
- Product ID
- Order ID
- Student ID

---

# 2. FOREIGN KEY

## What is it?

A **FOREIGN KEY** connects two tables and ensures valid relationships.

### Example

```sql
CREATE TABLE orders (

id SERIAL PRIMARY KEY,

user_id INT REFERENCES users(id),

amount DECIMAL

);
```

### users

| id  | name  |
| --- | ----- |
| 1   | Rahim |
| 2   | Karim |

### orders

| id  | user_id | amount |
| --- | ------- | ------ |
| 101 | 1       | 500    |
| 102 | 2       | 700    |

### Invalid Example

```sql
INSERT INTO orders(user_id,amount)
VALUES(10,500);
```

Output

```
ERROR

Foreign key constraint failed.
```

Because User 10 doesn't exist.

### Where to Use

- Orders → Users
- Posts → Users
- Comments → Posts
- Products → Categories

---

# 3. UNIQUE

## What is it?

Ensures duplicate values are not allowed.

Unlike PRIMARY KEY,

- Multiple UNIQUE constraints are allowed.
- NULL is generally allowed (PostgreSQL allows multiple NULLs).

### Example

```sql
CREATE TABLE users (

id SERIAL PRIMARY KEY,

email VARCHAR(100) UNIQUE

);
```

### Valid

| email           |
| --------------- |
| rahim@gmail.com |
| karim@gmail.com |

### Invalid

```sql
INSERT INTO users(email)

VALUES('rahim@gmail.com');
```

Output

```
ERROR

Duplicate value violates UNIQUE constraint.
```

### Where to Use

- Email
- Username
- Passport Number
- National ID

---

# 4. CHECK

## What is it?

Allows only values that satisfy a condition.

### Example

Age cannot be below 18.

```sql
CREATE TABLE users (

age INT CHECK(age>=18)

);
```

### Valid

```sql
INSERT INTO users(age)

VALUES(22);
```

### Invalid

```sql
INSERT INTO users(age)

VALUES(15);
```

Output

```
ERROR

CHECK constraint violated.
```

### Real-world Uses

- Age >=18
- Salary >0
- Price >0
- Rating between 1 and 5

---

# 5. DEFAULT

## What is it?

Automatically inserts a default value if no value is provided.

### Example

```sql
CREATE TABLE users (

country VARCHAR(50)

DEFAULT 'Bangladesh'

);
```

### Insert

```sql
INSERT INTO users DEFAULT VALUES;
```

### Output

| country    |
| ---------- |
| Bangladesh |

Another Example

```sql
status VARCHAR(20)

DEFAULT 'Pending'
```

### Where to Use

- Status
- Country
- Role
- Created Date
- Boolean Flags

---

# 6. NOT NULL

## What is it?

Prevents NULL values.

Every row must contain a value.

### Example

```sql
CREATE TABLE users (

name VARCHAR(100)

NOT NULL

);
```

### Valid

```sql
INSERT INTO users(name)

VALUES('Rahim');
```

### Invalid

```sql
INSERT INTO users(name)

VALUES(NULL);
```

Output

```
ERROR

NULL value violates NOT NULL constraint.
```

### Where to Use

Required fields

- Name
- Password
- Email
- Product Name
- Order Date

---

# Constraint Comparison

| Constraint  | Purpose                  |
| ----------- | ------------------------ |
| PRIMARY KEY | Unique identifier        |
| FOREIGN KEY | Connects two tables      |
| UNIQUE      | Prevent duplicate values |
| CHECK       | Allows only valid values |
| DEFAULT     | Inserts a default value  |
| NOT NULL    | Prevents NULL values     |

---

# Real-World Example

```sql
CREATE TABLE users (

id SERIAL PRIMARY KEY,

name VARCHAR(100) NOT NULL,

email VARCHAR(100) UNIQUE NOT NULL,

age INT CHECK(age>=18),

country VARCHAR(50) DEFAULT 'Bangladesh'

);
```

Now,

✔ id is always unique

✔ name cannot be NULL

✔ email must be unique

✔ age must be at least 18

✔ country becomes "Bangladesh" if omitted

---

# Where Are These Used?

| Constraint  | Common Uses               |
| ----------- | ------------------------- |
| PRIMARY KEY | Users, Orders, Products   |
| FOREIGN KEY | Orders, Comments, Reviews |
| UNIQUE      | Email, Username, Phone    |
| CHECK       | Age, Price, Rating        |
| DEFAULT     | Status, Country, Role     |
| NOT NULL    | Name, Password, Email     |

---

# Quick Revision

| Constraint  | What It Does                                   |
| ----------- | ---------------------------------------------- |
| PRIMARY KEY | Uniquely identifies each row                   |
| FOREIGN KEY | Maintains relationships between tables         |
| UNIQUE      | Prevents duplicate values                      |
| CHECK       | Restricts values based on a condition          |
| DEFAULT     | Automatically sets a value if none is provided |
| NOT NULL    | Requires a value; NULL is not allowed          |

> 💡 **Senior Developer Tip:**  
> In production databases, it's common to combine multiple constraints. For example, an `email` column is often defined as `UNIQUE NOT NULL`, and a `users` table typically uses `PRIMARY KEY`, `CHECK`, and `DEFAULT` together to enforce reliable, consistent data.
