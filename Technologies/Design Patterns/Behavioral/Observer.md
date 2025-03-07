---
tags:
  - design-pattern
  - design-pattern/behavioral
---
Date: 2025-03-06 : 16:17
***
## Intent 
Subscription mechanism to notify multiple objects about any events that happen to the object they’re observing.

## Structure
![[structure-observer.png]]

## Code Example
```go
// Observer interface
type Observer interface {
	Update(string)
}

// Concrete Observer
type ConcreteObserver struct {
	Name string
}

func (co *ConcreteObserver) Update(message string) {
	fmt.Printf("%s received update: %s\n", co.Name, message)
}

// Subject interface
type Subject interface {
	Register(Observer)
	Unregister(Observer)
	Notify(string)
}

// Concrete Subject
type ConcreteSubject struct {
	observers []Observer
}

func (cs *ConcreteSubject) Register(o Observer) {
	cs.observers = append(cs.observers, o)
}

func (cs *ConcreteSubject) Unregister(o Observer) {
	for i, observer := range cs.observers {
		if observer == o {
			cs.observers = append(cs.observers[:i], cs.observers[i+1:]...)
			break
		}
	}
}

func (cs *ConcreteSubject) Notify(message string) {
	for _, observer := range cs.observers {
		observer.Update(message)
	}
}

func main() {
	subject := &ConcreteSubject{}

	observer1 := &ConcreteObserver{Name: "Observer 1"}
	observer2 := &ConcreteObserver{Name: "Observer 2"}

	subject.Register(observer1)
	subject.Register(observer2)

	subject.Notify("Hello, Observers!")

	subject.Unregister(observer1)

	subject.Notify("Observer 1 has been removed!")
}

```

