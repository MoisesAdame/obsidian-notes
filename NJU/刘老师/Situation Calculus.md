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
When describing our actions, we only say what they change, and what they dont change or affect, we just dont mention it.

This is a problem, because if we want to derive what is not changed by the action, we cant. This is the **Frame Problem**. 

#### Example: Bob and Alice and the Room
If Alice is in a room and Bob is not, our initial situation is: $In_{0}\{ Alice \}, \neg In_{0}\{ Bob \}$. If we apply the function `Enter()`, defined as $\forall x (Enter(x) \to In_{1}\{ x \})$ to Bob. Then our conclussion is: $In_{0}\{ Alice \}, In_{0}\{ Bob \}$. But neither the initial condition, nor the definition of `Enter()` tells us why Alice is still in, there is the problem.

#### Reiter's Solution
Steps:
1. Identify the *fluents* of our probelm.
2. Write the *effect axioms* (possitive $\gamma^+$ and negative $\gamma^-$).
	- Example: The effect axiom `on(x, y, do(stack(x, y), s))` is rewritten as $a = stack(x, y) \supset on(x, y, do(a, s))$, which reads: "If the action $a$ is tack x over y, then in the new situation when we do $a$ in $s$, x will be on top of y." 
	- In this case because $on()$ does not have a negation, it belongs to the possitive effect axioms $\gamma^+$. 
	- So, we get $\gamma^+_{n}(a, \vec{x}, s) \supset F(\vec{x}, do(a, s))$. Where $a$ is the action, $\vec{x}$ are the parameters of our fluent, $s$ is the situation, and $F$ is the fluent.
3. Apply the *Succesor-State Axiom Formula*.
	- Formula: $F(\vec{x}, do(a, s)) \equiv \gamma^+(a, \vec{x}, s) $



## Reference
- Handbook of Knowledge Representation (Chapter 16), Lin Fangzhen.
