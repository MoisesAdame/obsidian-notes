---
tags:
  - sql
  - database
  - sql-statement
---
Date: 2024-06-12 : 01:42
***

## Description

The **GROUP BY** statement groups rows that have the same **values**.

This grouping is done over **summary rows** and is often paired with aggregate functions like **COUN()**, **MAX()**, **SUM()**, etc.

## Example

```sql
SELECT country, COUNT(customer_id)
FROM customer
GROUP BY country
```
