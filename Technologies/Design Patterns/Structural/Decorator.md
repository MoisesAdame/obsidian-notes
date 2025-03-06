---
tags:
  - design-pattern
  - design-pattern/structural
---
Date: 2025-03-06 : 15:19
***
## Intent
Gives new behaviors to objects by placing them inside a wrapper.

Imagine we have a Notifier class that only sends notifications via sms. Then a requirement is launched where we should be able to customize if we want one or more of the following notifications: SMS, facebook & slack. 
## Constructor
![[structure-decorator.png]]

## Code Example
```go
// Coffee is the component interface.
type Coffee interface {
	GetCost() float64
	GetDescription() string
}

// SimpleCoffee is a concrete component that implements Coffee.
type SimpleCoffee struct{}

func (c *SimpleCoffee) GetCost() float64 {
	return 2.00
}

func (c *SimpleCoffee) GetDescription() string {
	return "Simple Coffee"
}

// Base decorator that wraps a Coffee. It can be embedded by concrete decorators.
type CoffeeDecorator struct {
	coffee Coffee
}

func (d *CoffeeDecorator) GetCost() float64 {
	// Delegate call to the wrapped coffee.
	return d.coffee.GetCost()
}

func (d *CoffeeDecorator) GetDescription() string {
	return d.coffee.GetDescription()
}

// MilkDecorator is a concrete decorator that adds milk.
type MilkDecorator struct {
	CoffeeDecorator
}

func NewMilkDecorator(coffee Coffee) *MilkDecorator {
	return &MilkDecorator{CoffeeDecorator{coffee: coffee}}
}

func (m *MilkDecorator) GetCost() float64 {
	// Add extra cost for milk.
	return m.CoffeeDecorator.GetCost() + 0.50
}

func (m *MilkDecorator) GetDescription() string {
	// Append milk to the description.
	return m.CoffeeDecorator.GetDescription() + ", Milk"
}

func main() {
	// Create a simple coffee.
	var coffee Coffee = &SimpleCoffee{}
	fmt.Printf("%s: $%.2f\n", coffee.GetDescription(), coffee.GetCost())

	// Decorate the coffee with milk.
	coffee = NewMilkDecorator(coffee)
	fmt.Printf("%s: $%.2f\n", coffee.GetDescription(), coffee.GetCost())
}
```