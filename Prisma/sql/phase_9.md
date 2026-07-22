# 📚 Phase 9 - SQL Indexing & Query Performance

> **What is an Index?**
>
> An **Index** is a special data structure that helps the database find rows much faster without scanning the entire table.
>
> 📌 Think of it like the **index page of a book**. Instead of reading every page, you look at the index and jump directly to the required page.

---

# Why Indexes Exist

Without an index:

```
Database

↓

Read Row 1

↓

Read Row 2

↓

Read Row 3

↓

...

↓

Read 1,000,000 Rows
```

With an index:

```
Database

↓

Index

↓

Jump Directly to Required Row
```

Result:

✅ Faster Search

✅ Faster Filtering

✅ Faster Sorting

---

# Sample Table

## users

| id  | name  | email           | city   |
| --- | ----- | --------------- | ------ |
| 1   | Rahim | rahim@gmail.com | Dhaka  |
| 2   | Karim | karim@gmail.com | Khulna |
| 3   | Hasan | hasan@gmail.com | Dhaka  |
| ... | ...   | ...             | ...    |

---

# What is an Index?

An Index stores a sorted reference to table data.

Example

```sql
CREATE INDEX idx_users_email
ON users(email);
```

Now this query becomes much faster.

```sql
SELECT *
FROM users
WHERE email='rahim@gmail.com';
```

### Where to Use

- Login (Email)
- Username Search
- Product Search
- Order Lookup

---

# Why Indexes Exist

Indexes improve queries that use

- WHERE
- JOIN
- ORDER BY
- GROUP BY

Without an index, the database must scan every row.

---

# B-Tree Index ⭐ (Default)

## What is it?

B-Tree (Balanced Tree) is the default index in PostgreSQL and most relational databases.

It stores values in sorted order.

### Example

```sql
CREATE INDEX idx_name
ON users(name);
```

Now

```sql
SELECT *
FROM users
WHERE name='Rahim';
```

is very fast.

### Best For

- WHERE
- ORDER BY
- BETWEEN
- <
- >
- > =
- <=

### Real-world Use

Almost every application.

---

# Hash Index

## What is it?

Uses a hash table instead of a tree.

Very fast for exact matches.

### Example

```sql
CREATE INDEX idx_email_hash

ON users

USING HASH(email);
```

### Best For

```sql
WHERE email='rahim@gmail.com'
```

### Not Good For

```sql
ORDER BY

BETWEEN

<
>
```

---

# Composite Index

## What is it?

An index built on multiple columns.

### Example

```sql
CREATE INDEX idx_name_city

ON users(name,city);
```

Now this query becomes faster.

```sql
SELECT *

FROM users

WHERE name='Rahim'

AND city='Dhaka';
```

### Real-world Use

Search by

- Name + City
- First Name + Last Name
- Category + Price

---

# Clustered Index

## What is it?

The table data itself is physically stored in index order.

Only one clustered index is possible.

Example

```
1

2

3

4

5
```

Rows are stored in sorted order.

### Real-world Use

SQL Server uses clustered indexes by default for Primary Keys.

(PostgreSQL does not automatically create clustered indexes.)

---

# Non-Clustered Index

## What is it?

Stores pointers to table rows.

The table itself remains unchanged.

Example

```
Index

↓

Pointer

↓

Actual Data
```

### Real-world Use

Most indexes in PostgreSQL are non-clustered.

---

# Covering Index

## What is it?

An index containing **all columns needed by a query**, so the database doesn't need to read the table.

### Example

```sql
CREATE INDEX idx_users_cover

ON users(name,email);
```

Query

```sql
SELECT name,email

FROM users

WHERE name='Rahim';
```

Everything is already inside the index.

No table lookup required.

### Benefit

Very fast.

---

# Partial Index

## What is it?

Indexes only rows matching a condition.

### Example

```sql
CREATE INDEX idx_active_users

ON users(email)

WHERE active=true;
```

Only active users are indexed.

### Real-world Use

- Active Users
- Published Posts
- Paid Orders

Saves storage and improves speed.

---

# Table Scan

## What is it?

Database reads every row.

```
Row1

↓

Row2

↓

Row3

↓

...

↓

Last Row
```

### Happens When

- No index exists.
- Query cannot use an index.

### Performance

❌ Slow on large tables.

---

# Index Scan

