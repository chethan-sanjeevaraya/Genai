# INTRODUCTION TO SQL (Structured Query Language)

---

## 1. Introduction

SQL (Structured Query Language) is used to store, manipulate, and retrieve data from databases.

---

## 2. History of SQL

- Developed in 1970s by IBM (Raymond Boyce & Donald Chamberlin)
- Originally called SEQUEL
- Based on Edgar F. Codd’s relational model
- First used in IBM System R
- Oracle released first commercial SQL (1979)
- Standardized by ANSI & ISO

---

## 3. Database Basics

### What is a Database?
A database is an organized collection of data.

### Relational Database
- Data stored in tables (rows & columns)
- Examples: MySQL, Oracle, SQL Server

---

## 4. CRUD Operations

| Operation | SQL |
|----------|-----|
| Create | INSERT |
| Read | SELECT |
| Update | UPDATE |
| Delete | DELETE |

---

## 5. SQL Queries

### SELECT
```sql
SELECT * FROM customer;
```

### SELECT DISTINCT
```sql
SELECT DISTINCT first_name FROM customer;
```

### WHERE
```sql
SELECT * FROM customer WHERE first_name = 'John';
```

### AND / OR / NOT
```sql
SELECT * FROM customer WHERE first_name='John' AND city='NY';
```

### ORDER BY
```sql
SELECT * FROM customer ORDER BY first_name ASC;
```

### LIMIT (MySQL)
```sql
SELECT * FROM customer LIMIT 10;
```

---

## 6. Aggregate Functions

```sql
SELECT MIN(id) FROM customer;
SELECT MAX(id) FROM customer;
SELECT COUNT(*) FROM customer;
SELECT AVG(id) FROM customer;
SELECT SUM(id) FROM customer;
```

---

## 7. LIKE Operator

```sql
SELECT * FROM customer WHERE name LIKE 'A%';
```

Patterns:
- % = multiple characters
- _ = single character

---

## 8. IN / BETWEEN

```sql
SELECT * FROM customer WHERE id IN (1,2,3);
SELECT * FROM customer WHERE id BETWEEN 1 AND 10;
```

---

## 9. GROUP BY & HAVING

```sql
SELECT COUNT(id), city
FROM customer
GROUP BY city;

SELECT COUNT(id), city
FROM customer
GROUP BY city
HAVING COUNT(id) > 2;
```

---

## 10. JOINS

### INNER JOIN
```sql
SELECT *
FROM A
INNER JOIN B ON A.id = B.id;
```

### LEFT JOIN
```sql
SELECT *
FROM A
LEFT JOIN B ON A.id = B.id;
```

### RIGHT JOIN
```sql
SELECT *
FROM A
RIGHT JOIN B ON A.id = B.id;
```

---

## 11. DATABASE OPERATIONS

### CREATE DATABASE
```sql
CREATE DATABASE testdb;
```

### DROP DATABASE
```sql
DROP DATABASE testdb;
```

---

## 12. TABLE OPERATIONS

### CREATE TABLE
```sql
CREATE TABLE customer(
 id INT,
 name VARCHAR(50)
);
```

### INSERT
```sql
INSERT INTO customer VALUES (1,'John');
```

### UPDATE
```sql
UPDATE customer SET name='Mike' WHERE id=1;
```

### DELETE
```sql
DELETE FROM customer WHERE id=1;
```

---

## 13. ALTER TABLE

```sql
ALTER TABLE customer ADD email VARCHAR(50);
ALTER TABLE customer DROP COLUMN email;
```

---

## 14. CONSTRAINTS

### NOT NULL
```sql
name VARCHAR(50) NOT NULL
```

### UNIQUE
```sql
UNIQUE(id)
```

### PRIMARY KEY
```sql
PRIMARY KEY(id)
```

### FOREIGN KEY
```sql
FOREIGN KEY (id) REFERENCES table(id)
```

### CHECK
```sql
CHECK (age >= 18)
```

### DEFAULT
```sql
city VARCHAR(50) DEFAULT 'India'
```

---

## 15. INDEX

```sql
CREATE INDEX idx_name ON customer(name);
```

---

## 16. VIEWS

```sql
CREATE VIEW v_customer AS
SELECT name FROM customer;
```

---

## 17. STORED PROCEDURE

```sql
CREATE PROCEDURE myProc
AS
SELECT * FROM customer;
```

---

## 18. ADVANCED TOPICS

- IF / ELSE
- CASE
- LOOPS
- CURSOR

---

## END
