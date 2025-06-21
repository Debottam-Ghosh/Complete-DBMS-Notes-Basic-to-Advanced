## DDL Commands in SQL (Data Definition Language)
DDL (Data Definition Language) is a subset of SQL used to define and manage database structure or schema — such as creating, altering, and deleting tables and other database objects.

---

## 1. CREATE
Used to create a new table, database, view, or other object.

### 1.A) Create a Database
```bash
CREATE DATABASE Database_Name;
```
or, 

```bash
CREATE DATABASE IF NOT EXISTS Database_Name;
```

### 1.B) Create a Table
```bash
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);
```
#### Example:
```bash
CREATE TABLE Students (
    ID INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT
);
```

---

##  2. ALTER
Used to modify an existing database object like a table.
There are few alter commands in SQL:

```bash
ALTER TABLE table_name
[ADD | DROP | MODIFY] column_name datatype;
```
### 2.A) ADD - To add a new column to the table
```bash
ALTER TABLE table_name
ADD column_name datatype;
```

### 2.B) MODIFY - To change the data type of an existing column
```bash
ALTER TABLE table_name
MODIFY COLUMN column_name datatype;
```

### 2.C) RENAME COLUMN - To rename an existing column
```bash
ALTER TABLE table_name
RENAME COLUMN old_name TO new_name;
```

---

## 3. DROP
Used to delete a table, database permanently.
#### Dropping a Table
```bash
DROP TABLE table_name;
```

#### Dropping the whole Database
```bash
DROP TABLE table_name;
```

**NOTE:** This action is irreversible — it deletes both structure and data.

---

## 4. TRUNCATE
Used to delete all rows from a table without deleting its structure.
```bash
TRUNCATE TABLE table_name;
```

---

## 5. RENAME
Used to rename a table.
```bash
RENAME TABLE old_name TO new_name;
```


