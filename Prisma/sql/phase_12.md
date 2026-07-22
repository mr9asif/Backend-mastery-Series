# 📚 Phase 12 - Database Design & Normalization

> Database Design is the process of organizing data so it is **efficient, scalable, and easy to maintain**.
>
> A well-designed database reduces duplicate data, improves performance, and maintains data integrity.

---

# Database Design Process

```
Requirements

↓

Entities

↓

Attributes

↓

Relationships

↓

ER Diagram

↓

Normalization

↓

Database Tables
```

---

# 1. Entity

## What is an Entity?

An **Entity** is a real-world object that we want to store data about.

### Examples

- User
- Product
- Order
- Student
- Employee

Example

```
Entity

↓

Student
```

Student is an Entity because we store information about students.

### Real-world Use

E-commerce

- User
- Product
- Order
- Category

---

# 2. Attribute

## What is an Attribute?

An **Attribute** is a property of an Entity.

Example

Entity

```
Student
```

Attributes

```
id

name

email

phone

age
```

Database Table

| id  | name | email | phone |
| --- | ---- | ----- | ----- |

### Real-world Use

User Entity

- Name
- Email
- Password
- Address

---

# 3. Relationship

## What is a Relationship?

A Relationship connects two or more Entities.

Example

```
User

↓

Order
```

One User can place many Orders.

### Real-world Examples

- User → Orders
- Student → Courses
- Customer → Payments
- Author → Posts

---

# 4. ER Diagram (Entity Relationship Diagram)

## What is it?

An **ER Diagram** is a visual representation of Entities and their Relationships.

Example

```
Users

(id,name)

↓

1 ------ N

↓

Orders

(id,user_id,amount)
```

Meaning

One User can have many Orders.

### Where to Use

Before creating database tables.

---

# 5. Cardinality

## What is Cardinality?

Cardinality defines **how many records** are related between two entities.

Types

### One-to-One (1:1)

```
User

↓

Profile
```

One user has one profile.

---

### One-to-Many (1:N)

```
User

↓

Orders
```

One user can have many orders.

---

### Many-to-Many (M:N)

```
Students

↓

Enrollments

↓

Courses
```

One student takes many courses.

One course has many students.

### Real-world Uses

| Relationship | Example             |
| ------------ | ------------------- |
| 1:1          | User → Profile      |
| 1:N          | Category → Products |
| M:N          | Student ↔ Course    |

---

# 6. Optional vs Mandatory Relationships

## Optional Relationship

A relationship **may or may not exist**.

Example

```
User

↓

Profile
```

A new user may not create a profile immediately.

Profile is optional.

---

## Mandatory Relationship

A relationship **must exist**.

Example

```
Order

↓

User
```

Every Order must belong to a User.

Order cannot exist without a User.

### Real-world Examples

Optional

- User → Profile
- Product → Discount

Mandatory

- Order → User
- Payment → Order
- Comment → Post

---

# 7. Normalization

## What is Normalization?

Normalization is the process of organizing data to

- Remove duplicate data
- Improve consistency
- Reduce update problems

Goal

```
Less Redundancy

+

Better Design
```

---

# 8. First Normal Form (1NF)

## Rule

Every column must contain **only one value**.

❌ Bad

| id  | name  | phone       |
| --- | ----- | ----------- |
| 1   | Rahim | 01711,01822 |

One column contains multiple phone numbers.

---

✅ Good

| id  | name  | phone |
| --- | ----- | ----- |
| 1   | Rahim | 01711 |
| 1   | Rahim | 01822 |

or create a separate `phones` table.

### Why?

Databases work best with atomic (single) values.

---

# 9. Second Normal Form (2NF)

## Rule

Must satisfy 1NF.

Every non-key column must depend on the **entire Primary Key**.

Example

Enrollment Table

| student_id | course_id | student_name |
| ---------- | --------- | ------------ |

`student_name` depends only on `student_id`.

Not on the whole key.

Move student information to a separate Students table.

### Benefit

Removes partial dependency.

---

# 10. Third Normal Form (3NF)

## Rule

Must satisfy 2NF.

Non-key columns should depend only on the Primary Key.

Not on another non-key column.

❌ Bad

| id | city | zip_code |

If zip_code determines city,

then city depends on zip_code instead of id.

Move zip information into another table.

### Benefit

Removes transitive dependency.

---

# 11. BCNF (Boyce-Codd Normal Form)

## What is it?

BCNF is a stronger version of 3NF.

Rule

Every determinant must be a Candidate Key.

### Example

Teacher → Subject

If one teacher always teaches one subject,

store this relationship separately.

### Why?

Prevents hidden redundancy.

### Real-world Use

Large enterprise databases.

---

# 12. Denormalization

## What is it?

Denormalization is the process of **adding controlled redundancy** to improve read performance.

Instead of many JOINs,

store repeated data intentionally.

### Example

Normalized

```
Orders

↓

Users
```

Need JOIN to get customer name.

Denormalized

```
Orders

customer_name
```

No JOIN needed.

### Advantages

- Faster Queries
- Better Reports
- Less JOINs

### Disadvantages

- Duplicate Data
- More Storage
- Harder Updates

### Where to Use

- Analytics
- Dashboards
- Data Warehouses
- Reporting Systems

---

# Normalization Summary

| Form            | Purpose                                                  |
| --------------- | -------------------------------------------------------- |
| 1NF             | One value per column                                     |
| 2NF             | Remove partial dependency                                |
| 3NF             | Remove transitive dependency                             |
| BCNF            | Stronger version of 3NF                                  |
| Denormalization | Improve read performance by adding controlled redundancy |

---

# Real-World Example

## E-commerce Database

Entities

- Users
- Products
- Categories
- Orders
- Payments

Relationships

```
User

↓

Orders

↓

Order Items

↓

Products

↓

Categories
```

Normalization

- Separate Users table
- Separate Products table
- Separate Categories table
- Foreign Keys connect them

This reduces duplicate data and makes updates easier.

---

# Quick Revision

| Topic                  | Purpose                                    |
| ---------------------- | ------------------------------------------ |
| Entity                 | Real-world object stored in the database   |
| Attribute              | Property of an entity                      |
| Relationship           | Connection between entities                |
| ER Diagram             | Visual model of entities and relationships |
| Cardinality            | Defines how many records are related       |
| Optional Relationship  | Relationship may exist                     |
| Mandatory Relationship | Relationship must exist                    |
| 1NF                    | One value per column                       |
| 2NF                    | Remove partial dependency                  |
| 3NF                    | Remove transitive dependency               |
| BCNF                   | Stronger normalization rule                |
| Denormalization        | Add redundancy for better performance      |

---

# Interview Questions

### Basic

1. What is an Entity?
2. What is an Attribute?
3. What is an ER Diagram?
4. What is Cardinality?
5. Difference between Optional and Mandatory Relationships?

### Intermediate

6. What is Normalization?
7. Explain 1NF, 2NF, and 3NF with examples.
8. What is BCNF?
9. When should you use Denormalization?

### Advanced

10. Why is normalization important in database design?
11. What problems does denormalization solve?
12. How do you decide between normalization and denormalization in a real-world project?
13. Explain a normalized database design for an e-commerce application.

> 💡 **Senior Developer Tip:**  
> In production systems, databases are usually designed in **3NF** to minimize redundancy and maintain consistency. However, for high-performance reporting or analytics, developers may selectively **denormalize** specific data to reduce expensive JOIN operations while keeping the rest of the schema normalized.
