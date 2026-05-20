# SQL Theory

# 1. Database Fundamentals

## What is a Database?

A database is an organized collection of data that can be easily accessed, managed, and updated.

Example:

* Student records
* Banking systems
* E-commerce product data

---

## What is DBMS?

DBMS (Database Management System) is software used to manage databases.

Examples:

* MySQL
* PostgreSQL
* Oracle

Example Use Case:

A college uses PostgreSQL to store student marks and attendance.

---

## Types of Databases

### Relational Database

Stores data in tables.

Examples:

* PostgreSQL
* MySQL

Example:

| id | name  | marks |
| -- | ----- | ----- |
| 1  | Rahul | 90    |

### Non-Relational Database (NoSQL)

Stores data in flexible formats like JSON, key-value, documents.

Examples:

* MongoDB

Example JSON Document:

```json
{
  "name": "Rahul",
  "marks": 90
}
```

---

## RDBMS Features

* Table-based structure
* Relationships using keys
* ACID properties
* Structured Query Language (SQL)

Example:

A `students` table connected with a `courses` table using `student_id`.

---

# 2. SQL Fundamentals

## What is SQL?

SQL (Structured Query Language) is used to interact with relational databases.

Used for:

* Creating tables
* Inserting data
* Querying data
* Updating records

Example:

```sql
SELECT * FROM students;
```

---

## SQL Categories

### DDL (Data Definition Language)

* CREATE
* ALTER
* DROP
* TRUNCATE

Example:

```sql
CREATE TABLE students (
    id INT,
    name VARCHAR(50)
);
```

### DML (Data Manipulation Language)

* INSERT
* UPDATE
* DELETE

Example:

```sql
INSERT INTO students VALUES (1, 'Rahul');
```

### DQL (Data Query Language)

* SELECT

Example:

```sql
SELECT name FROM students;
```

### TCL (Transaction Control Language)

* COMMIT
* ROLLBACK
* SAVEPOINT

### DCL (Data Control Language)

* GRANT
* REVOKE

---

# 3. Constraints

## NOT NULL

Column cannot store NULL values.

Example:

```sql
name VARCHAR(50) NOT NULL
```

## UNIQUE

All values must be different.

Example:

```sql
email VARCHAR(100) UNIQUE
```

## PRIMARY KEY

Uniquely identifies each row.

Features:

* Unique
* Not Null
* One per table

Example:

```sql
id INT PRIMARY KEY
```

## FOREIGN KEY

Creates relation between two tables.

Example:

```sql
FOREIGN KEY (dept_id) REFERENCES departments(id)
```

## DEFAULT

Provides default value.

Example:

```sql
status VARCHAR(20) DEFAULT 'active'
```

---

# 4. Keys in SQL

## Candidate Key

Possible keys that can uniquely identify rows.

Example:

* Email
* Aadhaar number

## Primary Key

Chosen candidate key.

Example:

`student_id`

## Alternate Key

Candidate keys not selected as primary.

Example:

If `email` is not selected as primary key.

## Composite Key

Combination of multiple columns.

Example:

```sql
PRIMARY KEY(student_id, course_id)
```

## Foreign Key

Links two tables.

Example:

`dept_id` linking employees and departments.

## Super Key

Set of attributes that uniquely identify rows.

Example:

`(id, email)` together.

---

# 5. Filtering and Sorting

## WHERE Clause

Filters rows.

Example:

```sql
SELECT * FROM students
WHERE marks > 80;
```

## ORDER BY

Sorts results.

Example:

```sql
SELECT * FROM students
ORDER BY marks DESC;
```

### ASC

Ascending order.

### DESC

Descending order.

---

# 6. SQL Operators

## Arithmetic Operators

* ```+```
* ```-```
* ```*```
* ```/```

Example:

```sql
SELECT salary + 5000 FROM employees;
```

## Comparison Operators

* ```=```
* ```!=```
* ```>```
* ```<```
* ```>=```
* ```<=```

Example:

```sql
SELECT * FROM employees
WHERE salary >= 50000;
```

## Logical Operators

* AND
* OR
* NOT

Example:

```sql
SELECT * FROM students
WHERE marks > 80 AND city = 'Delhi';
```

## Special Operators

* IN
* BETWEEN
* LIKE
* IS NULL
* EXISTS

Example:

```sql
SELECT * FROM students
WHERE city IN ('Delhi', 'Mumbai');
```

---

# 7. Pattern Matching

## LIKE Operator

### %

Matches multiple characters.

### _

Matches single character.

Example:

```sql
SELECT * FROM students
WHERE name LIKE 'A%';
```

Starts with A.

Example:

```sql
WHERE name LIKE '_a%'
```

Second character is 'a'.

---

# 8. NULL Handling

## What is NULL?

Represents missing or unknown value.

Important:

* NULL is not zero
* NULL is not empty string

Example:

```sql
SELECT * FROM employees
WHERE bonus IS NULL;
```

---

# 9. Aggregate Functions

## COUNT()

Counts rows.

Example:

```sql
SELECT COUNT(*) FROM students;
```

## SUM()

Adds values.

Example:

```sql
SELECT SUM(salary) FROM employees;
```

## AVG()

Average value.

Example:

```sql
SELECT AVG(marks) FROM students;
```

## MIN()

Minimum value.

## MAX()

Maximum value.

