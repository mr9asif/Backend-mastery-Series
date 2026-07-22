# 📚 Phase 5 - GROUP BY & HAVING (SQL Mastery)

> In real-world projects, we often don't need every row individually. Instead, we need summaries like:
>
> - Total orders per customer
> - Average salary per department
> - Total revenue per month
> - Number of products per category
>
> That's where **GROUP BY** and **HAVING** become essential.

---

# Sample Table

## employees

| id  | name   | department | city     | salary |
| --- | ------ | ---------- | -------- | ------ |
| 1   | Rahim  | IT         | Dhaka    | 50000  |
| 2   | Karim  | HR         | Dhaka    | 40000  |
| 3   | Hasan  | IT         | Rajshahi | 60000  |
| 4   | Sakib  | Sales      | Dhaka    | 45000  |
| 5   | Fahim  | IT         | Dhaka    | 55000  |
| 6   | Nayeem | HR         | Rajshahi | 42000  |

---

# 1. GROUP BY

## What is it?

`GROUP BY` groups rows that have the same value into a single group.

Instead of showing every employee, SQL creates one group for each department (or city, etc.).

---

## Syntax

```sql
SELECT department
FROM employees
GROUP BY department;
```

---

## Example 1

Find all departments.

```sql
SELECT department
FROM employees
GROUP BY department;
```

### Output

| department |
| ---------- |
| IT         |
| HR         |
| Sales      |

---

## Example 2

Count employees in each department.

```sql
SELECT department,
COUNT(*) AS total_employee
FROM employees
GROUP BY department;
```

### Output

| department | total_employee |
| ---------- | -------------- |
| IT         | 3              |
| HR         | 2              |
| Sales      | 1              |

---

## Real World Uses

✅ Number of users in each country

✅ Number of products in each category

✅ Orders per customer

✅ Posts per author

---

# 2. Aggregate + GROUP BY

Aggregate Functions become much more powerful with GROUP BY.

Instead of calculating for the whole table, SQL calculates for each group.

---

## COUNT()

```sql
SELECT department,
COUNT(*) AS total_employee
FROM employees
GROUP BY department;
```

### Output

| department | total_employee |
| ---------- | -------------- |
| IT         | 3              |
| HR         | 2              |
| Sales      | 1              |

---

## SUM()

Find total salary of each department.

```sql
SELECT department,
SUM(salary) AS total_salary
FROM employees
GROUP BY department;
```

### Output

| department | total_salary |
| ---------- | ------------ |
| IT         | 165000       |
| HR         | 82000        |
| Sales      | 45000        |

---

## AVG()

Average salary.

```sql
SELECT department,
AVG(salary) AS average_salary
FROM employees
GROUP BY department;
```

### Output

| department | average_salary |
| ---------- | -------------- |
| IT         | 55000          |
| HR         | 41000          |
| Sales      | 45000          |

---

## MAX()

Highest salary.

```sql
SELECT department,
MAX(salary) AS highest_salary
FROM employees
GROUP BY department;
```

### Output

| department | highest_salary |
| ---------- | -------------- |
| IT         | 60000          |
| HR         | 42000          |
| Sales      | 45000          |

---

## MIN()

Lowest salary.

```sql
SELECT department,
MIN(salary) AS lowest_salary
FROM employees
GROUP BY department;
```

### Output

| department | lowest_salary |
| ---------- | ------------- |
| IT         | 50000         |
| HR         | 40000         |
| Sales      | 45000         |

---

# Real World Example

Imagine an E-commerce Website.

Orders Table

| customer | amount |
| -------- | ------ |
| Rahim    | 500    |
| Rahim    | 300    |
| Karim    | 200    |
| Karim    | 400    |
| Hasan    | 600    |

Find total spending of each customer.

```sql
SELECT customer,
SUM(amount) AS total_spent
FROM orders
GROUP BY customer;
```

### Output

| customer | total_spent |
| -------- | ----------- |
| Rahim    | 800         |
| Karim    | 600         |
| Hasan    | 600         |

Very common in dashboards.

---

# 3. GROUP BY Multiple Columns

You can group by more than one column.

---

Example

Group by Department and City.

```sql
SELECT department,
city,
COUNT(*) AS total
FROM employees
GROUP BY department, city;
```

### Output

| department | city     | total |
| ---------- | -------- | ----- |
| IT         | Dhaka    | 2     |
| IT         | Rajshahi | 1     |
| HR         | Dhaka    | 1     |
| HR         | Rajshahi | 1     |
| Sales      | Dhaka    | 1     |

