# 📚 Phase 7 - SQL JOIN (Quick Mastery)

> **What is JOIN?**
>
> A **JOIN** is used to combine data from **two or more tables** based on a related column (usually Primary Key ↔ Foreign Key).
>
> Without JOIN, relational databases would be useless because related data is stored in different tables.

---

# Sample Tables

## users

| id  | name  |
| --- | ----- |
| 1   | Rahim |
| 2   | Karim |
| 3   | Hasan |

## orders

| id  | user_id | amount |
| --- | ------- | ------ |
| 101 | 1       | 500    |
| 102 | 1       | 700    |
| 103 | 2       | 300    |
| 104 | 4       | 900    |

---

# Types of JOIN

1. INNER JOIN
2. LEFT JOIN
3. RIGHT JOIN
4. FULL OUTER JOIN
5. CROSS JOIN
6. SELF JOIN

---

# 1. INNER JOIN ⭐ (Most Used)

## What is it?

Returns **only matching rows** from both tables.

Think of it as:

```
Common Data Only
```

### Syntax

```sql
SELECT users.name, orders.amount
FROM users
INNER JOIN orders
ON users.id = orders.user_id;
```

### Output

| name  | amount |
| ----- | ------ |
| Rahim | 500    |
| Rahim | 700    |
| Karim | 300    |

Hasan is not shown because he has no order.

Order 104 is not shown because User 4 doesn't exist.

### Where to Use

- User Orders
- Student Courses
- Product Reviews
- Blog Posts
- Comments

---

# 2. LEFT JOIN ⭐⭐

## What is it?

Returns **all rows from the LEFT table** and matching rows from the RIGHT table.

If no match exists, NULL is returned.

### Syntax

```sql
SELECT users.name, orders.amount
FROM users
LEFT JOIN orders
ON users.id = orders.user_id;
```

### Output

| name  | amount |
| ----- | ------ |
| Rahim | 500    |
| Rahim | 700    |
| Karim | 300    |
| Hasan | NULL   |

### Where to Use

Show all users even if they never ordered.

Other examples

- All Students + Marks
- All Employees + Salary
- All Products + Reviews

---

# 3. RIGHT JOIN

## What is it?

Returns **all rows from the RIGHT table**.

If the LEFT table has no match, NULL is returned.

### Syntax

```sql
SELECT users.name, orders.amount
FROM users
RIGHT JOIN orders
ON users.id = orders.user_id;
```

### Output

| name  | amount |
| ----- | ------ |
| Rahim | 500    |
| Rahim | 700    |
| Karim | 300    |
| NULL  | 900    |

Order 104 exists but User 4 doesn't.

### Where to Use

Rarely used.

Usually LEFT JOIN is preferred.

---

# 4. FULL OUTER JOIN

## What is it?

Returns **everything**.

- Matching rows
- Left unmatched rows
- Right unmatched rows

### Syntax

```sql
SELECT users.name, orders.amount
FROM users
FULL OUTER JOIN orders
ON users.id = orders.user_id;
```

### Output

| name  | amount |
| ----- | ------ |
| Rahim | 500    |
| Rahim | 700    |
| Karim | 300    |
| Hasan | NULL   |
| NULL  | 900    |

### Where to Use

- Data Comparison
- Reporting
- Data Migration
- Data Auditing

---

# 5. CROSS JOIN

## What is it?

Returns **every possible combination**.

Formula

```
Rows1 × Rows2
```

3 Users

×

4 Orders

=

12 Rows

### Syntax

```sql
SELECT *
FROM users
CROSS JOIN orders;
```

### Output

```
Rahim + Order101

Rahim + Order102

Rahim + Order103

...

Karim + Order101

...

Hasan + Order104
```

### Where to Use

- Generate Test Data
- Product Variations
- Calendar Tables

---

# 6. SELF JOIN

## What is it?

Joining a table with itself.

### Example

employees

| id  | name  | manager_id |
| --- | ----- | ---------- |
| 1   | Rahim | NULL       |
| 2   | Karim | 1          |
| 3   | Hasan | 1          |

### Query

```sql
SELECT

e.name AS employee,

m.name AS manager

FROM employees e

LEFT JOIN employees m

ON e.manager_id = m.id;
```

### Output

| Employee | Manager |
| -------- | ------- |
| Rahim    | NULL    |
| Karim    | Rahim   |
| Hasan    | Rahim   |

