---
tags:
  - situation-caluclus
---
Date: 2026-10-29 : 19:44
***
## What it is?
A first order language that represents change.

## Concepts
### Situation, Action and Fluents
#### Situation
FOL objects. The complete state of the universe ate an instance of time.

#### Action
What makes the world change from one situation to another.

#### Fluents
Functions that describe the effects of actions. They depend on the situation.

#### Example
A robot that stacks blocks in a tower.
- Actions: `stack(x, y)`, `unstack(x, y)`, `putdow(x)`, `pickup(x)`
- Fluents: `handempty(s)`, `holding(x, s)`, `on(x, y, s)`, `clear(x, s)`

### Axioms
They are the desciption of our language. They are first order sentences. Example:
$$
Poss(stack(x, y), s) \equiv holding(x, s) ~\vee~
$$



## Reference
- Handbook of Knowledge Representation (Chapter 16), Lin Fangzhen.