---

## Real World Uses

Sales per City

Revenue per Month and Year

Orders per Customer per Year

Students per Department per Semester

---

# 4. HAVING

## What is HAVING?

`HAVING` filters **groups** after `GROUP BY`.

Remember

WHERE filters rows.

HAVING filters groups.

---

Example

Find departments having more than 2 employees.

```sql
SELECT department,
COUNT(*) AS total_employee
FROM employees
GROUP BY department
HAVING COUNT(*) > 2;
```

### Output

| department | total_employee |
| ---------- | -------------- |
| IT         | 3              |

---

Another Example

Departments whose average salary is greater than 45000.

```sql
SELECT department,
AVG(salary) AS avg_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 45000;
```

### Output

| department | avg_salary |
| ---------- | ---------- |
| IT         | 55000      |

---

## Real World Uses

Customers who spent more than $1000

Departments having more than 20 employees

Products sold more than 100 times

Authors having more than 50 posts

---

# 5. Filtering Groups

Sometimes you need both WHERE and HAVING.

Example

Only employees from Dhaka.

Then group them.

Then keep departments having at least 2 employees.

```sql
SELECT department,
COUNT(*) AS total_employee
FROM employees
WHERE city='Dhaka'
GROUP BY department
HAVING COUNT(*) >=2;
```

### Output

| department | total_employee |
| ---------- | -------------- |
| IT         | 2              |

---

# Execution Order

SQL executes queries in this order:

```
FROM

↓

WHERE

↓

GROUP BY

↓

HAVING

↓

SELECT

↓

ORDER BY

↓

LIMIT
```

This is a very common interview question.

---

# WHERE vs HAVING

| WHERE                          | HAVING                      |
| ------------------------------ | --------------------------- |
| Filters rows                   | Filters groups              |
| Executes before GROUP BY       | Executes after GROUP BY     |
| Cannot use aggregate functions | Can use aggregate functions |
| Faster                         | Usually slower              |

Example

WHERE

```sql
SELECT *
FROM employees
WHERE salary > 50000;
```

HAVING

```sql
SELECT department,
AVG(salary)
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;
```

---

# Common Real World Examples

### Dashboard

Number of users per country

```sql
SELECT country,
COUNT(*)
FROM users
GROUP BY country;
```

---

### E-commerce

Revenue by category

```sql
SELECT category,
SUM(price)
FROM products
GROUP BY category;
```

---

### School

Students in each department

```sql
SELECT department,
COUNT(*)
FROM students
GROUP BY department;
```

---

### Banking

Total balance by branch

```sql
SELECT branch,
SUM(balance)
FROM accounts
GROUP BY branch;
```

---

### Blogging

Posts per author

```sql
SELECT author_id,
COUNT(*)
FROM posts
GROUP BY author_id;
```

---

# Interview Questions

### Basic

1. What is GROUP BY?
2. Why do we use GROUP BY?
3. Difference between WHERE and HAVING?

### Intermediate

4. Can GROUP BY work without Aggregate Functions?
5. Why can't Aggregate Functions be used inside WHERE?
6. Can HAVING be used without GROUP BY?

### Advanced

7. Difference between GROUP BY and DISTINCT?
8. Explain SQL execution order.
9. When should you use WHERE instead of HAVING?

---

# Quick Revision

| Topic                     | Purpose                              |
| ------------------------- | ------------------------------------ |
| GROUP BY                  | Group rows having the same value     |
| COUNT() + GROUP BY        | Count records in each group          |
| SUM() + GROUP BY          | Total value of each group            |
| AVG() + GROUP BY          | Average value of each group          |
| MIN() + GROUP BY          | Smallest value in each group         |
| MAX() + GROUP BY          | Largest value in each group          |
| GROUP BY Multiple Columns | Create groups using multiple columns |
| HAVING                    | Filter grouped results               |
| WHERE                     | Filter rows before grouping          |
| HAVING                    | Filter groups after grouping         |

> 💡 **Senior Developer Tip:**  
> In backend development (Node.js, Prisma, PostgreSQL, MySQL), `GROUP BY` is commonly used for analytics dashboards, admin panels, reports, revenue summaries, user statistics, and business intelligence queries. Mastering `GROUP BY` and `HAVING` is essential for writing efficient reporting queries in real-world applications.
