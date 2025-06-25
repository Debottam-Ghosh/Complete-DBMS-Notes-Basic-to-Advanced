#
# Chapter 15: JOINS

<br>
<br>

In SQL, JOINs are used to **combine rows from two or more tables** based on a related column between them (usually foreign key relationships).

<br>

## Why Use JOINs?
To retrieve related data stored in different tables. For example:
- Get customer names from customers table along with their orders from orders table.
- Merge employee and department data.

<br>

## Basic Syntax
```bash
SELECT columns
FROM table1
JOIN table2
ON table1.common_column = table2.common_column;
```
You can replace `JOIN` with specific types like `INNER JOIN`, `LEFT JOIN`, etc.

## Types of JOINs in SQL
![image](https://github.com/user-attachments/assets/2cf33504-2230-4cf0-8770-d231b78a7934)

### INNER JOIN
- Returns only matching rows between both tables.
- Excludes non-match
#### Syntax:
```bash
SELECT a.name, b.order_id
FROM customers a
INNER JOIN orders b
ON a.customer_id = b.customer_id;
```
<br>

### LEFT JOIN / LEFT OUTER JOIN
- Returns all rows from the left table, and matching rows from the right table.
- If no match is found, returns NULL for right-side columns.
#### Syntax:
```bash
SELECT a.name, b.order_id
FROM customers a
LEFT JOIN orders b
ON a.customer_id = b.customer_id;
```

<br>

### RIGHT JOIN / RIGHT OUTER JOIN
- Opposite of LEFT JOIN.
- Returns all rows from the right table, and matching rows from the left.
#### Syntax:
```bash
SELECT a.name, b.order_id
FROM customers a
RIGHT JOIN orders b
ON a.customer_id = b.customer_id;
```

<br>

### FULL OUTER JOIN
- Returns all rows from both tables.
- Non-matching rows have NULLs in place of missing data.
#### Syntax:
```bash
SELECT a.name, b.order_id
FROM customers a
FULL OUTER JOIN orders b
ON a.customer_id = b.customer_id;
```

<br>

### CROSS JOIN
- Returns Cartesian product: all combinations of rows from both tables.
- Use carefully with large tables!
#### Syntax:
```bash
SELECT *
FROM products
CROSS JOIN colors;
```

<br>

### SELF JOIN
- A table is joined to itself, useful for hierarchical or comparative queries.

####  Syntax:
```bash
SELECT a.employee_name, b.manager_name
FROM employees a
JOIN employees b
ON a.manager_id = b.employee_id;
```

#

## JOIN vs UNION
| Feature   | JOIN                            | UNION                         |
| --------- | ------------------------------- | ----------------------------- |
| Combines  | Rows **horizontally** (columns) | Rows **vertically** (records) |
| Condition | Uses `ON` condition             | Uses similar structure        |
| Use case  | Related tables                  | Similar tables (same schema)  |



