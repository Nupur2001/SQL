#  SQL Cheat Sheet

## 🗂️ 1. Data Definition Language (DDL)

```sql
-- Create a table
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);

-- Alter a table
ALTER TABLE table_name ADD column_name datatype;
ALTER TABLE table_name DROP COLUMN column_name;

-- Drop a table
DROP TABLE table_name;
```

---

## 📥 2. Data Manipulation Language (DML)

```sql
-- Insert data
INSERT INTO table_name (column1, column2) VALUES (value1, value2);

-- Update data
UPDATE table_name
SET column1 = value1
WHERE condition;

-- Delete data
DELETE FROM table_name
WHERE condition;
```

---

## 📊 3. Data Query Language (DQL)

```sql
-- Select specific columns
SELECT column1, column2 FROM table_name;

-- Select all columns
SELECT * FROM table_name;

-- With conditions
SELECT * FROM table_name WHERE condition;

-- Sorting results
SELECT * FROM table_name ORDER BY column1 ASC;
SELECT * FROM table_name ORDER BY column1 DESC;

-- Limit results
SELECT * FROM table_name LIMIT 10;

-- Distinct values
SELECT DISTINCT column1 FROM table_name;
```

---

## 🔗 4. Joins

```sql
-- INNER JOIN
SELECT * FROM table1
INNER JOIN table2 ON table1.id = table2.id;

-- LEFT JOIN
SELECT * FROM table1
LEFT JOIN table2 ON table1.id = table2.id;

-- RIGHT JOIN
SELECT * FROM table1
RIGHT JOIN table2 ON table1.id = table2.id;

-- FULL OUTER JOIN
SELECT * FROM table1
FULL OUTER JOIN table2 ON table1.id = table2.id;
```

---

## 🧠 5. Aggregate Functions

```sql
-- Count
SELECT COUNT(*) FROM table_name;

-- Sum
SELECT SUM(column_name) FROM table_name;

-- Average
SELECT AVG(column_name) FROM table_name;

-- Min and Max
SELECT MIN(column_name), MAX(column_name) FROM table_name;

-- Group By
SELECT column, COUNT(*) 
FROM table_name
GROUP BY column;

-- Having
SELECT column, COUNT(*) 
FROM table_name
GROUP BY column
HAVING COUNT(*) > 1;
```

---

## 🧾 6. Subqueries & Aliases

```sql
-- Subquery in SELECT
SELECT name, (SELECT MAX(score) FROM scores) AS max_score FROM students;

-- Subquery in WHERE
SELECT * FROM employees 
WHERE department_id IN (SELECT id FROM departments WHERE location = 'New York');

-- Aliases
SELECT first_name AS name FROM employees;
```

---

## ⚙️ 7. Constraints

```sql
-- Primary Key
CREATE TABLE table_name (
    id INT PRIMARY KEY,
    name VARCHAR(100)
);

-- Foreign Key
CREATE TABLE orders (
    order_id INT,
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);

-- Unique
CREATE TABLE users (
    username VARCHAR(50) UNIQUE
);

-- Not Null
CREATE TABLE products (
    name VARCHAR(100) NOT NULL
);
```

---

## 🔐 8. User Access (Optional for Admins)

```sql
-- Create user
CREATE USER 'username'@'host' IDENTIFIED BY 'password';

-- Grant privileges
GRANT ALL PRIVILEGES ON database.* TO 'username'@'host';

-- Revoke privileges
REVOKE ALL PRIVILEGES ON database.* FROM 'username'@'host';
```

---

## 🧹 9. Useful Clauses & Keywords

| Clause     | Description                          |
|------------|--------------------------------------|
| `WHERE`    | Filter rows                          |
| `ORDER BY` | Sort rows                            |
| `GROUP BY` | Aggregate rows                       |
| `HAVING`   | Filter groups                        |
| `LIMIT`    | Limit number of results              |
| `LIKE`     | Pattern matching (`_` or `%`)        |
| `IN`       | Match any value in a list            |
| `BETWEEN`  | Range filtering                      |
| `IS NULL`  | Check for NULL values                |

---

> ✅ **Tip**: Practice with an online SQL editor like [SQLFiddle](https://sqlfiddle.com) or [SQLiteOnline](https://sqliteonline.com).
