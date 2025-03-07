---
tags:
  - design-pattern/behavioral
  - design-pattern
---
Date: 2025-03-06 : 20:35
***
## Intent 
Lets you define a family of algorithms, put each of them into a separate class, and make their objects interchangeable.

Build different **strategies** in the interface strategy and select one of them from the main method.

## Structure
![[structure-strategy.png]]

## Code Example
```go
// Strategy interface
type Strategy interface {
	Execute(int, int) int
}

// Concrete Strategies
type Addition struct{}

func (a *Addition) Execute(x, y int) int {
	return x + y
}

type Subtraction struct{}

func (s *Subtraction) Execute(x, y int) int {
	return x - y
}

// Context struct
type Context struct {
	strategy Strategy
}

// SetStrategy allows changing strategy dynamically
func (c *Context) SetStrategy(s Strategy) {
	c.strategy = s
}

// ExecuteStrategy runs the current strategy
func (c *Context) ExecuteStrategy(x, y int) int {
	return c.strategy.Execute(x, y)
}

func main() {
	// Create context
	context := &Context{}

	// Use Addition strategy
	context.SetStrategy(&Addition{})
	fmt.Println("10 + 5 =", context.ExecuteStrategy(10, 5))

```