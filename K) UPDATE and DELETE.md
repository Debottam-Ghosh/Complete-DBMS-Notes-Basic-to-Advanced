#
# Chapter 11: UPDATE and DELETE

<br>
<br>

## UPDATE Statement in SQL
The `UPDATE` statement is used to modify existing records in a table.
<br>

### Syntax
```bash
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```
<br>

### Important
- Always use a WHERE clause to avoid updating all records in the table.
- You can update one or more columns at a time.
<br>

### Example
**Increase salary of IT department employees by 10%**
```bash
UPDATE employees
SET salary = salary * 1.10
WHERE department = 'IT';
```
<br>

**Change city of a specific user**
```bash
UPDATE users
SET city = 'Mumbai'
WHERE user_id = 101;
```

---

## DELETE Statement in SQL
The `DELETE` statement is used to remove rows from a table.
<br>

### Syntax
```bash
DELETE FROM table_name
WHERE condition;
```
<br>

### Important
- If you omit the WHERE clause, all rows in the table will be deleted.
- Unlike TRUNCATE, DELETE can be used with conditions and can be rolled back (if transactions are enabled).
<br>

### Example
**Delete users who have not logged in for over 1 year**
```bash
DELETE FROM users
WHERE last_login < '2024-06-01';
```
<br>

**Remove products that are discontinued**
```bash
DELETE FROM products
WHERE status = 'Discontinued';
```
##

## Comparison Table: UPDATE vs DELETE
| Feature       | `UPDATE`                              | `DELETE`                     |
| ------------- | ------------------------------------- | ---------------------------- |
| Purpose       | Modify existing records               | Remove existing records      |
| Syntax        | `UPDATE table SET col=value WHERE...` | `DELETE FROM table WHERE...` |
| WHERE clause  | Optional, but recommended             | Optional, but recommended    |
| Without WHERE | Updates all rows                      | Deletes all rows             |
| Affects       | Specific columns                      | Entire row(s)                |

