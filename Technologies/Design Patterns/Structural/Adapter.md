---
tags:
---
Date: 2025-03-06 : 14:32
***
## Intent 
Allows objects with **incompatible** interfaces to collaborate.

## Structure Example
![[structure-adapter.png]]

## Code Example
```go
// Target interface: the client expects this.
type Target interface {
	Request() string
}

// Adaptee: an existing type with a different interface.
type Adaptee struct{}

// SpecificRequest is the method of Adaptee that doesn't match the Target interface.
func (a *Adaptee) SpecificRequest() string {
	return "Adaptee: Specific request."
}

// Adapter: wraps an Adaptee to make it compatible with the Target interface.
type Adapter struct {
	adaptee *Adaptee
}

// Request implements the Target interface by delegating to the Adaptee's SpecificRequest.
func (adapter *Adapter) Request() string {
	// Here we can add conversion logic if needed.
	return adapter.adaptee.SpecificRequest()
}

func main() {
	// Create an instance of Adaptee.
	adaptee := &Adaptee{}

	// Wrap the adaptee in an adapter.
	adapter := &Adapter{adaptee: adaptee}

	// The client uses the adapter as a Target.
	var client Target = adapter
	fmt.Println(client.Request())
}
```