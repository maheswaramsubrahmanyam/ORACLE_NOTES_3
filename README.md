# ORACLE_NOTES_3


### Question: What is the primary purpose of the Data Definition Language (DDL) in Oracle?

**Correct Answer:**  
**b) Define and modify database structure** ✅

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
