---
tags:
---
Date: 2025-03-06 : 14:13
***
## Intent 
Imagine wanting to copy an object. Yo can do this by creating another object and assigning the same attributes, but a problem arises when we have to copy **private attributes**.

This pattern delegates the cloning process to the actual objects that are being cloned, declaring a common interface

## Structure
![[structure-prototype.png]]

## Code Example
```go
// Shape is the prototype interface declaring the Clone method.
type Shape interface {
	Clone() Shape
}

// Rectangle represents a rectangle shape.
type Rectangle struct {
	Width, Height int
}

// Clone creates a new copy of the Rectangle.
func (r *Rectangle) Clone() Shape {
	return &Rectangle{
		Width:  r.Width,
		Height: r.Height,
	}
}

// Triangle represents a triangle shape.
type Triangle struct {
	Base, Height int
}

// Clone creates a new copy of the Triangle.
func (t *Triangle) Clone() Shape {
	return &Triangle{
		Base:   t.Base,
		Height: t.Height,
	}
}

func main() {
	// Create initial shapes.
	rectangle := &Rectangle{Width: 10, Height: 20}
	triangle := &Triangle{Base: 15, Height: 25}

	// Clone shapes using the Prototype design pattern.
	rectangleClone := rectangle.Clone()
	triangleClone := triangle.Clone()

	// Display cloned shapes.
	fmt.Println("Cloned shapes:")
	rectangleClone.Draw()
	triangleClone.Draw()
}
```