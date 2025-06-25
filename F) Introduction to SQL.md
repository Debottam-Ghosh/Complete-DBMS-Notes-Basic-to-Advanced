#
# Chapter 6: Introduction to SQL
<br>
<br>


## What is SQL?
SQL (Structured Query Language) is a standard language used to communicate with relational databases. It allows users to store, retrieve, manage, and manipulate data efficiently.
<br>
SQL is used with popular databases like MySQL, PostgreSQL, Oracle, SQL Server, and SQLite.

## Why Use SQL?
- To create and modify database structures (tables, views, indexes)
- To insert, update, delete data
- To query (retrieve) specific data using conditions
- To control access to data securely

## Categories of SQL Commands
| Category | Commands                               | Purpose                   |
| -------- | -------------------------------------- | ------------------------- |
| **DDL**  | `CREATE`, `ALTER`, `DROP`, `TRUNCATE`  | Define & manage structure |
| **DML**  | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | Work with data            |
| **DCL**  | `GRANT`, `REVOKE`                      | Control user access       |
| **TCL**  | `COMMIT`, `ROLLBACK`, `SAVEPOINT`      | Manage transactions       |


![image](https://github.com/user-attachments/assets/a0705f00-c7f9-405d-9535-f45523c552f4)


### Good Practice
- Always use `;` at the end of your SQL statements. Not Mandatory but advisable.
- Write the commands in upper case. Again not mandatory. SQL is not case sensitive. Not using upper case will not throw an error but not a good practice.
