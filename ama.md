# AMA Session Questions and Answers

### Adhikya Edammala: Can we use alias names in WHERE?

No, because WHERE executes before SELECT.
Alias names can be used in ORDER BY, but not usually in WHERE.

---

### Allanki VV Manikanta Sai: What is use of pass?

pass is a null statement in Python.
It is used as a placeholder when no code is written yet.

---

### Arpit Yadav: Explain ACID properties

ACID properties ensure reliable database transactions:

* Atomicity → all or nothing
* Consistency → valid data only
* Isolation → transactions don’t interfere
* Durability → saved permanently after commit

---

### Boorle Sowmya Sri Lakshmi: What is use of CUBE in SQL?

CUBE generates subtotals and grand totals for all column combinations in GROUP BY.
Useful in reports and data analysis.

---

### Injamuri Arun Kumar: What is normalization?

Normalization is the process of organizing data to reduce redundancy and improve consistency.


---

### Kamparapu Lakshman: How to achieve inheritance in Python?

Inheritance is achieved by passing the parent class inside child class brackets.

```python
class Parent:
    pass

class Child(Parent):
    pass
```

---

### M Harivardhan Reddy: Rename a table in SQL

```sql
ALTER TABLE old_table_name
RENAME TO new_table_name;
```

---

### Md Musharaf: Difference between DELETE, TRUNCATE and DROP

| Command  | Removes       | Rollback  | Structure     |
| -------- | ------------- | --------- | ------------- |
| DELETE   | Selected rows | Yes       | Keeps table   |
| TRUNCATE | All rows      | Mostly No | Keeps table   |
| DROP     | Entire table  | No        | Removes table |

---

### Naman Sharma: Use of ORDER BY

ORDER BY is used to sort query results in ascending (ASC) or descending (DESC) order.

---

### Nayunipatruni Harsha Vardhan: Difference between UNION and UNION ALL

| UNION              | UNION ALL        |
| ------------------ | ---------------- |
| Removes duplicates | Keeps duplicates |


---

### Parlapalli Sulochana: What is return type of file.readlines()?

It returns a **list of strings**.
Each element represents one line from the file.

---

### Rongala Vasu: What are higher order functions?

Higher order functions are functions that:

* take another function as argument
* return a function


---

### Rovinpal Udupi: What is view in relation(SQL)?

A view is a virtual table created from a SQL query.
It does not store data permanently.

---

### Tumma Haritha: What is deadlock in SQL?

Deadlock happens when two or more transactions wait for each other forever, blocking execution.

---

### Yash Nitin Raut: Can we remove subqueries with its replacement?

Yes, many subqueries can be replaced using: JOIN
