---
tags:
---
Date: 2025-03-04 : 15:22
***
## Intent 
Helps to create **complex** objects step by step. You can also use it to crate *multiple representations*.

## Structure
### Erroneous Structure: Giant Constructor
Use a giant constructor with a lot of parameters. Unfortunately, most of the time the **vast majority** of parameters wont be used.
```go
func NewHouse(windows bool, doors bool, room)
```