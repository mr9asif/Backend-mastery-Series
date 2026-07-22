# 📚 Phase 10 - SQL Transactions & Concurrency

> **What is a Transaction?**
>
> A **Transaction** is a group of SQL operations executed as a single unit of work.
>
> Either **all operations succeed**, or **none of them are applied**.

---

# Why Transactions?

Imagine a Banking System.

Rahim transfers **1000 BDT** to Karim.

Steps:

1. Deduct 1000 from Rahim
2. Add 1000 to Karim

If the server crashes after step 1, Rahim loses money but Karim doesn't receive it.

❌ Incorrect

A transaction prevents this problem.

---

# Transaction Flow

```
BEGIN

↓

SQL Query

↓

SQL Query

↓

SQL Query

↓

COMMIT

or

ROLLBACK
```

---

# BEGIN

## What is it?

Starts a transaction.

### Example

```sql
BEGIN;
```

Everything after BEGIN becomes part of one transaction.

### Where to Use

- Money Transfer
- Order Placement
- Inventory Update
- Multiple Table Updates

---

# COMMIT

## What is it?

Permanently saves all changes.

### Example

```sql
BEGIN;

UPDATE accounts
SET balance = balance - 1000
WHERE id = 1;

UPDATE accounts
SET balance = balance + 1000
WHERE id = 2;

COMMIT;
```

### Output

✅ Changes are saved permanently.

### Real-world Use

- Payment Success
- Order Completed
- User Registration

---

# ROLLBACK

## What is it?

Cancels all changes made during the transaction.

### Example

```sql
BEGIN;

UPDATE accounts
SET balance = balance - 1000
WHERE id = 1;

ROLLBACK;
```

### Output

Nothing changes.

Balance returns to the original value.

### Real-world Use

- Payment Failed
- Server Error
- Validation Failed

---

# SAVEPOINT

## What is it?

Creates a checkpoint inside a transaction.

You can roll back to that checkpoint without canceling the entire transaction.

### Example

```sql
BEGIN;

UPDATE products
SET stock = stock - 1
WHERE id = 10;

SAVEPOINT stock_updated;

UPDATE orders
SET status='Completed'
WHERE id=100;

ROLLBACK TO stock_updated;

COMMIT;
```

### Result

✔ Stock update remains.

❌ Order update is canceled.

### Where to Use

Large transactions with multiple steps.

---

# ACID Properties

ACID ensures transactions are reliable.

ACID stands for

- Atomicity
- Consistency
- Isolation
- Durability

---

# 1. Atomicity

## Meaning

Everything or Nothing.

If one query fails,

the entire transaction fails.

### Example

```
Deduct Money

✔

Add Money

❌

↓

ROLLBACK
```

### Real-world Use

Banking

Payment Systems

---

# 2. Consistency

## Meaning

Database always remains valid.

Rules and constraints are never broken.

### Example

If balance cannot be negative,

Transaction is rejected.

### Real-world Use

- Foreign Keys
- CHECK Constraints
- Business Rules

---

# 3. Isolation

## Meaning

Multiple transactions should not interfere with each other.

Example

Rahim transfers money.

Karim should not see half-completed data.

### Real-world Use

ATM

Online Banking

E-commerce

---

# 4. Durability

## Meaning

Once COMMIT succeeds,

data is permanently saved.

Even if power fails,

the data remains.

### Real-world Use

Orders

Payments

Invoices

---

# Isolation Levels

Isolation Levels control how transactions interact with each other.

---

# 1. Read Uncommitted

## Meaning

Can read uncommitted data.

### Problem

Dirty Read.

Example

Transaction A updates salary.

Transaction B reads it before COMMIT.

Transaction A rolls back.

Transaction B already saw invalid data.

### Usage

Almost never used.

---

# 2. Read Committed ⭐

## Meaning

Reads only committed data.

No Dirty Reads.

### Example

Transaction A

```
UPDATE salary
```

Not committed.

Transaction B

Cannot see it.

### Used By

PostgreSQL Default

Oracle

SQL Server

---

