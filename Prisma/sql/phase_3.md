# 📚 SQL CRUD & Advanced SELECT Cheat Sheet

> This file contains the most commonly used SQL commands with syntax, examples, real-world use cases, and alternatives.

---

# Sample Table

## users

| id  | name  | email           | age | city     | phone       |
| --- | ----- | --------------- | --- | -------- | ----------- |
| 1   | Rahim | rahim@gmail.com | 22  | Dhaka    | 01711111111 |
| 2   | Karim | karim@gmail.com | 19  | Rajshahi | NULL        |
| 3   | Hasan | hasan@gmail.com | 25  | Dhaka    | 01822222222 |
| 4   | Sojib | sojib@gmail.com | 28  | Khulna   | NULL        |

---

# 1. INSERT

### Category

DML (Data Manipulation Language)

### Purpose

Used to insert new records into a table.

### Syntax

```sql
INSERT INTO users(name,email,age,city)
VALUES('Sakib','sakib@gmail.com',24,'Dhaka');
```

### Output

A new row is added.

| id  | name  | email           |
| --- | ----- | --------------- |
| 5   | Sakib | sakib@gmail.com |

### Real-world Use

- User Registration
- Add Product
- Create Order
- Add Comment

### Alternative

None.

---

# 2. SELECT

### Category

DQL (Data Query Language)

### Purpose

Used to retrieve data.

### Syntax

```sql
SELECT *
FROM users;
```

### Output

Returns all users.

### Real-world Use

- Login
- Profile Page
- Dashboard
- Product List

### Alternative

Select specific columns instead of `*`

```sql
SELECT name,email
FROM users;
```

Better for performance.

---

# 3. UPDATE

### Category

DML

### Purpose

Updates existing records.

### Syntax

```sql
UPDATE users
SET city='Chattogram'
WHERE id=2;
```

### Output

User 2 city becomes Chattogram.

### Real-world Use

- Edit Profile
- Change Password
- Update Product Price

### Important

Always use WHERE.

❌ Wrong

```sql
UPDATE users
SET city='Dhaka';
```

This updates EVERY user.

---

# 4. DELETE

### Category

DML

### Purpose

Deletes records.

### Syntax

```sql
DELETE
FROM users
WHERE id=4;
```

### Output

User with id 4 is deleted.

### Real-world Use

- Delete Account
- Delete Product
- Remove Comment

### Important

Never forget WHERE.

---

# 5. WHERE

### Category

DQL

### Purpose

Filters rows.

### Syntax

```sql
SELECT *
FROM users
WHERE city='Dhaka';
```

### Output

Only users from Dhaka.

### Real-world Use

- Search Users
- Product Filters
- Admin Dashboard

### Alternative Operators

```sql
=
>
<
>=
<=
<>
!=
```

Example

```sql
WHERE age > 20
```

---

# 6. ORDER BY

### Category

DQL

### Purpose

Sorts data.

### Syntax

Ascending

```sql
SELECT *
FROM users
ORDER BY age ASC;
```

Descending

```sql
SELECT *
FROM users
ORDER BY age DESC;
```

### Output

Rows sorted by age.

### Real-world Use

- Latest Posts
- Highest Price
- Lowest Price

---

# 7. LIMIT

### Category

DQL

### Purpose

Returns limited rows.

### Syntax

```sql
SELECT *
FROM users
LIMIT 2;
```

### Output

Only first two users.

### Real-world Use

- Homepage
- Top Products
- Recent Posts

### Alternative

SQL Server uses

```sql
TOP 2
```

instead of LIMIT.

---

# 8. OFFSET

### Category

DQL

### Purpose

Skips rows.

### Syntax

```sql
SELECT *
FROM users
LIMIT 2 OFFSET 2;
```

### Output

Skips first two users and returns next two.

### Real-world Use

Pagination.

Example

Page 1

```sql
LIMIT 10 OFFSET 0
```

Page 2

```sql
LIMIT 10 OFFSET 10
```

