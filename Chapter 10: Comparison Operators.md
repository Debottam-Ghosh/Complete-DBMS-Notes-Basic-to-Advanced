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

### Wildcards in SQL
Wildcards are used with the `LIKE` operator in SQL to search for a specific pattern in a column, usually text (strings). They are powerful tools for pattern-based filtering in WHERE clauses.

## Common SQL Wildcards
| Wildcard         | Description                                                         | Example                                    |
| ---------------- | ------------------------------------------------------------------- | ------------------------------------------ |
| `%`              | Matches **zero or more characters**                                 | `WHERE name LIKE 'A%'` (starts with A)     |
| `_`              | Matches **exactly one character**                                   | `WHERE code LIKE 'A_1'` (e.g., A21, AB1)   |

### Examples of Wildcard Usage
```bash
-- Find names starting with 'S'
SELECT * FROM employees
WHERE name LIKE 'S%';

-- Names ending with 'n'
SELECT * FROM students
WHERE name LIKE '%n';

-- Names with 'a' as second letter
SELECT * FROM authors
WHERE name LIKE '_a%';

-- Find items containing 'pen' anywhere
SELECT * FROM products
WHERE name LIKE '%pen%';

-- Find names that are exactly 4 characters long
SELECT * FROM users
WHERE username LIKE '____';
```

#### Wildcards Do Not Work With:
- Numeric data types (unless converted to text).
- Operators other than LIKE (e.g., you can't use % with =).

| Pattern   | Matches                            |
| --------- | ---------------------------------- |
| `'A%'`    | Words starting with A              |
| `'%son'`  | Words ending in "son"              |
| `'__b%'`  | Third character is 'b'             |
| `'____'`  | Exactly 4 characters               |
| `'%a%e%'` | Contains both 'a' and 'e' in order |



