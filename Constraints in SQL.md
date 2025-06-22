Constraints are rules applied to table columns in SQL to ensure data integrity, validity, and consistency in a relational database.

<br>

## Common Types of SQL Constraints
| Constraint    | Description                                                      |
| ------------- | ---------------------------------------------------------------- |
| `NOT NULL`    | Ensures a column cannot have `NULL` values                       |
| `UNIQUE`      | Ensures all values in a column are unique                        |
| `PRIMARY KEY` | Uniquely identifies each record and combines `NOT NULL + UNIQUE` |
| `FOREIGN KEY` | Enforces referential integrity by linking to another table’s key |
| `CHECK`       | Ensures values meet a specific condition                         |
| `DEFAULT`     | Sets a default value when none is provided                       |

### 1. NOT NULL
```bash
CREATE TABLE Students (
    ID INT NOT NULL,
    Name VARCHAR(50) NOT NULL
);
```

<br>

### 2. UNIQUE
```bash
CREATE TABLE Users (
    Email VARCHAR(100) UNIQUE
);
```

<br>

### 3. PRIMARY KEY
- Uniquely identifies each row.
- Combines NOT NULL + UNIQUE.
- Only one primary key allowed per table.
```bash
CREATE TABLE Employees (
    EmpID INT PRIMARY KEY,
    Name VARCHAR(50)
);
```
You can also define a composite primary key:
```bash
PRIMARY KEY (OrderID, ProductID)
```

<br>

### 4. FOREIGN KEY
- Enforces a relationship between two tables. The foreign key must match a primary key in another table.
```bash
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerID INT,
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```

<br>

### 5. CHECK
- Limits the values that can be placed in a column.
```bash
CREATE TABLE Products (
    Price DECIMAL(10,2),
    CHECK (Price > 0)
);
```

<br>

### 6. DEFAULT
- Provides a default value when no value is specified.
```bash
CREATE TABLE Students (
    Name VARCHAR(50),
    Grade CHAR(1) DEFAULT 'C'
);
```

<br>

### Adding Constraints After Table Creation
You can also use ALTER TABLE to add constraints:
```bash
ALTER TABLE Students
ADD CONSTRAINT unique_email UNIQUE (Email);
```
