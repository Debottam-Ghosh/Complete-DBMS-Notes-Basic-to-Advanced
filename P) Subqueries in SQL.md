#
# Chapter 16: Subqueries in SQL
<br>
<br>

A **subquery** (also called an inner query or nested query) is a query nested inside another query.<br>
It is used to filter, calculate, or retrieve values used by the main query. <br>
It also allows breaking complex logic into smaller, manageable queries.

<br>

## General Syntax
```bash
SELECT column1
FROM table1
WHERE column2 = (SELECT column2 FROM table2 WHERE condition);
```
<br>

## Types of Subqueries
### 1. Single-row Subquery
Returns one value (one row, one column)

```bash
SELECT name
FROM employees
WHERE salary = (SELECT MAX(salary) FROM employees);
```
<br>

### 2. Multiple-row Subquery
Returns multiple rows, used with IN, ANY, or ALL

```bash
SELECT name
FROM employees
WHERE department_id IN (SELECT department_id FROM departments WHERE location = 'Mumbai');
```
<br>

### 3. Multiple-column Subquery
Returns multiple columns; used in IN, EXISTS, or in JOIN-like conditions

```bash
SELECT name
FROM employees
WHERE (department_id, job_id) IN
      (SELECT department_id, job_id FROM job_postings);
```
<br>

### 4. Correlated Subquery
- Refers to a column from the outer query
- Evaluated for each row of the outer query

```bash
SELECT e.name
FROM employees e
WHERE salary > (
    SELECT AVG(salary)
    FROM employees
    WHERE department_id = e.department_id
);
```
<br>

### 5. Subquery in FROM Clause (Derived Table)
Treated like a temporary table in the main query

```bash
SELECT department, avg_salary
FROM (
    SELECT department, AVG(salary) AS avg_salary
    FROM employees
    GROUP BY department
) AS dept_avg
WHERE avg_salary > 60000;
```

<br>

### 6. Subquery in SELECT Clause
Used to compute values directly in the SELECT list

```bash
SELECT name,
       (SELECT department_name FROM departments WHERE departments.id = employees.department_id) AS dept_name
FROM employees;
```
