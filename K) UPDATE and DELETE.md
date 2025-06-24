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



