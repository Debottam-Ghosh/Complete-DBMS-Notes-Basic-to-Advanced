#
# Chapter 10: Comparison Operators

<br>
<br>

Comparison operators are used in SQL to compare two expressions. These are most commonly used in the `WHERE` clause to filter records based on specific conditions.

## `List of Comparison Operators`
| Operator      | Description                    | Example                               |
| ------------- | ------------------------------ | ------------------------------------- |
| `=`           | Equal to                       | `WHERE age = 25`                      |
| `!=` or `<>`  | Not equal to                   | `WHERE city != 'Delhi'`               |
| `>`           | Greater than                   | `WHERE salary > 50000`                |
| `<`           | Less than                      | `WHERE age < 30`                      |
| `>=`          | Greater than or equal to       | `WHERE marks >= 40`                   |
| `<=`          | Less than or equal to          | `WHERE experience <= 2`               |
| `BETWEEN`     | Within a range (inclusive)     | `WHERE age BETWEEN 20 AND 30`         |
| `NOT BETWEEN` | Outside a range                | `WHERE price NOT BETWEEN 100 AND 500` |
| `IN`          | Match any value in a list      | `WHERE country IN ('India', 'USA')`   |
| `NOT IN`      | Exclude values in a list       | `WHERE dept NOT IN ('HR', 'Sales')`   |
| `LIKE`        | Pattern matching (`for strings`) | `WHERE name LIKE 'A%'`                |
| `NOT LIKE`    | Not matching a pattern         | `WHERE email NOT LIKE '%.edu'`        |
| `IS NULL`     | Checks for NULL values         | `WHERE address IS NULL`               |
| `IS NOT NULL` | Checks non-NULL values         | `WHERE phone IS NOT NULL`             |


### Important Points
- Use `=` for exact match; use `LIKE` for partial or pattern matching.
- Null values must be compared using `IS NULL` or `IS NOT NULL`, not with `=` or `!=`.
- Use `IN`/`NOT IN` for multiple value checks in a clean way.
- `BETWEEN` is inclusive of both lower and upper bounds.

### Example Queries
```bash
SELECT * FROM employees
WHERE age >= 30 AND department = 'IT';

SELECT * FROM products
WHERE price BETWEEN 100 AND 200;

SELECT * FROM users
WHERE city IN ('Kolkata', 'Mumbai');
```

### Wildcards in SQL
Wildcards are used with the `LIKE` operator in SQL to search for a specific pattern in a column, usually text (strings). They are powerful tools for pattern-based filtering in WHERE clauses.

## Common SQL Wildcards
| Wildcard         | Description                                                         | Example                                    |
| ---------------- | ------------------------------------------------------------------- | ------------------------------------------ |
| `%`              | Matches **zero or more characters**                                 | `WHERE name LIKE 'A%'` (starts with A)     |
| `_`              | Matches **exactly one character**                                   | `WHERE code LIKE 'A_1'` (e.g., A21, AB1)   |

### Examples of Wildcard Usage
**Find names starting with 'S'**
```bash
SELECT * FROM employees
WHERE name LIKE 'S%';
```
<br>

**Names ending with 'n'**
```
SELECT * FROM students
WHERE name LIKE '%n';
```
<br>

**Names with 'a' as second letter**
```bash
SELECT * FROM authors
WHERE name LIKE '_a%';
```
<br>

**Find items containing 'pen' anywhere**
```bash
SELECT * FROM products
WHERE name LIKE '%pen%';
```
<br>

**Find names that are exactly 4 characters long**
```bash
SELECT * FROM users
WHERE username LIKE '____';
```

#### Wildcards Do Not Work With:
- Numeric data types (unless converted to text).
- Operators other than LIKE (e.g., you can't use % with =)

<br>

| Pattern   | Matches                            |
| --------- | ---------------------------------- |
| `'A%'`    | Words starting with A              |
| `'%son'`  | Words ending in "son"              |
| `'__b%'`  | Third character is 'b'             |
| `'____'`  | Exactly 4 characters               |
| `'%a%e%'` | Contains both 'a' and 'e' in order |

#

## Advanced Examples Using Comparison Operators
```bash
# 1. Find IT employees aged 30 or above, whose email ends with '.com' and have a non-null phone number 
SELECT * FROM employees
WHERE age >= 30
  AND department = 'IT'
  AND email LIKE '%.com'
  AND phone IS NOT NULL;

-- 2. Get all products priced outside the 100 to 200 range and not made in 'China' or 'Bangladesh'
SELECT * FROM products
WHERE price NOT BETWEEN 100 AND 200
  AND country_of_origin NOT IN ('China', 'Bangladesh');

-- 3. Retrieve users from Kolkata or Mumbai whose name starts with 'S' and who are not students
SELECT * FROM users
WHERE city IN ('Kolkata', 'Mumbai')
  AND name LIKE 'S%'
  AND profession != 'Student';

-- 4. List customers whose age is between 18 and 60, email does not end with '.edu', and address is provided
SELECT * FROM customers
WHERE age BETWEEN 18 AND 60
  AND email NOT LIKE '%.edu'
  AND address IS NOT NULL;

-- 5. Fetch employees who either work in HR or Sales, earn more than ₹50,000, and are not located in Delhi
SELECT * FROM employees
WHERE department IN ('HR', 'Sales')
  AND salary > 50000
  AND city <> 'Delhi';

-- 6. Show records where employee code has exactly 6 characters and starts with 'A'
SELECT * FROM employees
WHERE emp_code LIKE 'A_____'  -- A followed by 5 characters

-- 7. Find products with null descriptions and cost less than or equal to 100
SELECT * FROM products
WHERE description IS NULL
  AND price <= 100;
```




