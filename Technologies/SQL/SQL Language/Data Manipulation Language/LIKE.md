---
tags:
  - sql
  - database
  - sql-statement
---
Date: 2024-06-12 : 01:28
***

## Description

It is used inside a [[WHERE]] and is used to look for a given *pattern*.

It is a best practice **not to use it**. Instead use **=**

The main difference is that **LIKE** allows partial matches and **=** doesn't.
## Example
```sql
SELECT name, sex, race
FROM customer
WHERE name LIKE 'ste%'
```


