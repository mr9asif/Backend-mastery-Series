# 📚 Phase 15 - PostgreSQL Backup, Restore & Replication

> Data is one of the most valuable assets of an application. PostgreSQL provides tools for **backing up**, **restoring**, and **replicating** databases to protect against data loss and improve availability.

---

# Backup & Recovery Workflow

```
Database

↓

Backup (Dump)

↓

Backup File

↓

Restore

↓

Database
```

---

# 1. Backup

## What is a Backup?

A **Backup** is a copy of your database that can be used to recover data if something goes wrong.

### Why Backups Are Important

- Server Failure
- Accidental Data Deletion
- Database Corruption
- Hardware Failure
- Disaster Recovery

### Real-world Use

- Daily Backups
- Weekly Full Backups
- Cloud Storage Backups

---

# 2. Restore

## What is Restore?

**Restore** is the process of recovering a database from a backup.

### Example

```bash
pg_restore \
-d my_database \
backup_file.dump
```

### Result

The backup is restored into the database.

### Where to Use

- Recover deleted data
- Move to a new server
- Disaster recovery

---

# 3. Dump

## What is a Dump?

A **Dump** is an exported copy of a database or its objects.

PostgreSQL provides the `pg_dump` utility.

### Backup an Entire Database

```bash
pg_dump my_database > backup.sql
```

### Custom Format

```bash
pg_dump -Fc my_database \
-f backup.dump
```

### Types of Dumps

- Full Database
- Specific Table
- Schema Only
- Data Only

### Real-world Use

- Database Migration
- Versioned Backups
- Testing

---

# 4. Import

## What is Import?

Import means bringing data **into** a database.

### Import an SQL Backup

```bash
psql my_database \
-f backup.sql
```

### Import CSV Data

```sql
COPY users(name,email)

FROM '/path/users.csv'

DELIMITER ','

CSV HEADER;
```

### Where to Use

- Initial Data
- Migration
- Bulk Upload

---

# 5. Export

## What is Export?

Export means taking data **out of** a database.

### Export Query Result

```sql
COPY (

SELECT *

FROM users

)

TO '/path/users.csv'

DELIMITER ','

CSV HEADER;
```

### Where to Use

- Reports
- Analytics
- Data Sharing
- Excel Processing

---

# Import vs Export

| Import                   | Export                   |
| ------------------------ | ------------------------ |
| Data enters the database | Data leaves the database |
| COPY FROM                | COPY TO                  |
| psql                     | pg_dump / COPY           |

---

# 6. Replication (Overview)

## What is Replication?

Replication is the process of keeping **multiple database servers synchronized**.

One server copies its data to another.

```
Primary Server

↓

Replica Server
```

If the primary server fails,

the replica can be used.

---

# Types of Replication

## Physical Replication

Copies the entire database at the storage level.

### Advantages

- Simple
- Fast
- High Availability

### Used For

- Disaster Recovery
- Failover Servers

---

## Logical Replication

Replicates selected tables or databases.

### Advantages

- Flexible
- Selective Replication

### Used For

- Data Sharing
- Microservices
- Reporting Databases

---

# Why Use Replication?

Benefits

- High Availability
- Disaster Recovery
- Load Balancing
- Read Scaling
- Better Reliability

---

# Primary vs Replica

| Primary                      | Replica              |
| ---------------------------- | -------------------- |
| Accepts Writes               | Usually Read Only    |
| Source of Truth              | Copy of Primary      |
| Handles INSERT/UPDATE/DELETE | Handles Read Queries |

---

# Backup vs Replication

| Backup                               | Replication                  |
| ------------------------------------ | ---------------------------- |
| Snapshot of data                     | Continuous synchronization   |
| Used for recovery                    | Used for high availability   |
| Protects against accidental deletion | Does **not** replace backups |
| Stored separately                    | Keeps another server updated |

> **Important:** Replication is **not a substitute for backups**. If data is accidentally deleted on the primary database, that deletion is usually replicated to the replica as well.

---

# Real-World Example

## E-commerce Application

```
Users

↓

Primary PostgreSQL

↓

Replica PostgreSQL

↓

Analytics & Reporting
```

Every Night

```
pg_dump

↓

Cloud Storage
```

If the primary server crashes,

- Restore from backup if necessary.
- Or promote the replica to become the new primary.

---

# Common PostgreSQL Tools

| Tool       | Purpose                              |
| ---------- | ------------------------------------ |
| pg_dump    | Create logical backups               |
| pg_restore | Restore custom-format backups        |
| psql       | Execute SQL files and import backups |
| COPY       | Import and export table data         |

---

# Quick Revision

| Topic       | Purpose                                     |
| ----------- | ------------------------------------------- |
| Backup      | Create a copy of database data              |
| Restore     | Recover data from a backup                  |
| Dump        | Export a database or its objects            |
| Import      | Load data into a database                   |
| Export      | Extract data from a database                |
| Replication | Keep multiple database servers synchronized |

---

# Interview Questions

### Basic

1. What is a database backup?
2. What is the difference between Backup and Restore?
3. What is `pg_dump`?
4. What is `pg_restore`?
5. Difference between Import and Export?

### Intermediate

6. What is Replication?
7. Difference between Physical and Logical Replication?
8. Why is replication important in production systems?
9. When would you use `COPY` instead of `pg_dump`?

### Advanced

10. Why is replication not a replacement for backups?
11. Explain the difference between Backup and Replication.
12. How would you migrate a PostgreSQL database to a new server?
13. Describe a disaster recovery strategy for a production PostgreSQL application.

> 💡 **Senior Developer Tip:**  
> In production environments, follow the **3-2-1 backup strategy** whenever possible:
>
> - **3 copies** of your data (original + 2 backups)
> - **2 different storage media** (e.g., local disk and cloud storage)
> - **1 off-site copy** (cloud or another data center)
>
> Combine **regular automated backups** with **replication** to achieve both disaster recovery and high availability.
