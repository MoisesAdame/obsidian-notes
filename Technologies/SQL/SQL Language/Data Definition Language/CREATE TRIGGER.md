---
tags:
  - sql
  - sql-statement
  - database
---
Date: 2024-06-12 : 04:45
***

## Description

A trigger is a special type of [[CREATE PROCEDURE]] that **automatically** executes in response to certain events on a particular table or view.

## Example

```sql
DELIMITER //
CREATE TRIGGER add_to_inserts
AFTER INSERT 
ON student
FOR EACH ROW
BEGIN
	INSERT INTO inserts
	VALUES (1);
END //
DELIMITER ;
```
