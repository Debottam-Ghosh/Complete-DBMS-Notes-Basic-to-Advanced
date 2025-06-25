#
# Chapter 13: ORDER BY, GROUP BY, HAVING

<br>
<br>

The `ORDER BY` clause is used to **sort** the result set of a query by one or more columns.

<br>

## Syntax
```bash
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC | DESC], column2 [ASC | DESC];
```
<br>

Where,
- ASC = Ascending order (default)
- DESC = Descending order

<br>

## Examples
**Sort employees by name in ascending order**
```bash
SELECT * FROM employees
ORDER BY name ASC;
```
<br>

**Sort products by price in descending order**
```bash
SELECT * FROM products
ORDER BY price DESC;
```
<br>

**Sort students by grade (desc) and then by name (asc)**
```bash
SELECT * FROM students
ORDER BY grade DESC, name ASC;
```

#

## Important
1. You can sort by:
  - One or more columns
  - Column aliases (e.g., SELECT salary * 1.10 AS increased_salary)
  - Column positions (e.g., ORDER BY 2 refers to the second selected column), Although it's not a very good practice as it can be confusing sometimes.
2. ORDER BY is always the last clause in a SELECT statement (after WHERE, GROUP BY, and HAVING)
3. Works with both text (A–Z, Z–A) and numbers (0–9, 9–0)

#

### Sorting with Expressions
##### Sort employees by yearly salary (monthly_salary * 12)
```bash
SELECT name, monthly_salary
FROM employees
ORDER BY monthly_salary * 12 DESC;
```
#

## ORDER BY with `LIMIT`
Use ORDER BY along with LIMIT (in MySQL/PostgreSQL) to get top N records:
**Top 5 highest-paid employees**
```bash
SELECT name, salary
FROM employees
ORDER BY salary DESC
LIMIT 5;
```





