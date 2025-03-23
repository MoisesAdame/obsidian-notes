---
tags:
  - design-pattern/creational
  - design-pattern
---
Date: 2025-03-04 : 15:22
***
## Intent 
Helps to create **complex** objects step by step. You can also use it to crate *multiple representations*.

## Structure
### Erroneous Structure: Giant Constructor
Use a giant constructor with a lot of parameters. Unfortunately, most of the time the **vast majority** of parameters wont be used.
```go
func NewHouse(windows int, doors int, rooms int, hasGarage bool, hasSwimmingPool bool, hasGarden bool, ...)
```

### Correct Structure: House Builder
![[structure-builder.png]]

## Code Example
```go
// -- Define the Product
// Car represents the complex object being built
type Car struct {
	Brand   string
	Color   string
	Engine  string
	Wheels  int
	Sunroof bool
}

// -- Create the Builder Interface
// CarBuilder defines the builder interface
type CarBuilder interface {
	SetBrand(brand string) CarBuilder
	SetColor(color string) CarBuilder
	SetEngine(engine string) CarBuilder
	SetWheels(wheels int) CarBuilder
	SetSunroof(sunroof bool) CarBuilder
	Build() Car
}

// -- Implement the Concrete Builder
// ConcreteCarBuilder implements CarBuilder
type ConcreteCarBuilder struct {
	car Car
}

func NewCarBuilder() *ConcreteCarBuilder {
	return &ConcreteCarBuilder{}
}

func (b *ConcreteCarBuilder) SetBrand(brand string) CarBuilder {
	b.car.Brand = brand
	return b
}

func (b *ConcreteCarBuilder) SetColor(color string) CarBuilder {
	b.car.Color = color
	return b
}

func (b *ConcreteCarBuilder) SetEngine(engine string) CarBuilder {
	b.car.Engine = engine
	return b
}

func (b *ConcreteCarBuilder) SetWheels(wheels int) CarBuilder {
	b.car.Wheels = wheels
	return b
}

func (b *ConcreteCarBuilder) SetSunroof(sunroof bool) CarBuilder {
	b.car.Sunroof = sunroof
	return b
}

func (b *ConcreteCarBuilder) Build() Car {
	return b.car
}
```