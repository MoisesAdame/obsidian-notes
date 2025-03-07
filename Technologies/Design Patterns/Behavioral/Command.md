---
tags:
  - design-pattern/behavioral
  - design-pattern
---
Date: 2025-03-06 : 20:42
***
## Intent 
 Turns a request into an object. This transformation lets you pass requests as a method arguments, delay or queue a request’s execution, and support undoable operations.

## Structure
![[structure-command.png]]

## Code Example
```go
// Command interface
type Command interface {
	Execute()
	Undo()
}

// Receiver (The actual business logic)
type Light struct {
	isOn bool
}

func (l *Light) TurnOn() {
	l.isOn = true
	fmt.Println("Light is ON")
}

// Concrete Command to turn the light ON
type LightOnCommand struct {
	light *Light
}

func (c *LightOnCommand) Execute() {
	c.light.TurnOn()
}

func (c *LightOnCommand) Undo() {
	c.light.TurnOff()
}

// Invoker (Holds commands and triggers execution)
type RemoteControl struct {
	command Command
}

func (r *RemoteControl) SetCommand(cmd Command) {
	r.command = cmd
}

func (r *RemoteControl) PressButton() {
	r.command.Execute()
}

func (r *RemoteControl) PressUndo() {
	r.command.Undo()
}

func main() {
	// Receiver
	light := &Light{}

	// Concrete commands
	lightOn := &LightOnCommand{light: light}

	// Invoker
	remote := &RemoteControl{}

	// Turn the light ON
	remote.SetCommand(lightOn)
	remote.PressButton()

	// Undo (Turn it OFF)
	remote.PressUndo()

	// Undo (Turn it ON)
	remote.PressUndo()
}
```