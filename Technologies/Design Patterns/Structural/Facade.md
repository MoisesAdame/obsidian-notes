---
tags:
  - design-pattern
  - design-pattern/structural
---
Date: 2025-03-06 : 15:41
***
## Intent 
Provides a simplified interface to a library, a framework, or any other complex set of classes.

## Structure
![[structure-facade.png]]

## Code Example
```go
// SubsystemA represents a part of a complex system.
type SubsystemA struct{}

// OperationA performs an action in SubsystemA.
func (s *SubsystemA) OperationA() {
	fmt.Println("SubsystemA: Executing Operation A")
}

// SubsystemB represents another part of a complex system.
type SubsystemB struct{}

// OperationB performs an action in SubsystemB.
func (s *SubsystemB) OperationB() {
	fmt.Println("SubsystemB: Executing Operation B")
}

// Facade provides a simplified interface to the complex subsystems.
type Facade struct {
	subsystemA *SubsystemA
	subsystemB *SubsystemB
}

// NewFacade creates a new Facade instance with initialized subsystems.
func NewFacade() *Facade {
	return &Facade{
		subsystemA: &SubsystemA{},
		subsystemB: &SubsystemB{},
	}
}

// DoSomething encapsulates the interactions with the subsystems.
func (f *Facade) DoSomething() {
	fmt.Println("Facade: Delegating tasks to subsystems...")
	f.subsystemA.OperationA()
	f.subsystemB.OperationB()
}

func main() {
	// Create the Facade.
	facade := NewFacade()

	// Use the Facade to perform operations on the subsystems.
	facade.DoSomething()
}
```