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
INSERT INTO table_name VALUES (value11, value12, ..., value_1n), (value21, value22, ..., value_2n), (value31, value32, ..., value_3n);
```

- All constraints like NOT NULL, UNIQUE, FOREIGN KEY, etc., will be enforced during insert.
