#
# Chapter 14: CASE Statement in SQL
The CASE statement in SQL allows you to perform if-then-else logic in SQL queries, returning different values based on conditions.
<br>

## Syntax
```bash
CASE 
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    ...
    ELSE result_default
END AS new_col_name
```

<br>

## Example

#### 1. Label Employee Salary Levels
```bash
SELECT name, salary,
  CASE 
    WHEN salary >= 80000 THEN 'High'
    WHEN salary >= 50000 THEN 'Medium'
    ELSE 'Low'
  END AS salary_level
FROM employees;
```

####  2. Grade Students Based on Marks
```bash
SELECT student_name, marks,
  CASE 
    WHEN marks >= 90 THEN 'A'
    WHEN marks >= 75 THEN 'B'
    WHEN marks >= 60 THEN 'C'
    ELSE 'F'
  END AS grade
FROM students;
```

#### 3. Replace Department Codes with Names (Simple CASE)
```bash
SELECT employee_id, department_code,
  CASE department_code
    WHEN 'HR' THEN 'Human Resources'
    WHEN 'IT' THEN 'Information Tech'
    WHEN 'FIN' THEN 'Finance'
    ELSE 'Other'
  END AS department_name
FROM employees;
```

#### 4. Use CASE in ORDER BY for Custom Sorting
```bash
SELECT name, status
FROM tasks
ORDER BY 
  CASE status
    WHEN 'High' THEN 1
    WHEN 'Medium' THEN 2
    WHEN 'Low' THEN 3
    ELSE 4
  END;
```

