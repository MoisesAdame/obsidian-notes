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
Description of our language. 
Describe the effects of actions. 
They are first order sentences.

Example:
$$
Poss(stack(x, y), s) \equiv holding(x, s) \land clear(y, s)
$$

In plain words `Poss(a, s)` is execute action `a` on situation `s`. So, we can only stack block x on block y iff we are holding it and there is no block on top of block y.

### Frame Problem


## Reference
- Handbook of Knowledge Representation (Chapter 16), Lin Fangzhen.
