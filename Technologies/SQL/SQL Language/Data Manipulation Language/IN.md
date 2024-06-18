---
tags:
  - sql
  - sql-statement
  - database
---
Date: 2024-06-12 : 01:50
***

## Description

It is used inside a [[WHERE]] and is used for the same as the mathematical $x \in \{1, 2, 3\}$.

It can also be paired with the keyword **NOT**.

## Example

```sql
SELECT name, id
FROM customer
WHERE country IN ('MEXICO', 'CHINA')
```
