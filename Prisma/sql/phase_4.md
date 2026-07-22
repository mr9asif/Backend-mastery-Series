# 📚 Phase 4 - SQL Functions (Quick Revision)

> SQL Functions help us manipulate, summarize, and analyze data. They make queries more powerful and reduce the amount of work done in the application.

---

# Sample Table

## employees

| id  | name  | department | salary | age | joined_date |
| --- | ----- | ---------- | ------ | --- | ----------- |
| 1   | Rahim | IT         | 50000  | 24  | 2023-01-10  |
| 2   | Karim | HR         | 40000  | 29  | 2022-06-15  |
| 3   | Hasan | IT         | 60000  | 26  | 2021-09-20  |
| 4   | Sakib | Sales      | 45000  | 30  | 2024-02-05  |

---

# Aggregate Functions

Aggregate Functions perform calculations on multiple rows and return **a single result**.

Functions:

- COUNT()
- SUM()
- AVG()
- MIN()
- MAX()

---

## 1. COUNT()

### Purpose

Counts the number of rows.

### Syntax

```sql
SELECT COUNT(*)
FROM employees;
```

### Output

| count |
| ----- |
| 4     |

### Real-world Use

- Total Users
- Total Orders
- Total Products

---

## 2. SUM()

### Purpose

Calculates the total value of a numeric column.

### Syntax

```sql
SELECT SUM(salary)
FROM employees;
```

### Output

| sum    |
| ------ |
| 195000 |

### Real-world Use

- Total Sales
- Total Revenue
- Total Salary

---

## 3. AVG()

### Purpose

Calculates the average value.

### Syntax

```sql
SELECT AVG(salary)
FROM employees;
```

### Output

| avg   |
| ----- |
| 48750 |

### Real-world Use

- Average Salary
- Average Product Price
- Average Rating

---

## 4. MIN()

### Purpose

Returns the smallest value.

### Syntax

```sql
SELECT MIN(salary)
FROM employees;
```

### Output

| min   |
| ----- |
| 40000 |

### Real-world Use

- Lowest Price
- Youngest Employee
- Earliest Date

---

## 5. MAX()

### Purpose

Returns the largest value.

### Syntax

```sql
SELECT MAX(salary)
FROM employees;
```

### Output

| max   |
| ----- |
| 60000 |

### Real-world Use

- Highest Salary
- Highest Price
- Latest Date

---

# String Functions

String Functions work with text values.

Functions:

- CONCAT()
- LOWER()
- UPPER()
- LENGTH()
- SUBSTRING()

---

## 1. CONCAT()

### Purpose

Joins multiple strings.

### Syntax

```sql
SELECT CONCAT(name,' works in ',department)
FROM employees;
```

### Output

| concat               |
| -------------------- |
| Rahim works in IT    |
| Karim works in HR    |
| Hasan works in IT    |
| Sakib works in Sales |

### Real-world Use

- Full Name
- Address
- Report Generation

---

## 2. LOWER()

### Purpose

Converts text to lowercase.

### Syntax

```sql
SELECT LOWER(name)
FROM employees;
```

### Output

```
rahim
karim
hasan
sakib
```

### Real-world Use

Case-insensitive search.

---

## 3. UPPER()

### Purpose

Converts text to uppercase.

### Syntax

```sql
SELECT UPPER(name)
FROM employees;
```

### Output

```
RAHIM
KARIM
HASAN
SAKIB
```

### Real-world Use

Reports
Export Files

---

## 4. LENGTH()

### Purpose

Returns the number of characters.

### Syntax

```sql
SELECT LENGTH(name)
FROM employees;
```

### Output

| name  | length |
| ----- | ------ |
| Rahim | 5      |
| Karim | 5      |
| Hasan | 5      |
| Sakib | 5      |

### Real-world Use

Password Validation
Username Validation

---

## 5. SUBSTRING()

### Purpose

Extracts part of a string.

### Syntax

```sql
SELECT SUBSTRING(name,1,3)
FROM employees;
```

### Output

```
Rah
Kar
Has
Sak
```

### Real-world Use

Short Names
Initials
Codes

---

# Date Functions

Date Functions work with dates and times.

Functions:

- NOW()
- CURRENT_DATE
- EXTRACT()
- AGE()

---

## 1. NOW()

### Purpose

Returns current date and time.

### Syntax

```sql
SELECT NOW();
```

### Output

```
2026-07-22 10:30:15
```

### Real-world Use

Login Time
Order Time
Created At

---

## 2. CURRENT_DATE

### Purpose

Returns only today's date.

### Syntax

```sql
SELECT CURRENT_DATE;
```

### Output

```
2026-07-22
```

### Real-world Use

Attendance
Today's Orders

---

## 3. EXTRACT()

### Purpose

Extracts a specific part of a date.

### Syntax

```sql
SELECT EXTRACT(YEAR FROM joined_date)
FROM employees;
```

### Output

| year |
| ---- |
| 2023 |
| 2022 |
| 2021 |
| 2024 |

### Real-world Use

Year-wise Reports
Monthly Reports

---

## 4. AGE()

### Purpose

Calculates the difference between two dates.

### Syntax

```sql
SELECT AGE(joined_date)
FROM employees;
```

### Output

```
3 years
4 years
5 years
2 years
```

_(Output depends on the current date.)_

### Real-world Use

Employee Experience
Membership Duration

---

# Numeric Functions

Numeric Functions perform calculations on numbers.

Functions:

- ROUND()
- FLOOR()
- CEIL()

---

## 1. ROUND()

### Purpose

Rounds a decimal number.

### Syntax

```sql
SELECT ROUND(99.567,2);
```

### Output

```
99.57
```

### Real-world Use

Currency
Average Rating

---

## 2. FLOOR()

### Purpose

Rounds down to the nearest integer.

### Syntax

```sql
SELECT FLOOR(99.99);
```

### Output

```
99
```

### Real-world Use

Discount Calculation
Price Calculation

---

## 3. CEIL()

### Purpose

Rounds up to the nearest integer.

### Syntax

```sql
SELECT CEIL(99.01);
```

### Output

```
100
```

### Real-world Use

Shipping Cost
Seat Allocation
Pagination

---

# Quick Revision

| Function     | Purpose                  |
| ------------ | ------------------------ |
| COUNT()      | Count rows               |
| SUM()        | Total value              |
| AVG()        | Average value            |
| MIN()        | Smallest value           |
| MAX()        | Largest value            |
| CONCAT()     | Join strings             |
| LOWER()      | Lowercase text           |
| UPPER()      | Uppercase text           |
| LENGTH()     | Count characters         |
| SUBSTRING()  | Extract part of text     |
| NOW()        | Current date & time      |
| CURRENT_DATE | Today's date             |
| EXTRACT()    | Extract year/month/day   |
| AGE()        | Difference between dates |
| ROUND()      | Round decimal            |
| FLOOR()      | Round down               |
| CEIL()       | Round up                 |

---

# Interview Questions

### Beginner

1. What are Aggregate Functions?
2. Difference between COUNT() and SUM()?
3. Difference between LOWER() and UPPER()?
4. What does NOW() return?
5. Difference between FLOOR() and CEIL()?

### Intermediate

1. Why do we use Aggregate Functions?
2. Can Aggregate Functions be used with GROUP BY?
3. When would you use EXTRACT() instead of CURRENT_DATE?
4. Why is ROUND() useful in financial applications?