# 3. Repeatable Read

## Meaning

If you read a row twice,

you get the same result.

### Prevents

- Dirty Read
- Non-repeatable Read

### Real-world Use

Inventory

Bank Balance

---

# 4. Serializable ⭐

## Meaning

Highest isolation level.

Transactions behave as if executed one after another.

### Prevents

- Dirty Read
- Non-repeatable Read
- Phantom Read

### Drawback

Slower performance.

### Real-world Use

Banking

Financial Systems

---

# Concurrency

## What is it?

Concurrency means multiple users access the database at the same time.

Example

```
User A

↓

Database

↑

User B

↑

User C
```

### Real-world Use

Facebook

YouTube

Amazon

Banking

---

# Locking

## What is it?

Locking prevents multiple transactions from modifying the same data simultaneously.

Without locking,

data may become inconsistent.

---

# Row Lock

## What is it?

Locks only one row.

Other rows remain accessible.

### Example

```sql
SELECT *

FROM accounts

WHERE id=1

FOR UPDATE;
```

Only account 1 is locked.

### Benefit

Better performance.

Most commonly used.

---

# Table Lock

## What is it?

Locks the entire table.

No other transaction can modify the table.

### Example

```sql
LOCK TABLE users
IN EXCLUSIVE MODE;
```

### Benefit

Useful for maintenance.

### Drawback

Blocks all users.

---

# Deadlocks

## What is it?

Occurs when two transactions wait for each other forever.

Example

```
Transaction A

Locks Row 1

↓

Needs Row 2

------------------

Transaction B

Locks Row 2

↓

Needs Row 1

```

Both wait forever.

This is called a Deadlock.

### PostgreSQL

Automatically detects deadlocks.

One transaction is canceled.

### How to Avoid

✅ Lock rows in the same order.

✅ Keep transactions short.

✅ Commit quickly.

---

# Real-World Example

## Online Shopping

Customer places an order.

Transaction

```sql
BEGIN;

Reduce product stock;

Create order;

Create payment;

COMMIT;
```

If payment fails,

```sql
ROLLBACK;
```

Stock returns to normal.

No incorrect data.

---

# Quick Revision

| Topic            | Purpose                                         |
| ---------------- | ----------------------------------------------- |
| Transaction      | Execute multiple queries as one unit            |
| BEGIN            | Start a transaction                             |
| COMMIT           | Save all changes permanently                    |
| ROLLBACK         | Undo all changes                                |
| SAVEPOINT        | Roll back to a checkpoint                       |
| Atomicity        | All or nothing                                  |
| Consistency      | Keep database valid                             |
| Isolation        | Transactions don't interfere                    |
| Durability       | Committed data survives failures                |
| Read Uncommitted | Allows dirty reads                              |
| Read Committed   | Reads only committed data (PostgreSQL default)  |
| Repeatable Read  | Same row returns same data within a transaction |
| Serializable     | Highest isolation, safest but slower            |
| Concurrency      | Multiple users access simultaneously            |
| Row Lock         | Lock a single row                               |
| Table Lock       | Lock the whole table                            |
| Deadlock         | Transactions wait on each other                 |

---

# Interview Questions

### Basic

1. What is a transaction?
2. Difference between COMMIT and ROLLBACK?
3. What is SAVEPOINT?
4. What does ACID stand for?
5. What is Concurrency?

### Intermediate

6. Explain the four ACID properties.
7. Difference between Row Lock and Table Lock?
8. What is the default isolation level in PostgreSQL?
9. What is a Deadlock?

### Advanced

10. When should you use Serializable isolation?
11. How do transactions ensure data consistency?
12. How can you avoid deadlocks?
13. Why are transactions essential in banking and e-commerce systems?

> 💡 **Senior Developer Tip:**  
> In real-world backend development (Node.js, Prisma, Django, Laravel, Spring Boot), always wrap related operations (e.g., creating an order, updating inventory, and recording a payment) inside a **single transaction**. If any step fails, use **ROLLBACK** so the database remains consistent and no partial updates are saved.
