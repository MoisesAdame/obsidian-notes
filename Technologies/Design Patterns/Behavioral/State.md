---
tags:
  - design-pattern/behavioral
  - design-pattern
---
Date: 2025-03-06 : 20:59
***
## Intent 
Lets an object alter its behavior when its internal state changes. It appears as if the object changed its class.

>**Finite State Machine**
>A system that can be in **one state at a time** and changes between states based on certain **rules**. Think of it like a traffic light:
>1. It can be **red, yellow, or green** (these are the states).
>2. t changes from one color to another **based on time or sensor inputs** (these are the transitions).
>3.  **never jumps randomly**—it follows a **fixed pattern** (like red → green → yellow → red).



## Structure
The following is the **finite state machine** of a document. It can be in the state draft, moderation or pusblish.
![[structure-state-part1.png]]

Create an interface and implement concrete states.
![[structure-state-part2.png]]

## Code Example
```go

```