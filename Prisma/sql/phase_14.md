# 📚 Phase 14 - PostgreSQL Security & Access Control

> Database security is the practice of protecting data from unauthorized access, modification, or deletion. PostgreSQL provides a powerful permission system using **Users**, **Roles**, and **Privileges**.

---

# Security Overview

```
Application

↓

Database User

↓

Role

↓

Permissions

↓

Database Objects
```

---

# 1. Users

## What is a User?

A **User** is an account that can connect to a PostgreSQL database.

A user can

- Login
- Run queries
- Create tables
- Insert data
- Manage databases (if permitted)

### Create a User

```sql
CREATE USER rahim
WITH PASSWORD 'password123';
```

### Delete a User

```sql
DROP USER rahim;
```

### Where to Use

- Developers
- Applications
- Database Administrators (DBAs)

---

# 2. Roles

## What is a Role?

A **Role** is a collection of permissions.

In PostgreSQL, **Users and Roles are both roles** internally. A role can optionally have the `LOGIN` privilege, allowing it to act as a user.

Instead of assigning permissions to every user individually,

assign them to a role.

### Create a Role

```sql
CREATE ROLE manager;
```

Give login permission

```sql
CREATE ROLE app_user
LOGIN
PASSWORD 'secret123';
```

Assign a Role

```sql
GRANT manager TO rahim;
```

### Real-world Roles

- Admin
- Manager
- Employee
- Read Only User
- Application User

---

# 3. Permissions

## What are Permissions?

Permissions determine **what a user or role is allowed to do**.

Common Permissions

- SELECT
- INSERT
- UPDATE
- DELETE
- CREATE
- ALTER
- DROP
- EXECUTE

Example

```
User

↓

Can Read

✔

Can Update

✔

Can Delete

❌
```

---

# 4. GRANT

## What is GRANT?

`GRANT` gives permissions to a user or role.

### Example

Allow reading

```sql
GRANT SELECT

ON users

TO rahim;
```

Allow multiple permissions

```sql
GRANT

SELECT,

INSERT,

UPDATE

ON users

TO manager;
```

### Real-world Use

- Read-only dashboards
- Application users
- Reporting systems

---

# 5. REVOKE

## What is REVOKE?

`REVOKE` removes previously granted permissions.

### Example

```sql
REVOKE UPDATE

ON users

FROM rahim;
```

Now Rahim can no longer update the `users` table.

### Real-world Use

- Employee leaves the company
- Reduce privileges
- Improve security

---

# GRANT vs REVOKE

| GRANT             | REVOKE              |
| ----------------- | ------------------- |
| Gives permissions | Removes permissions |
| Increases access  | Restricts access    |

---

# 6. SQL Injection

## What is SQL Injection?

SQL Injection is a security attack where an attacker inserts malicious SQL into user input.

### Unsafe Example

Application Code

```sql
SELECT *

FROM users

WHERE email='user_input'

AND password='password_input';
```

If the attacker enters

```
' OR 1=1 --
```

The query becomes

```sql
SELECT *

FROM users

WHERE email=''

OR 1=1 --'
```

Result

Every user is returned.

Authentication is bypassed.

### Risks

- Data Theft
- Account Hijacking
- Data Deletion
- Database Damage

---

# How to Prevent SQL Injection

✅ Prepared Statements

✅ Parameterized Queries

✅ Input Validation

✅ Least Privilege

❌ Never concatenate user input into SQL strings.

---

# 7. Prepared Statements

## What is a Prepared Statement?

A Prepared Statement separates **SQL code** from **user input**.

The database treats input as data,

not executable SQL.

### PostgreSQL Example

Prepare

```sql
PREPARE get_user(text) AS

SELECT *

FROM users

WHERE email=$1;
```

Execute

```sql
EXECUTE get_user('rahim@gmail.com');
```

### Application Example (Node.js)

```javascript
const query = `
SELECT *
FROM users
WHERE email = $1
`;

await pool.query(query, [email]);
```

The value of `email` is sent separately from the SQL query, preventing SQL injection.

### Benefits

- Prevents SQL Injection
- Better Performance (for repeated queries)
- Cleaner Code

---

# Security Best Practices

✅ Use Roles instead of assigning permissions to each user.

✅ Give only the permissions that are required.

✅ Use Prepared Statements for all user input.

✅ Store passwords securely (e.g., hashed with bcrypt in the application).

✅ Regularly review and remove unused users and roles.

---

# Real-World Example

## Online Shopping Application

### Admin

Permissions

- SELECT
- INSERT
- UPDATE
- DELETE

---

### Customer

Permissions

- SELECT Products
- Create Orders

Cannot

- Delete Products
- Update Other Users

---

### Application User

Uses Prepared Statements for

- Login
- Search
- Registration
- Order Placement

This protects the database from SQL Injection attacks.

---

# Quick Revision

| Topic              | Purpose                                          |
| ------------------ | ------------------------------------------------ |
| User               | Account that can connect to the database         |
| Role               | Collection of permissions                        |
| Permissions        | Define allowed actions                           |
| GRANT              | Give permissions                                 |
| REVOKE             | Remove permissions                               |
| SQL Injection      | Attack using malicious SQL input                 |
| Prepared Statement | Prevent SQL Injection by separating SQL and data |

---

# Interview Questions

### Basic

1. What is a User in PostgreSQL?
2. What is a Role?
3. Difference between a User and a Role?
4. What does GRANT do?
5. What does REVOKE do?

### Intermediate

6. What is SQL Injection?
7. How can SQL Injection be prevented?
8. What is a Prepared Statement?
9. Why should applications use parameterized queries?

### Advanced

10. Explain the principle of least privilege.
11. Why are Roles preferred over assigning permissions directly to users?
12. How do Prepared Statements improve both security and performance?
13. Describe how you would secure a production PostgreSQL database.

> 💡 **Senior Developer Tip:**  
> In modern applications using **Node.js, Prisma, Django, Laravel, or Spring Boot**, you rarely write raw SQL with user input. Instead, use **parameterized queries or your ORM's query builder**, assign **minimum required permissions** to application accounts, and organize access through **roles** rather than granting privileges directly to every user.
