---
tags:
  - design-pattern/creational
  - factory-method
---
Date: 2025-03-04 : 14:25
***
## Intent
Provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.

## Structure
![[structure-factory-method.png]]

## Code Example
```go
// Notification interface
type Notification interface {
	Send(message string)
}

// EmailNotification struct
type EmailNotification struct{}

func (e *EmailNotification) Send(message string) {
	fmt.Println("Sending Email:", message)
}

// SMSNotification struct
type SMSNotification struct{}

func (s *SMSNotification) Send(message string) {
	fmt.Println("Sending SMS:", message)
}

// Factory Method
func GetNotification(notificationType string) Notification {
	if notificationType == "email" {
		return &EmailNotification{}
	} else if notificationType == "sms" {
		return &SMSNotification{}
	}
	return nil
}
```