Page 3

```sql
LIMIT 10 OFFSET 20
```

---

# 9. DISTINCT

### Category

DQL

### Purpose

Removes duplicate values.

### Syntax

```sql
SELECT DISTINCT city
FROM users;
```

### Output

Dhaka

Rajshahi

Khulna

### Real-world Use

- Filter Options
- Unique Categories
- Unique Cities

### Alternative

GROUP BY can also produce unique values.

---

# 10. ALIASES (AS)

### Category

DQL

### Purpose

Renames a column temporarily.

### Syntax

```sql
SELECT name AS full_name
FROM users;
```

### Output

| full_name |
| --------- |
| Rahim     |

### Real-world Use

- API Response
- Reports
- Dashboard

### Alternative

```sql
SELECT name full_name
FROM users;
```

`AS` is optional in PostgreSQL.

---

# 11. LIKE

### Category

DQL

### Purpose

Pattern searching.

### Syntax

Starts with R

```sql
SELECT *
FROM users
WHERE name LIKE 'R%';
```

Ends with m

```sql
LIKE '%m'
```

Contains "ha"

```sql
LIKE '%ha%'
```

Single Character

```sql
LIKE '_a%'
```

### Real-world Use

- Search Bar
- User Search
- Product Search

### Alternative

ILIKE (PostgreSQL)

Case-insensitive search.

```sql
WHERE name ILIKE 'rahim'
```

---

# 12. IN

### Category

DQL

### Purpose

Checks multiple values.

### Syntax

```sql
SELECT *
FROM users
WHERE city IN ('Dhaka','Khulna');
```

### Output

Returns users from Dhaka and Khulna.

### Real-world Use

- Multi Filter
- Multiple Categories

### Alternative

```sql
WHERE city='Dhaka'
OR city='Khulna'
```

IN is cleaner.

---

# 13. BETWEEN

### Category

DQL

### Purpose

Checks a range.

### Syntax

```sql
SELECT *
FROM users
WHERE age BETWEEN 20 AND 25;
```

### Output

Returns users whose age is between 20 and 25.

### Real-world Use

- Price Filter
- Date Filter
- Age Filter

### Alternative

```sql
WHERE age >=20
AND age <=25
```

---

# 14. IS NULL

### Category

DQL

### Purpose

Finds NULL values.

### Syntax

```sql
SELECT *
FROM users
WHERE phone IS NULL;
```

### Output

Users without phone numbers.

### Real-world Use

- Incomplete Profiles
- Missing Data

### Alternative

Find non-null values.

```sql
WHERE phone IS NOT NULL
```

---

# 15. EXISTS

### Category

DQL

### Purpose

Checks whether another query returns at least one row.

### Example Tables

users

orders

### Query

```sql
SELECT name
FROM users u
WHERE EXISTS (
    SELECT 1
    FROM orders o
    WHERE o.user_id = u.id
);
```

### Output

Returns users who have placed at least one order.

### Real-world Use

- Active Customers
- Users with Orders
- Products with Reviews

### Alternative

Can also be solved using JOIN.

---

# Quick Revision Table

| Command  | Category | Main Purpose          |
| -------- | -------- | --------------------- |
| INSERT   | DML      | Add new data          |
| SELECT   | DQL      | Read data             |
| UPDATE   | DML      | Modify data           |
| DELETE   | DML      | Remove data           |
| WHERE    | DQL      | Filter rows           |
| ORDER BY | DQL      | Sort rows             |
| LIMIT    | DQL      | Return limited rows   |
| OFFSET   | DQL      | Skip rows             |
| DISTINCT | DQL      | Remove duplicates     |
| AS       | DQL      | Rename columns        |
| LIKE     | DQL      | Pattern search        |
| IN       | DQL      | Match multiple values |
| BETWEEN  | DQL      | Filter by range       |
| IS NULL  | DQL      | Find NULL values      |
| EXISTS   | DQL      | Check related records |
