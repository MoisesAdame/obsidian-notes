---
tags:
  - design-pattern/structural
  - design-pattern
---
Date: 2025-03-06 : 15:07
***
## Intent 
Lets you compose objects into **tree structures** and then work with these structures as if they were individual objects.

It is very similar to what we do when implementing a tree data structure.
## Structure
![[structure-composite.png]]

## Code Example
```go
// Component is the common interface for both simple (leaf) and complex (composite) objects.
type Component interface {
	Operation() string
}

// Leaf represents an individual object in the composition.
type Leaf struct {
	name string
}

// Operation for Leaf returns its name.
func (l *Leaf) Operation() string {
	return l.name
}

// Composite represents a complex component that can have children.
type Composite struct {
	name     string
	children []Component
}

// Add appends a new child to the composite.
func (c *Composite) Add(child Component) {
	c.children = append(c.children, child)
}

// Operation for Composite calls Operation on all its children and aggregates the results.
func (c *Composite) Operation() string {
	result := c.name + " ["
	for i, child := range c.children {
		result += child.Operation()
		if i < len(c.children)-1 {
			result += ", "
		}
	}
	result += "]"
	return result
}

func main() {
	// Create leaf components.
	leaf1 := &Leaf{name: "Leaf1"}
	leaf2 := &Leaf{name: "Leaf2"}
	leaf3 := &Leaf{name: "Leaf3"}

	// Create a composite component and add leaves to it.
	composite1 := &Composite{name: "Composite1"}
	composite1.Add(leaf1)
	composite1.Add(leaf2)

	// Create a root composite and add both a composite and a leaf.
	root := &Composite{name: "Root"}
	root.Add(composite1)
	root.Add(leaf3)

	// Display the result of the operation.
	fmt.Println(root.Operation())
}
```