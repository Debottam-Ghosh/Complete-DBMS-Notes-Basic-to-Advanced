## What is a Relational Database?
A Relational Database stores data in tables (relations) consisting of rows (tuples) and columns (attributes).


## Key Terms
| Term        | Description                                  |
| ----------- | -------------------------------------------- |
| Relation    | A table with rows and columns                |
| Tuple       | A row in a relation                          |
| Attribute   | A column in a relation                       |
| Domain      | Set of permissible values for an attribute   |
| Degree      | Number of attributes (columns) in a relation |
| Cardinality | Number of tuples (rows) in a relation        |


## Example: 
### &nbsp;&nbsp;&nbsp;`Students`
| StudentID | Name    | Age | Course  |
| --------- | ------- | --- | ------- |
| 101       | Alice   | 20  | Math    |
| 102       | Bob     | 21  | Physics |
| 103       | Charlie | 22  | CS      |

### Key Terms with Examples
| Term              | Meaning                                                       | Example from Table                          |
| ----------------- | ------------------------------------------------------------- | ------------------------------------------- |
| **Relation**      | A **table** in a database                                     | `Students` table                            |
| **Tuple**         | A **row** in a relation; represents one record                | Row: (101, Alice, 20, Math)                 |
| **Attribute**     | A **column** in the table; represents a field                 | `StudentID`, `Name`, `Age`, `Course`        |
| **Domain**        | Set of valid values an attribute can hold                     | Domain of `Age`: Positive integers          |
| **Degree**        | Number of attributes (columns) in a relation                  | 4 (StudentID, Name, Age, Course)            |


