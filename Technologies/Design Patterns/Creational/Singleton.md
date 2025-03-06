---
tags:
  - design-pattern/creational
  - design-pattern
---
Date: 2025-03-04 : 14:47
***
## Intent 
Ensures that a class has **only one instance**. This can be done only if the instance is accessible from anywhere.

## Structure
![[structure-singleton.png]]

## Code Example
```go
// Singleton struct
type Singleton struct {
	Data string
}

var instance *Singleton

// GetInstance ensures only one instance is created
func GetInstance() *Singleton {
	if instance == nil {
		instance = &Singleton{Data: "Hello!"}
	}
	return instance
}
```