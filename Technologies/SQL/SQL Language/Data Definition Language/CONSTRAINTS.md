---
tags:
  - sql
  - sql-statement
---
Date: 2024-06-12 : 03:44
***

## Description

SQL constraints are used to specify **rules** for the **data** in a table.

Some of them are:
- NOT NULL
- UNIQUE
- PRIMARY KEY: The same as NOT NULL + UNIQUE
- FOREIGN KEY
- CHECK
- DEFAULT
- CREATE INDEX

## Example

```sql
CREATE TABLE student (
	id int AUTO_INCREMENT PRIMARY KEY,
	last_name varchar(255) NOT NULL,
	first_name varchar(255) NOT NULL,
	sex varchar(1) NOT NULL,
	dob DATE NOT NULL,
	CHECK (sex IN ('M', 'F'))
)
```