---

# 10. GROUP BY and HAVING

## GROUP BY

Groups rows for aggregation.

Example:

```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department;
```

## HAVING

Filters grouped data.

Example:

```sql
SELECT department, COUNT(*)
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```

Difference:

* WHERE filters rows before grouping
* HAVING filters after grouping

---

# 11. Subqueries

## What is a Subquery?

Query inside another query.

Example:

```sql
SELECT name
FROM students
WHERE marks > (
    SELECT AVG(marks) FROM students
);
```

---

# 12. Set Operations

## UNION

Combines unique rows.

Example:

```sql
SELECT city FROM customers
UNION
SELECT city FROM suppliers;
```

## UNION ALL

Combines all rows including duplicates.

## INTERSECT

Common rows.

Example:

```sql
SELECT city FROM customers
INTERSECT
SELECT city FROM suppliers;
```

---

# 13. Views

## What is a View?

Virtual table based on query.

Example:

```sql
CREATE VIEW top_students AS
SELECT * FROM students
WHERE marks > 90;
```

Advantages:

* Security
* Simplifies complex queries
* Reusability

---

# 14. Transactions

## What is Transaction?

Group of SQL operations executed together.

Example:

Bank money transfer.

---

## ACID Properties

### Atomicity

All or nothing.

Example:

Money deducted and credited together.

### Consistency

Database remains valid.

### Isolation

Transactions do not interfere.

### Durability

Committed data is permanent.

---

## COMMIT

Saves changes.

## ROLLBACK

Undo changes.

## SAVEPOINT

Creates checkpoint.

---

# 15. Indexes

## What is an Index?

Improves query performance.

Example:

Searching a book using index page.

Types:

* Clustered
* Non-clustered
* Composite
* Unique

Advantages:

* Faster SELECT

Disadvantages:

* Slower INSERT/UPDATE/DELETE
* Extra storage

---

# 16. Normalization

## Purpose

Reduce redundancy and improve consistency.

Example:

Separating customer and order tables.

---

## Denormalization

Combining tables for performance.

Example:

Keeping customer name directly in orders table for faster reads.

---

# 17. Joins

## INNER JOIN

Matching rows only.

Example:

```sql
SELECT students.name, departments.dept_name
FROM students
INNER JOIN departments
ON students.dept_id = departments.id;
```

## LEFT JOIN

All left rows + matched right rows.

## RIGHT JOIN

All right rows + matched left rows.

## FULL OUTER JOIN

All rows from both tables.

## CROSS JOIN

A CROSS JOIN returns all possible combinations of rows from two tables.

Example:

3 students × 2 subjects = 6 rows.

## SELF JOIN

Table joined with itself.

Example:

Employee and manager in same table.

---

# 18. Window Functions

## What are Window Functions?

Perform calculations across rows without grouping.

Example:

Ranking employees by salary.

---

## Important Window Functions

### ROW_NUMBER()

Unique row number.

### RANK()

Ranking with gaps.

### DENSE_RANK()

Ranking without gaps.

### NTILE()

Divide rows into groups.

---

## OVER Clause

Defines window partition.

Example:

```sql
SELECT name, salary,
RANK() OVER (ORDER BY salary DESC)
FROM employees;
```

---

# 19. CASE Statements

## CASE Expression

Conditional logic in SQL.

Similar to if-else.

Example:

```sql
SELECT name,
CASE
    WHEN marks >= 90 THEN 'Excellent'
    WHEN marks >= 70 THEN 'Good'
    ELSE 'Average'
END
FROM students;
```

Used in:

* SELECT
* ORDER BY
* GROUP BY

---

# 20. Stored Procedures

## What is Stored Procedure?

Saved SQL program in database.

Example:

Procedure to calculate employee bonus.

Advantages:

* Reusability
* Security
* Better performance

---

# 21. Functions

## Scalar Functions

Return single value.

Example:

```sql
UPPER('rahul')
```

## Table-Valued Functions

Return table.

---

# 22. Sequences and Auto Increment

## AUTO_INCREMENT / SERIAL

Automatically generates IDs.

Example:

```sql
id SERIAL PRIMARY KEY
```

## Sequence

Database object generating numbers.

---

# 23. Temporary Tables

## Temporary Table

Exists temporarily for session.

Example:

```sql
CREATE TEMP TABLE temp_sales AS
SELECT * FROM sales;
```

Uses:

* Intermediate calculations
* Reporting

---

# 24. Locks and Concurrency

## Why Locking?

Prevents data conflicts.

Example:

Two users editing same bank balance.

---

## Types of Locks

### Shared Lock

Read only.

### Exclusive Lock

Read + write protection.

---

## Deadlock

Two transactions waiting on each other.

Prevention:

* Consistent locking order
* Short transactions

---

# 25. Partitioning

## What is Partitioning?

Splits large tables into smaller parts.

Example:

Separate sales data by year.

Types:

* Range partitioning
* List partitioning
* Hash partitioning

---

# 26. SQL Security

## Authentication

Verifies identity.

Example:

Username and password login.

## Authorization

Controls permissions.

Example:

Giving read-only access.

---

## GRANT

Give permission.

Example:

```sql
GRANT SELECT ON students TO user1;
```

## REVOKE

Remove permission.

Example:

```sql
REVOKE SELECT ON students FROM user1;
```

---
