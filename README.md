# ORACLE_NOTES_3


### Question: What is the primary purpose of the Data Definition Language (DDL) in Oracle?

**Correct Answer:**  
**b) Define and modify database structure** 

---

### Detailed Answer (10 Marks)

#### 1. Definition
- Data Definition Language (DDL) is a subset of SQL used to **define, create, alter, and remove database objects**.  
- It deals with the **structure of the database** rather than the data stored inside the tables.  
- Examples of database objects include **tables, indexes, views, sequences, and schemas**.

#### 2. Purpose of DDL
- **Define Structure**: Create new tables, indexes, views, and other objects.  
- **Modify Structure**: Alter existing tables or objects to add, delete, or change columns or constraints.  
- **Delete Objects**: Remove objects permanently when no longer needed.  
- **Enforce Integrity**: Define primary keys, foreign keys, and unique constraints to maintain data integrity.  

#### 3. Key DDL Commands
| Command | Purpose |
|---------|---------|
| CREATE  | Creates a new database object (table, view, index, etc.) |
| ALTER   | Modifies an existing object structure |
| DROP    | Deletes a database object permanently |
| TRUNCATE | Removes all rows from a table but keeps its structure |
| RENAME  | Renames an existing object |

#### 4. Syntax Examples
```sql
-- Creating a table
CREATE TABLE Employee (
   emp_id NUMBER PRIMARY KEY,
   emp_name VARCHAR2(50),
   salary NUMBER(10,2)
);

-- Altering a table to add a column
ALTER TABLE Employee ADD (email VARCHAR2(100));

-- Dropping a table
DROP TABLE Employee;
````

#### 5. Explanation

* DDL **does not manipulate data directly** (that is the job of DML).
* Any changes made by DDL commands are **auto-committed**, meaning they are **permanent**.
* DDL is essential for **database design, structure management, and maintaining integrity**.
* It forms the **foundation for any relational database** because without properly defined structures, storing and retrieving data efficiently is impossible.

#### 6. Conclusion

* The **primary purpose of DDL** is to **define and modify the database structure**, ensuring the database is **well-organized, secure, and consistent**.
* In Oracle SQL, understanding DDL is crucial for **designing scalable and maintainable databases**.



---

### Question: Which SQL function is used to convert data from one type to another?

**Correct Answer:**  
**d) Conversion function** 

---

### Detailed Answer (10 Marks)

#### 1. Definition
- Conversion functions in SQL are used to **change the data type of a value** from one type to another.  
- They are essential when combining or comparing different types of data in queries, calculations, or reports.  
- Commonly used in Oracle SQL to **ensure type compatibility**.

#### 2. Purpose of Conversion Functions
- Convert **numbers to strings**, **strings to numbers**, **dates to strings**, etc.  
- Help prevent **type mismatch errors** in SQL statements.  
- Enable **formatting of data** for reporting or calculations.  

#### 3. Common Oracle Conversion Functions
| Function | Description |
|----------|-------------|
| TO_CHAR  | Converts a number or date to a string |
| TO_NUMBER | Converts a string to a numeric value |
| TO_DATE  | Converts a string to a date value |
| CAST     | Converts data from one type to another using ANSI standard syntax |

#### 4. Syntax & Examples
```sql
-- Convert number to string
SELECT TO_CHAR(12345) FROM dual;

-- Convert string to number
SELECT TO_NUMBER('12345') + 10 FROM dual;

-- Convert string to date
SELECT TO_DATE('27-SEP-2025','DD-MON-YYYY') FROM dual;

-- Using CAST
SELECT CAST(salary AS VARCHAR2(10)) FROM Employee;
````

#### 5. Explanation

* **TO_CHAR** is useful when formatting numbers or dates for display.
* **TO_NUMBER** allows arithmetic operations on string inputs.
* **TO_DATE** ensures strings representing dates can be used in date calculations.
* **CAST** is flexible and follows ANSI SQL standards.

#### 6. Conclusion

* The primary function to **convert data types** in Oracle SQL is the **Conversion Function**.
* Proper use ensures **data consistency, prevents errors, and supports accurate calculations and reporting**.


---

### Question: Which constraint ensures that a foreign key value matches a primary key value?

**Correct Answer:**  
**c) Referential constraint** 

---

### Detailed Answer (10 Marks)

#### 1. Definition
- A **referential constraint** (or foreign key constraint) ensures **data integrity between two tables**.  
- It guarantees that the **value in a foreign key column matches a primary key value** in the referenced table.  
- Helps maintain **consistency in relational databases**.  

#### 2. Purpose of Referential Constraints
- Enforces **relationships between tables**.  
- Prevents **orphan records** (foreign key pointing to a non-existent primary key).  
- Supports **relational integrity** in a database.  
- Ensures that **changes in parent table** are properly handled in child tables.  

#### 3. Syntax
```sql
-- Creating a table with a foreign key
CREATE TABLE Department (
    dept_id NUMBER PRIMARY KEY,
    dept_name VARCHAR2(50)
);

CREATE TABLE Employee (
    emp_id NUMBER PRIMARY KEY,
    emp_name VARCHAR2(50),
    dept_id NUMBER,
    CONSTRAINT fk_dept FOREIGN KEY (dept_id)
        REFERENCES Department(dept_id)
        ON DELETE CASCADE
);
````

#### 4. Explanation

* `fk_dept` is the **referential constraint** linking `Employee.dept_id` to `Department.dept_id`.
* If you try to insert an employee with a `dept_id` that doesn’t exist in `Department`, Oracle will **reject the operation**.
* `ON DELETE CASCADE` ensures that deleting a department automatically deletes related employees.
* Referential constraints maintain **logical consistency** across relational tables.

#### 5. Types of Referential Actions

* **CASCADE** → Automatically updates or deletes dependent rows.
* **SET NULL** → Sets foreign key values to NULL if parent row is deleted.
* **NO ACTION / RESTRICT** → Prevents deletion or update if dependent rows exist.

#### 6. Conclusion

* The **referential constraint** ensures **foreign key values match primary key values**, maintaining **referential integrity** in the database.
* It is essential for designing **reliable and consistent relational databases** in Oracle SQL.



---
