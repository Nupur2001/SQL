# 🔠 Types of SQL Commands

SQL commands are categorized into five main types based on their functionality:

---

## 📥 1. DML – Data Manipulation Language

Used to manipulate data within existing tables.

| Command  | Description                              | Example Query |
|----------|------------------------------------------|----------------|
| `SELECT` | Retrieves data from a table               | `SELECT * FROM employees;` |
| `INSERT` | Adds new data into a table                | `INSERT INTO employees (id, name, salary) VALUES (1, 'John', 50000);` |
| `UPDATE` | Modifies existing data                    | `UPDATE employees SET salary = 60000 WHERE id = 1;` |
| `DELETE` | Removes data from a table                 | `DELETE FROM employees WHERE id = 1;` |

---

## 🛠️ 2. DDL – Data Definition Language

Used to define and manage database structures.

| Command    | Description                                 | Example Query |
|------------|---------------------------------------------|----------------|
| `CREATE`   | Creates tables, views, indexes, etc.        | `CREATE TABLE employees (id INT, name VARCHAR(50), salary DECIMAL(10,2));` |
| `ALTER`    | Modifies an existing table structure        | `ALTER TABLE employees ADD COLUMN department VARCHAR(50);` |
| `DROP`     | Deletes objects like tables or views        | `DROP TABLE employees;` |
| `TRUNCATE` | Removes all records from a table (faster)   | `TRUNCATE TABLE employees;` |
| `RENAME`   | Renames a database object                   | `RENAME TABLE employees TO staff;` |

---

## 🔒 3. DCL – Data Control Language

Used to control access to data in the database.

| Command   | Description                          | Example Query |
|-----------|--------------------------------------|----------------|
| `GRANT`   | Gives privileges to users            | `GRANT SELECT, INSERT ON employees TO user1;` |
| `REVOKE`  | Removes privileges from users        | `REVOKE INSERT ON employees FROM user1;` |

---

## 🔄 4. TCL – Transaction Control Language

Used to manage transactions in a database.

| Command     | Description                                   | Example Query |
|-------------|-----------------------------------------------|----------------|
| `COMMIT`    | Saves all changes made by the transaction     | `COMMIT;` |
| `ROLLBACK`  | Undoes changes since the last COMMIT          | `ROLLBACK;` |
| `SAVEPOINT` | Sets a savepoint within a transaction         | `SAVEPOINT before_update;` |
| `SET TRANSACTION` | Defines characteristics of a transaction | `SET TRANSACTION READ WRITE;` |

🧠 **Example Workflow:**
```sql
BEGIN;
UPDATE employees SET salary = salary + 5000 WHERE department = 'Sales';
SAVEPOINT before_bonus;
UPDATE employees SET salary = salary + 2000 WHERE department = 'HR';
ROLLBACK TO before_bonus;
COMMIT;


## ⚙️ 5. DQL – Data Query Language

Primarily focused on querying data.

| Command  | Description                     | Example Query |
|----------|---------------------------------|----------------|
| `SELECT` | Used to retrieve data from tables | `SELECT name, salary FROM employees WHERE department = 'HR';` |

> 🔁 **Note:** `SELECT` is sometimes categorized under **DQL**, but some systems also include it under **DML**.

---

## 🧩 Summary

| Category | Full Form | Purpose |
|-----------|------------|----------|
| **DML** | Data Manipulation Language | Work with table data |
| **DDL** | Data Definition Language | Create or modify structures |
| **DCL** | Data Control Language | Control user access |
| **TCL** | Transaction Control Language | Manage transactions |
| **DQL** | Data Query Language | Retrieve data |

---

## 💡 Quick Tip

If you’re learning SQL, start with:

1. `SELECT` → to view data  
2. `INSERT`, `UPDATE`, `DELETE` → to modify data  
3. `CREATE`, `ALTER`, `DROP` → to manage tables  
4. `COMMIT`, `ROLLBACK` → to control transactions  

Then move to permissions with `GRANT` and `REVOKE`.

---

## ✅ Now You Understand

- **DML** = Works *with data*  
- **DDL** = Works *on structure*  
- **DCL** = Controls *who can access*  
- **TCL** = Manages *transactions*  
- **DQL** = *Queries data*


