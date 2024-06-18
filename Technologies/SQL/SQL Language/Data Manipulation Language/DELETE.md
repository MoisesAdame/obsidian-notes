---
tags:
  - sql
  - sql-statement
  - database
---
Date: 2024-06-12 : 03:01
***

## Description

Deletes a record given certain condition.

Is very **expensive** because it reconstructs the **indexes**.

## Example

```sql
DELETE FROM customer
WHERE id=3
```