## What is it?

Database uses an index to locate rows.

```
Index

↓

Required Row
```

### Performance

✅ Much faster.

---

# Sequential Scan

## What is it?

Another name for reading the table from start to end.

Example

```sql
SELECT *

FROM users

WHERE city='Dhaka';
```

If no index exists,

PostgreSQL performs

```
Sequential Scan
```

---

# Query Planner

## What is it?

The Query Planner decides the fastest way to execute a query.

It chooses

- Table Scan
- Index Scan
- Hash Join
- Merge Join
- Nested Loop

Automatically.

Developers don't manually choose these in normal SQL.

---

# EXPLAIN

## What is it?

Shows **how PostgreSQL plans to execute** a query.

### Example

```sql
EXPLAIN

SELECT *

FROM users

WHERE email='rahim@gmail.com';
```

Possible Output

```
Index Scan

using idx_users_email
```

or

```
Seq Scan
```

### Why Use It?

To check

- Is the index being used?
- Is the query efficient?

---

# EXPLAIN ANALYZE

## What is it?

Runs the query and shows the actual execution statistics.

### Example

```sql
EXPLAIN ANALYZE

SELECT *

FROM users

WHERE email='rahim@gmail.com';
```

Example Output

```
Index Scan

Execution Time: 0.15 ms
```

### Difference

| EXPLAIN               | EXPLAIN ANALYZE                         |
| --------------------- | --------------------------------------- |
| Shows execution plan  | Executes query + shows real performance |
| Doesn't run the query | Runs the query                          |

---

# When Should You Create an Index?

✅ Frequently searched columns

```sql
WHERE email=...
```

---

✅ JOIN columns

```sql
user_id
```

---

✅ ORDER BY columns

```sql
ORDER BY created_at DESC
```

---

✅ GROUP BY columns

```sql
GROUP BY department
```

---

# When Should You Avoid an Index?

❌ Very small tables

❌ Columns that change frequently

❌ Low-cardinality columns (few unique values, e.g., gender)

Too many indexes slow down

- INSERT
- UPDATE
- DELETE

because indexes also need to be updated.

---

# Real-World Examples

| Application  | Indexed Columns           |
| ------------ | ------------------------- |
| Login System | email                     |
| E-commerce   | product_name, category_id |
| Banking      | account_number            |
| Facebook     | user_id                   |
| YouTube      | video_id                  |
| Blog         | slug                      |
| School       | student_id                |

---

# Quick Revision

| Topic               | Purpose                                     |
| ------------------- | ------------------------------------------- |
| Index               | Speeds up data retrieval                    |
| B-Tree Index        | Default index for most queries              |
| Hash Index          | Fast exact-match searches                   |
| Composite Index     | Index on multiple columns                   |
| Clustered Index     | Data stored in index order                  |
| Non-Clustered Index | Separate index pointing to table rows       |
| Covering Index      | Query served entirely from the index        |
| Partial Index       | Index only selected rows                    |
| Table Scan          | Reads every row                             |
| Index Scan          | Uses an index to find rows                  |
| Sequential Scan     | Full table scan                             |
| Query Planner       | Chooses the fastest execution plan          |
| EXPLAIN             | Shows the planned execution strategy        |
| EXPLAIN ANALYZE     | Executes query and shows actual performance |

---

# Interview Questions

### Basic

1. What is an Index?
2. Why do databases use indexes?
3. Difference between Table Scan and Index Scan?
4. What is a B-Tree Index?
5. What is a Composite Index?

### Intermediate

6. When should you create an index?
7. When should you avoid creating an index?
8. Difference between Hash Index and B-Tree Index?
9. What is a Covering Index?
10. What is a Partial Index?

### Advanced

11. What does PostgreSQL's Query Planner do?
12. Difference between EXPLAIN and EXPLAIN ANALYZE?
13. Why can too many indexes reduce INSERT/UPDATE/DELETE performance?
14. Why is B-Tree the default index type in PostgreSQL?

> 💡 **Senior Developer Tip:**  
> In real-world backend development, you rarely add indexes randomly. Instead, use **`EXPLAIN ANALYZE`** to identify slow queries first, then create indexes on the columns used most often in `WHERE`, `JOIN`, `ORDER BY`, and `GROUP BY`. This data-driven approach avoids unnecessary indexes and keeps both read and write performance balanced.
