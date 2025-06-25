#
# Chapter 4: Keys in RDBMS
<br>
<br>


## What Are 'Keys'?
In Database Management Systems (DBMS), a key is **an attribute or a set of attributes** that uniquely identifies a record (row) in a table.
There are **8 types of keys** in RDBMS.

| RollNo | Name    | Email                                             | Phone      | Course  |
| ------ | ------- | ------------------------------------------------- | ---------- | ------- |
| 101    | Alice   | [alice12@example.com](mailto:alice12@example.com) | 9876543210 | Math    |
| 102    | Bob     | [bob454@example.com](mailto:bob454@example.com)   | 9123456780 | Math    |
| 103    | Alice   | [alice76@example.com](mailto:alice76@example.com) | 9988776655 | CS      |

## 1. Primary Key
- It is the smallest possible set that can uniquely identifies each record in a table.
- Cannot contain NULL values.
- Must be unique i.e., each table can have only one primary key.
- The primary key is denoted by an underline to the name of the attribute.

#### Example: 
`RollNo` is the primary key — every student has a unique roll number.
`Phone` is the primary key — every student has a unique phone number.
But note that {RollNo, Phone} is not a primary key as it is not the smallest set.



## 2. Candidate Key
- Set of all possible primary keys.
- All possible fields that can serve as a primary key.
- Every candidate key can uniquely identify a row.

#### Example: 
RollNo, Email, and Phone can all uniquely identify a student. 
So, Candidate Keys = {RollNo, Email, Phone}

##  3. Super Key
- Any combination of attributes that uniquely identifies a row.
- It is the set conatining all possible combinations of keys.
- Includes candidate keys and additional attributes.

#### Example:
Super Keys = {RollNo}, {Email}, {Phone}, {RollNo, Name}, {Phone, Name}

## 4. Composite Key
- A key made of two or more attributes that together uniquely identify a row.
- Used when a single field is not sufficient.

#### Example:
Let’s say we have another table: 
Course_Enrollments:
| RollNo | Course  | Semester |
| ------ | ------- | -------- |
| 101    | Math    | 1        |
| 101    | Physics | 2        |

Here, {RollNo + Course} can serve as a composite key because a student can enroll in multiple courses, but not in the same course more than once.

## 5. Foreign Key
- A field that refers to the primary key of another table.
- Establishes a relationship between two tables.

#### Example:
In `Course_Enrollments`, RollNo is a foreign key referencing Students(RollNo).
