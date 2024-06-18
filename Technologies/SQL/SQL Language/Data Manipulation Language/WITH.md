---
tags:
  - sql
  - sql-statement
  - database
---
Date: 2024-06-12 : 02:11
***

## Description

Sometimes, we have queries inside other queries. These are called **subqueries**.

They can be fairly common and thats the reason for the existence of **Common Table Expressions** which are *temporary* results. 

> [!danger] 
> WITH lives inside the query.
> [[CREATE VIEW]] lives inside the table.

## Example

```sql
WITH cte AS ( 
	SELECT column1, column2 
	FROM table 
	WHERE condition 
)
SELECT *
FROM cte
```
