# 📚 Phase 11 - Advanced SQL Concepts

> These are advanced SQL features used in real-world applications for reporting, automation, reusable logic, and complex data analysis.

---

# 1. Views

## What is a View?

A **View** is a virtual table created from one or more SQL queries.

It doesn't store data itself. It simply shows data from the original table.

### Example

```sql
CREATE VIEW employee_info AS

SELECT name, salary
FROM employees;
```

Use the View

```sql
SELECT *
FROM employee_info;
```

### Output

| name  | salary |
| ----- | ------ |
| Rahim | 50000  |
| Karim | 40000  |

### Where to Use

- Reports
- Dashboards
- Hide sensitive columns
- Simplify complex queries

---

# 2. Materialized Views

## What is it?

A Materialized View **stores the query result physically**.

Unlike a normal View, it is much faster for large reports.

### Example

```sql
CREATE MATERIALIZED VIEW sales_report AS

SELECT category,
SUM(price)
FROM products
GROUP BY category;
```

Refresh Data

```sql
REFRESH MATERIALIZED VIEW sales_report;
```

### Where to Use

- Analytics
- Business Reports
- Dashboards
- Large Datasets

---

# 3. Stored Procedures (Basic)

## What is it?

A Stored Procedure is a group of SQL statements stored inside the database.

It can be executed whenever needed.

### Example (PostgreSQL)

```sql
CREATE PROCEDURE hello()

LANGUAGE SQL

AS $$

SELECT 'Hello World';

$$;
```

Run

```sql
CALL hello();
```

### Output

```
Hello World
```

### Where to Use

- Monthly Reports
- Salary Processing
- Data Import
- Batch Operations

---

# 4. Functions

## What is it?

A Function is similar to a Stored Procedure but **returns a value**.

### Example

```sql
CREATE FUNCTION total(a INT,b INT)

RETURNS INT

LANGUAGE SQL

AS $$

SELECT a+b;

$$;
```

Run

```sql
SELECT total(10,20);
```

### Output

```
30
```

### Where to Use

- Tax Calculation
- Discount Calculation
- Business Logic
- Reusable SQL

---

# 5. Triggers (Basic)

## What is a Trigger?

A Trigger automatically runs when an event occurs.

Events

- INSERT
- UPDATE
- DELETE

### Example

Whenever a new user is added.

```sql
CREATE TRIGGER user_trigger

AFTER INSERT

ON users

FOR EACH ROW

EXECUTE FUNCTION log_user();
```

### Where to Use

- Audit Logs
- Notifications
- History Tables
- Auto Updates

---

# 6. Common Table Expressions (CTE)

## What is a CTE?

A CTE creates a temporary result set using the `WITH` keyword.

Makes complex queries easier to read.

### Example

```sql
WITH high_salary AS (

SELECT *

FROM employees

WHERE salary>50000

)

SELECT *

FROM high_salary;
```

### Output

Employees with salary above 50000.

### Where to Use

- Complex Reports
- Large Queries
- Readability

---

# 7. Recursive CTE

## What is it?

A Recursive CTE references itself.

Used for hierarchical data.

### Example

Employee → Manager

Category → Parent Category

Folder → Subfolder

### Example

```sql
WITH RECURSIVE numbers AS (

SELECT 1

UNION ALL

SELECT number+1

FROM numbers

WHERE number<5

)

SELECT *

FROM numbers;
```

### Output

```
1

2

3

4

5
```

### Where to Use

- Organization Charts
- Category Trees
- File Systems
- Comments with Replies

---

# 8. Subqueries

## What is a Subquery?

A query inside another query.

### Example

Find employees earning more than average salary.

```sql
SELECT *

FROM employees

WHERE salary>(

SELECT AVG(salary)

FROM employees

);
```

### Output

Employees whose salary is greater than the average salary.

### Where to Use

- Reports
- Filtering
- Comparisons

---

# 9. Correlated Subqueries

## What is it?

A Correlated Subquery depends on the outer query.

It runs once for each row.

### Example

Find employees earning more than the average salary of their department.

```sql
SELECT *

FROM employees e

WHERE salary>(

SELECT AVG(salary)

FROM employees

WHERE department=e.department

);
```

### Output

Only employees above their department average.

### Where to Use

- Department Reports
- Sales Analysis
- Business Intelligence

---

# 10. Window Functions

## What are Window Functions?

Window Functions perform calculations across rows **without grouping them**.

Unlike `GROUP BY`, they **keep every row**.

Common Functions

- ROW_NUMBER()
- RANK()
- DENSE_RANK()
- LAG()
- LEAD()

### Example

Assign row numbers.

```sql
SELECT

name,

salary,

ROW_NUMBER()

OVER(

ORDER BY salary DESC

)

FROM employees;
```

### Output

| name  | salary | row_number |
| ----- | ------ | ---------- |
| Hasan | 60000  | 1          |
| Rahim | 50000  | 2          |
| Karim | 40000  | 3          |

### Where to Use

- Leaderboards
- Rankings
- Pagination
- Reports
- Analytics

---

# Real-World Uses

| Feature             | Common Uses                  |
| ------------------- | ---------------------------- |
| View                | Dashboard, Reports           |
| Materialized View   | Analytics, BI Reports        |
| Stored Procedure    | Batch Jobs, Payroll          |
| Function            | Calculations, Business Logic |
| Trigger             | Audit Logs, Notifications    |
| CTE                 | Complex Queries              |
| Recursive CTE       | Trees, Hierarchies           |
| Subquery            | Filtering                    |
| Correlated Subquery | Advanced Filtering           |
| Window Functions    | Rankings, Analytics          |

---

# Quick Revision

| Topic               | Purpose                                        |
| ------------------- | ---------------------------------------------- |
| View                | Virtual table from a query                     |
| Materialized View   | Stored query result for faster reads           |
| Stored Procedure    | Store and execute multiple SQL statements      |
| Function            | Reusable SQL logic that returns a value        |
| Trigger             | Automatically executes on INSERT/UPDATE/DELETE |
| CTE                 | Temporary named query using `WITH`             |
| Recursive CTE       | Self-referencing CTE for hierarchical data     |
| Subquery            | Query inside another query                     |
| Correlated Subquery | Subquery that depends on the outer query       |
| Window Functions    | Calculate across rows without grouping them    |

---

# Interview Questions

### Basic

1. What is the difference between a View and a Materialized View?
2. What is a Stored Procedure?
3. What is the difference between a Function and a Stored Procedure?
4. What is a Trigger?
5. What is a CTE?

### Intermediate

6. When would you use a Recursive CTE?
7. What is the difference between a Subquery and a Correlated Subquery?
8. Why are CTEs preferred over deeply nested queries?

### Advanced

9. What is the difference between `GROUP BY` and Window Functions?
10. When would you choose a Materialized View instead of a View?
11. How do Window Functions help in analytics queries?
12. Give a real-world example where a Trigger is useful.

> 💡 **Senior Developer Tip:**  
> In modern backend development, **Views** simplify reusable queries, **CTEs** improve readability, **Window Functions** are heavily used in analytics and reporting, and **Subqueries** help solve complex filtering problems. Features like **Stored Procedures** and **Triggers** are powerful but are often used selectively to keep business logic maintainable in the application layer.
