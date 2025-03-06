---
tags:
  - design-pattern/creational
  - design-pattern
---
Date: 2025-03-04 : 14:59
***
## Intent 
Pattern that allows us to produce **related objects** without having to fully specify the class. The "father class" has to be an interface.

### In Case You Don't Remember What a Interface Is
Consider the following situation:

> _You are in the middle of a large, empty room, when a zombie suddenly attacks you._
> 
> _You have no weapon._
> 
> _Luckily, a fellow living human is standing in the doorway of the room._
> 
> _"Quick!" you shout at him. "Throw me something I can hit the zombie with!"_

Now consider:  
You didn't specify (nor do you care) exactly **what** your friend will choose to toss ...but it doesn't matter, as long as:
- It's something that **can** be tossed (He can't toss you the sofa)
- It's something that you can grab hold of (Let's hope he didn't toss a shuriken)
- It's something you can use to bash the zombie's brains out (That rules out pillows and such)

It doesn't matter whether you get a baseball bat or a hammer -  
as long as it implements your three conditions, you're good.

**Finally:** When you write an interface, you're basically saying: "I need something that..."

## Structure
![[structure-abstract-factory.png]]

## Code Example
```go
// -- Define Abstract Interfaces
// Button interface
type Button interface {
	Render()
}

// Checkbox interface
type Checkbox interface {
	Check()
}

// GUIFactory interface (Abstract Factory)
type GUIFactory interface {
	CreateButton() Button
	CreateCheckbox() Checkbox
}

// -- Implement Concrete Products
// MacOSButton struct
type MacOSButton struct{}

func (m *MacOSButton) Render() {
	fmt.Println("Rendering MacOS Button")
}

// WindowsButton struct
type WindowsButton struct{}

func (w *WindowsButton) Render() {
	fmt.Println("Rendering Windows Button")
}

// MacOSCheckbox struct
type MacOSCheckbox struct{}

func (m *MacOSCheckbox) Check() {
	fmt.Println("MacOS Checkbox Checked")
}

// WindowsCheckbox struct
type WindowsCheckbox struct{}

func (w *WindowsCheckbox) Check() {
	fmt.Println("Windows Checkbox Checked")
}

// -- Implement Concrete Factories
// MacOSFactory struct
type MacOSFactory struct{}

func (m *MacOSFactory) CreateButton() Button {
	return &MacOSButton{}
}

func (m *MacOSFactory) CreateCheckbox() Checkbox {
	return &MacOSCheckbox{}
}

// WindowsFactory struct
type WindowsFactory struct{}

func (w *WindowsFactory) CreateButton() Button {
	return &WindowsButton{}
}

func (w *WindowsFactory) CreateCheckbox() Checkbox {
	return &WindowsCheckbox{}
}

// -- Implement Factory Selector
// GetFactory function (Factory Selector)
func GetFactory(osType string) GUIFactory {
	if osType == "mac" {
		return &MacOSFactory{}
	} else if osType == "windows" {
		return &WindowsFactory{}
	}
	return nil
}
```