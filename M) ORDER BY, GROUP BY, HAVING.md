#
# Chapter 13: ORDER BY, GROUP BY, HAVING

<br>
<br>

# ORDER BY Clause in SQL

The `ORDER BY` clause is used to **sort** the result set of a query by one or more columns.

<br>

## Syntax
```bash
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC | DESC], column2 [ASC | DESC];
```
Where,
- ASC = Ascending order (default)
- DESC = Descending order

<br>

## Examples
#### Sort employees by name in ascending order
```bash
SELECT * FROM employees
ORDER BY name ASC;
```
#### Sort products by price in descending order
```bash
SELECT * FROM products
ORDER BY price DESC;
```
#### Sort students by grade (desc) and then by name (asc)
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
#### Sort employees by yearly salary (monthly_salary * 12)
```bash
SELECT name, monthly_salary
FROM employees
ORDER BY monthly_salary * 12 DESC;
```
#

## ORDER BY with `LIMIT`
Use ORDER BY along with LIMIT (in MySQL/PostgreSQL) to get top N records:
#### Top 5 highest-paid employees
```bash
SELECT name, salary
FROM employees
ORDER BY salary DESC
LIMIT 5;
```
<br>

We Can Pass Two Values to LIMIT in SQL to get records between a certain range:
```bash
SELECT name, salary
FROM employees
ORDER BY salary DESC
LIMIT 2,3;
```
This returns the 3rd, 4th, and 5th highest salaries from the employees table.
<br>

**Basic Syntax:**
`LIMIT m`: Returns first `m` rows from the top
`LIMIT m, n`: Skips the first `m` rows and then returns next `n` rows after skipping 


---

# GROUP BY Clause in SQL
The `GROUP BY` clause is used to **group rows** that have the same values in specified columns and apply aggregate functions (like COUNT(), SUM(), etc.) to **each group**.

## Syntax
```bash
SELECT column1, AGG_FUNC(column2)
FROM table_name
GROUP BY column1;
```
- AGG_FUNC = Aggregate functions like COUNT(), SUM(), AVG(), MAX(), MIN()

#

## Examples

#### 1. Count the number of employees in each department
```bash
SELECT department, COUNT(*) AS total_employees
FROM employees
GROUP BY department;
```
#### 2. Total sales amount per customer
```bash
SELECT customer_id, SUM(amount) AS total_spent
FROM sales
GROUP BY customer_id;
```
#### 3. Average marks scored by each student
```bash
SELECT student_id, AVG(marks) AS average_marks
FROM exam_results
GROUP BY student_id;
```

#

## Common Mistakes
| Mistake                                                                      | Correction                                      |
| ---------------------------------------------------------------------------- | ----------------------------------------------- |
| Using columns in `SELECT` not in `GROUP BY` or aggregate functions           | Only include grouped columns or use aggregation |
| Placing `GROUP BY` before `WHERE`                                            | `GROUP BY` should come **after** `WHERE`        |
| Using `GROUP BY` without aggregates (unless intentionally grouping raw rows) | Use at least one aggregate function             |

<br>

## GROUP BY with Multiple Columns
You can group by more than one column:
#### Count employees by department and gender
```bash
SELECT department, gender, COUNT(*) AS count
FROM employees
GROUP BY department, gender;
```

---

# HAVING Clause in SQL
The HAVING` clause is used to **filter the results** of a GROUP BY query, similar to how WHERE filters individual rows **before grouping**.

<br>

## Syntax
```bash
SELECT column1, AGG_FUNC(column2)
FROM table_name
GROUP BY column1
HAVING condition;
```

<br>

## Examples
#### 1. Show departments with more than 5 employees
```bash
SELECT department, COUNT(*) AS total_employees
FROM employees
GROUP BY department
HAVING COUNT(*) > 5;
```

#### 2. Find customers who spent more than ₹10,000
```bash
SELECT customer_id, SUM(amount) AS total_spent
FROM sales
GROUP BY customer_id
HAVING SUM(amount) > 10000;
```

#### 3. Display products with an average rating less than 3
```bash
SELECT product_id, AVG(rating) AS avg_rating
FROM reviews
GROUP BY product_id
HAVING AVG(rating) < 3;
```

<br>

## Where vs Having
| Feature       | `WHERE`                      | `HAVING`                        |
| ------------- | ---------------------------- | ------------------------------- |
| Used On       | Individual rows              | Grouped data (after `GROUP BY`) |
| Aggregate Use | ❌ Cannot use aggregate funcs | ✅ Can use aggregate funcs       |
| Order         | Comes before `GROUP BY`      | Comes after `GROUP BY`          |

<br>

## Important
- Use HAVING only when you're filtering aggregated results.
- You can use both WHERE and HAVING in the same query.
- If you're not using GROUP BY, HAVING behaves like WHERE but with aggregates.


---

# Some Real World Complex Queries

### 1. Department-wise Average Salary of Employees Hired After 2018
#### Requirements:
- Filter employees hired after 2018 (WHERE)
- Group them by department (GROUP BY)
- Show only departments where average salary > ₹60,000 (HAVING)
- Order the result by average salary descending (ORDER BY)
```bash
SELECT department, AVG(salary) AS avg_salary
FROM employees
WHERE hire_date > '2018-01-01'
GROUP BY department
HAVING AVG(salary) > 60000
ORDER BY avg_salary DESC;
```


#

### 2. Top 3 Customers by Total Purchase Value (₹)
#### Requirements:
- Group sales by customer ID
- Calculate total purchase (SUM)
- Exclude customers with null names (WHERE)
- Sort by total spent in descending order (ORDER BY)
- Limit to top 3
```bash
SELECT customer_id, SUM(purchase_amount) AS total_spent
FROM sales
WHERE customer_name IS NOT NULL
GROUP BY customer_id
HAVING SUM(purchase_amount) > 0
ORDER BY total_spent DESC
LIMIT 3;
```

#

### 3. Find Products with High Sales Volume in Specific Categories
#### Requirements:
- Filter only categories 'Electronics' and 'Furniture'.
- Group by product
- Include only those with total quantity sold > 100
- Order by quantity sold descending
```bash
SELECT product_name, category, SUM(quantity) AS total_quantity
FROM orders
WHERE category IN ('Electronics', 'Furniture')
GROUP BY product_name, category
HAVING SUM(quantity) > 100
ORDER BY total_quantity DESC;
```

#

### 4. List Courses with More Than 50 Students and Average Marks ≥ 70
#### Requirements:
- Group records by course name
- Filter to include only groups with student count > 50 and average marks ≥ 70
- Order alphabetically by course name
```bash
SELECT course_name, COUNT(*) AS total_students, AVG(marks) AS avg_marks
FROM student_courses
GROUP BY course_name
HAVING COUNT(*) > 50 AND AVG(marks) >= 70
ORDER BY course_name ASC;
```

#

###  5. Employee Report Based on Salary and Joining Year
#### Requirements:
- Filter employees who joined after 2015
- Group by year of joining and department
- Calculate average and max salary
- Show only those departments with more than 3 employees
- Order by year and department
```bash
SELECT YEAR(join_date) AS joining_year, department, 
       COUNT(*) AS total_employees,
       AVG(salary) AS avg_salary,
       MAX(salary) AS max_salary
FROM employees
WHERE join_date > '2015-01-01'
GROUP BY YEAR(join_date), department
HAVING COUNT(*) > 3
ORDER BY joining_year, department;
```












