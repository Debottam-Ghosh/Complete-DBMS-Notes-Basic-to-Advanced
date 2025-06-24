#
# Chapter 12: Functions in SQL

<br>
<br>

SQL functions are built-in methods used to perform operations on data such as calculation, formatting, and transformation. They return a single value and are typically used in SELECT, WHERE, ORDER BY, or HAVING clauses.

## Types of SQL Functions
**1. Scalar Functions** – operate on a single value and return a single value
**2. Aggregate Functions** – operate on a group of rows
#
## Scalar Functions
These return a single value based on input. Categories include:
### a) String Functions
| Function             | Description                   | Example                              |
| -------------------- | ----------------------------- | ------------------------------------ |
| `UPPER()`            | Converts to uppercase         | `UPPER(name)` → `'JOHN'`             |
| `LOWER()`            | Converts to lowercase         | `LOWER(city)` → `'delhi'`            |
| `LENGTH()` / `LEN()` | Returns string length         | `LENGTH(name)` → `5`                 |
| `SUBSTRING()`        | Extracts part of a string     | `SUBSTRING(name, 1, 3)` → `'Joh'`    |
| `CONCAT()`           | Joins two or more strings     | `CONCAT(first_name, ' ', last_name)` |
| `TRIM()`             | Removes spaces from both ends | `TRIM('  Hello ')` → `'Hello'`       |
<br>

### b) Date/Time Functions

| Function                     | Description             | Example                                |
| ---------------------------- | ----------------------- | -------------------------------------- |
| `NOW()`                      | Current date and time   | `SELECT NOW();`                        |
| `CURDATE()`                  | Current date            | `SELECT CURDATE();`                    |
| `YEAR()`, `MONTH()`, `DAY()` | Extract parts of a date | `YEAR(dob)` → `1995`                   |
| `DATEDIFF()`                 | Days between two dates  | `DATEDIFF('2025-06-22', '2025-01-01')` |
<br>

### c) Numeric Functions

| Function  | Description         | Example                        |
| --------- | ------------------- | ------------------------------ |
| `ROUND()` | Rounds a number     | `ROUND(123.456, 2)` → `123.46` |
| `CEIL()`  | Rounds up           | `CEIL(4.2)` → `5`              |
| `FLOOR()` | Rounds down         | `FLOOR(4.8)` → `4`             |
| `ABS()`   | Absolute value      | `ABS(-10)` → `10`              |
| `MOD()`   | Modulus (remainder) | `MOD(10, 3)` → `1`             |

#

## Aggregate Functions

Often used with `GROUP BY` to summarize data.
<br>

| Function  | Description                        | Example                              |
| --------- | ---------------------------------- | ------------------------------------ |
| `COUNT()` | Counts rows                        | `SELECT COUNT(*) FROM employees;`    |
| `SUM()`   | Calculates total of numeric column | `SELECT SUM(salary) FROM employees;` |
| `AVG()`   | Calculates average                 | `SELECT AVG(age) FROM students;`     |
| `MIN()`   | Finds minimum value                | `SELECT MIN(price) FROM products;`   |
| `MAX()`   | Finds maximum value                | `SELECT MAX(score) FROM exams;`      |




