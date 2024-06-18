---
tags:
  - sql
  - sql-statement
  - database
---
Date: 2024-06-12 : 02:17
***

## Description

This statement creates a **virtual table** that comes from one or more tables in the database.

The view lives inside the table.

Why are they useful:
- **Simplicity**: No need to rewrite the queries fro scratch.
- **Security**: Can be seen as a DTO. Exposes only authorized data.

## Example

```sql
CREATE VIEW view_name AS  
SELECT column1, column2, ...  
FROM table_name  
WHERE condition;
```
