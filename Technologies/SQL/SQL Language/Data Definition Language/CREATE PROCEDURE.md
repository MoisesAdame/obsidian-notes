---
tags:
  - sql
  - sql-statement
  - database
---
Date: 2024-06-12 : 04:33
***

## Description

A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.

Stored procedures not always **return** something.

## Example

```sql
DELIMITER //
CREATE PROCEDURE select_similar_first_names(IN name_alike varchar(255))
BEGIN
    SELECT *
    FROM student
    WHERE first_name LIKE concat('%', name_alike, '%');
END //
DELIMITER ;
```
