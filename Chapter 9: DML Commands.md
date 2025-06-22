**DML (Data Manipulation Language)** commands are used to manipulate data stored in relational database tables. These commands do not affect the structure of the table — they only affect the rows (records) inside it.

<br>

## DML vs. DDL
| Feature            | DDL (Data Definition Language) | DML (Data Manipulation Language)       |
| ------------------ | ------------------------------ | -------------------------------------- |
| Affects structure? | ✅ Yes                          | ❌ No                                   |
| Affects data?      | ❌ No                           | ✅ Yes                                  |
| Examples           | `CREATE`, `ALTER`, `DROP`      | `SELECT`, `INSERT`, `UPDATE`, `DELETE` |

<br>

## 1. INSERT
This command in SQL is used to add new rows (records) into a table in a database.

<br>

### Basic Syntax
```bash
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

- Column names are optional if values for ALL columns are provided in the SAME ORDER as the table’s structure.
```bash
INSERT INTO table_name VALUES (value1, value2, ..., value_n);
```

- You can insert one row at a time or multiple rows using a single statement.
```bash
INSERT INTO table_name VALUES (value11,...,value_1n), (value21,...,value_2n), (value31,...,value_3n);
```

- All constraints like NOT NULL, UNIQUE, FOREIGN KEY, etc., will be enforced during insert.

---

## 2. SELECT
The SELECT command is used to retrieve data from one or more tables in a database.

### Syntax:
```bash
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

### 2.A) All Columns
```bash
SELECT * FROM Students;
```

 ### 2.B) Filter Some Columns
 ```
SELECT Roll_No,Name,Gender FROM Students;
```

### 2.C) Changing Name of Columns
```bash
SELECT Student_Name as Name, Gender as SEX FROM Students;
```
```bash
SELECT Physics_Score + Math_Score + Chemistry_Score as Science_Score FROM Students;
```

### 2.D) Finding Distict Values of a Column
```bash
SELECT DISTINCT Gender FROM Students;
```
You will get the distinct values only. Like: (Male, Female) or (Male, Female, Others)
