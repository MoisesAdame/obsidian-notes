---
tags:
  - sql
  - database
  - sql-statement
---
Date: 2024-06-12 : 01:20
***

## Description

Suppose that we have $\sigma_{1}$ and $\sigma_{2}$  UNION gives us $\sigma_{1} \cup \sigma_{2}$.

The big difference is that:
- UNION **doesn't** allow duplicates.
- UNION ALL does allow duplicates.

The dimension of the selects **has to be the same** for them to work.
## Example
```sql
SELECT column1, column2, column3 FROM table1
UNION | UNION ALL
SELECT column1, column2, column3 FROM table2;
```