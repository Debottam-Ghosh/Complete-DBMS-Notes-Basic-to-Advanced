## What is an ER Diagram?
An ER Diagram (Entity-Relationship Diagram) is a visual representation of data that shows how entities are related in a database system. It’s widely used in database design.

## Key Components of ER Diagrams
| Component        | Description                                         | Example                  |
| ---------------- | --------------------------------------------------- | ------------------------ |
| **Entity**       | Real-world object or concept stored in the database | Student, Course          |
| **Attribute**    | Property or characteristic of an entity             | Student Name, Course ID  |
| **Entity Set**   | Collection of similar entities                      | All students             |
| **Relationship** | Association between entities                        | Enrolls (Student–Course) |
| **Primary Key**  | Uniquely identifies an entity                       | Roll Number, Course Code |

## Types of Entities
- **Strong Entity:** Has a primary key and exists independently.
<br>Example: Student

- **Weak Entity:** Doesn’t have a primary key and depends on another entity.
<br>Example: Dependents of Employees

## Types of Attributes
| Attribute Type    | Description                          | Example                            |
| ----------------- | ------------------------------------ | ---------------------------------- |
| **Simple**        | Cannot be divided further            | Age                                |
| **Composite**     | Can be divided into smaller parts    | Full Name → First Name + Last Name |
| **Derived**       | Can be derived from other attributes | Age from DOB                       |
| **Multivalued**   | Can have multiple values             | Phone Numbers                      |
| **Key Attribute** | Uniquely identifies entity instances | Student ID                         |

## Symbols Used in ER Model
![image](https://github.com/user-attachments/assets/255d6a89-2fe1-4105-9272-ac76b4fe6381)

### ER Diagram:
![image](https://github.com/user-attachments/assets/743e78a3-0468-4b62-8de9-4b99dbc68348)


## Cardinality of Relationships
| Type                    | Description                           | Example            |
| ----------------------- | ------------------------------------- | ------------------ |
| **One-to-One (1:1)**    | One entity relates to one of another  | Person – Passport  |
| **One-to-Many (1\:N)**  | One entity relates to many of another | Teacher – Students |
| **Many-to-Many (M\:N)** | Many entities relate to many others   | Student – Courses  |

### One-to-One
![image](https://github.com/user-attachments/assets/39c0e453-e5d9-48ee-9385-8deaf3dc0c3d)

### One-to-Many
![image](https://github.com/user-attachments/assets/bebfda2c-ddc5-4404-94f6-999b30a6f65a)

### Many-to-One
![image](https://github.com/user-attachments/assets/2c13d342-c93a-43dd-b894-a1ff4b588d7c)

### Many-to-Many
![image](https://github.com/user-attachments/assets/d648287f-e304-4b15-ad4e-d376b583a59c)

## Participation Constraints
| Type        | Description                                       | Example                               |
| ----------- | ------------------------------------------------- | ------------------------------------- |
| **Total**   | Every entity must participate in the relationship | Every student must enroll in a course |
| **Partial** | Some entities may not participate                 | some courses are not enrolled by any of the students         |

### ER Diagram
![image](https://github.com/user-attachments/assets/901cd0a4-6a19-43e7-984f-658cad91dc05)

