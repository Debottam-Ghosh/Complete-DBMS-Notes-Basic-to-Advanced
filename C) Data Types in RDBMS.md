#
# Chapter 3: Data Types in RDBMS
<br>
<br>

In RDBMS, data types define the kind of data a column can hold — such as numbers, text, dates, etc. They ensure data integrity, optimization, and accurate storage.

<br>

## Numeric Data Types
| Data Type      | Description                            | Example Values        |
| -------------- | -------------------------------------- | --------------------- |
| `INT`          | Integer numbers                        | 10, -5, 1000          |
| `SMALLINT`     | Smaller range of integers              | 32, -255              |
| `BIGINT`       | Very large integers                    | 9223372036854775807   |
| `DECIMAL(p,s)` | Fixed-point numbers (precision, scale) | 123.45 (DECIMAL(5,2)) |
| `NUMERIC(p,s)` | Same as DECIMAL                        | 99.99                 |
| `FLOAT`        | Approximate floating-point numbers     | 3.14159               |
| `REAL`         | Less precision than FLOAT              | 1.23                  |
| `DOUBLE`       | More precision                         | 3.1415926535          |

<br>

## Character/String Data Types
| Data Type       | Description                  | Example         |
| --------------- | ---------------------------- | --------------- |
| `CHAR(n)`       | Fixed-length string (padded) | 'A', 'Hello  '  |
| `VARCHAR(n)`    | Variable-length string       | 'World'         |
| `TEXT`          | Large text data              | Articles, Notes |

<br>

## Date and Time Data Types
| Data Type   | Description             | Example                 |
| ----------- | ----------------------- | ----------------------- |
| `DATE`      | Stores date only        | `'2025-06-21'`          |
| `TIME`      | Stores time only        | `'13:45:00'`            |
| `DATETIME`  | Stores both date & time | `'2025-06-21 13:45:00'` |
| `TIMESTAMP` | Stores timestamp        | `'2025-06-21 13:45:00'` |
| `YEAR`      | Stores year only        | `2025`                  |

<br>

## Boolean Type
| Data Type | Description   | Example           |
| --------- | ------------- | ----------------- |
| `BOOLEAN` | True or False | TRUE, FALSE, 1, 0 |

<br>

## Binary Types
| Data Type      | Description                 | Use Case               |
| -------------- | --------------------------- | ---------------------- |
| `BINARY(n)`    | Fixed-length binary data    | Encryption, flags      |
| `VARBINARY(n)` | Variable-length binary data | Images, files          |
| `BLOB`         | Large Binary Object         | Multimedia files, docs |

