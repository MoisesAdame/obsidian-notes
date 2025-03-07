---
tags:
  - design-pattern/behavioral
  - design-pattern
---
Date: 2025-03-06 : 21:14
***
## Intent
Defines the skeleton of an algorithm in the superclass but lets subclasses override specific steps of the algorithm without changing its structure.

## Structure
![[structure-template.png]]

## Code Example
```go
// Abstract class with template method
type Game struct{}

func (g *Game) Play() {
    g.Start()
    g.PlayTurn()
    g.End()
}

func (g *Game) Start() {
    fmt.Println("Game starting...")
}

func (g *Game) End() {
    fmt.Println("Game over!")
}

// Concrete class that implements specific steps
type Chess struct {
    Game
}

func (c *Chess) PlayTurn() {
    fmt.Println("Chess: Playing a turn")
}

type Football struct {
    Game
}

func (f *Football) PlayTurn() {
    fmt.Println("Football: Playing a turn")
}
```