### Where to Use

- Employee → Manager
- Category → Parent Category
- Friend Relationship

---

# Advanced JOIN

Advanced JOIN means using JOIN with other SQL features.

Examples

- JOIN + WHERE
- JOIN + GROUP BY
- JOIN + Aggregate Functions
- Multiple JOINs

Used in almost every backend project.

---

# Multiple Table JOIN

Joining more than two tables.

Example

```
Users

↓

Orders

↓

Products
```

### Query

```sql
SELECT

users.name,

products.name

FROM users

JOIN orders

ON users.id=orders.user_id

JOIN products

ON orders.product_id=products.id;
```

### Where to Use

- E-commerce
- School Management
- Hospital
- Banking

---

# JOIN + GROUP BY

Used when you need grouped data after joining tables.

### Example

Find total orders for each user.

```sql
SELECT

users.name,

COUNT(orders.id)

FROM users

JOIN orders

ON users.id=orders.user_id

GROUP BY users.name;
```

### Output

| name  | orders |
| ----- | ------ |
| Rahim | 2      |
| Karim | 1      |

### Where to Use

- User Statistics
- Sales Reports
- Dashboard

---

# JOIN + Aggregate Functions

Aggregate Functions

- COUNT()
- SUM()
- AVG()
- MAX()
- MIN()

### Example

Total money spent by each user.

```sql
SELECT

users.name,

SUM(orders.amount)

FROM users

JOIN orders

ON users.id=orders.user_id

GROUP BY users.name;
```

### Output

| name  | total |
| ----- | ----- |
| Rahim | 1200  |
| Karim | 300   |

### Where to Use

- Revenue Reports
- Customer Spending
- Business Analytics

---

# JOIN Optimization

JOIN itself isn't slow.

Poor database design makes it slow.

### Tips

✅ Join using indexed columns.

Usually

```text
Primary Key

↓

Foreign Key
```

---

Only select needed columns.

❌

```sql
SELECT *
```

✅

```sql
SELECT users.name, orders.amount
```

---

Use INNER JOIN when possible.

It is generally faster than OUTER JOINs because it returns only matching rows.

---

Avoid unnecessary JOINs.

Join only the tables you need.

---

# Which JOIN Should I Use?

| JOIN            | Returns                    | Most Common Use             |
| --------------- | -------------------------- | --------------------------- |
| INNER JOIN      | Matching rows only         | ⭐⭐⭐⭐⭐ Everyday queries |
| LEFT JOIN       | All left + matching right  | ⭐⭐⭐⭐ Dashboards, APIs   |
| RIGHT JOIN      | All right + matching left  | ⭐ Rare                     |
| FULL OUTER JOIN | Everything                 | Reporting                   |
| CROSS JOIN      | Every possible combination | Test data                   |
| SELF JOIN       | Same table                 | Manager, Category Tree      |

---

# Real-World Examples

| Project    | JOIN Used                           |
| ---------- | ----------------------------------- |
| E-commerce | Users + Orders + Products           |
| Facebook   | Users + Posts + Comments            |
| YouTube    | Users + Videos + Likes              |
| Hospital   | Doctors + Patients + Appointments   |
| School     | Students + Courses + Enrollments    |
| Banking    | Customers + Accounts + Transactions |

---

# Quick Revision

| Topic             | Purpose                                          |
| ----------------- | ------------------------------------------------ |
| INNER JOIN        | Return only matching records                     |
| LEFT JOIN         | Keep all rows from the left table                |
| RIGHT JOIN        | Keep all rows from the right table               |
| FULL OUTER JOIN   | Keep all rows from both tables                   |
| CROSS JOIN        | Every possible combination                       |
| SELF JOIN         | Join a table with itself                         |
| Multiple JOIN     | Join more than two tables                        |
| JOIN + GROUP BY   | Group joined data                                |
| JOIN + Aggregate  | Calculate totals, averages, counts after joining |
| JOIN Optimization | Write faster and more efficient JOIN queries     |

> 💡 **Senior Developer Tip:**  
> In real-world backend development (Node.js, Prisma, Django, Laravel, Spring Boot), **INNER JOIN** and **LEFT JOIN** are used most frequently (about 90% of cases). `RIGHT JOIN` and `FULL OUTER JOIN` are relatively rare, while `SELF JOIN` is useful for hierarchical data such as managers, categories, or organizational structures.
