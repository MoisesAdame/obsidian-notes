---
tags:
  - situation-caluclus
---
Date: 2026-11-02 : 19:02
***
## Chapter's Tip
The conceptual heart. Ontology (`S0`, `do`, situations as histories, fluents), action precondition axioms, effect axioms, the **qualification problem**, the **frame problem**, and the simple solution via **successor state axioms** (combining Pednault + Davis/Haas/Schubert). Also planning-as-theorem-proving and the database example.

## Basic Definitions
- **Situation Calculus**: A Second Order Language, designed to represent worlds that change.
- **Actions**: Changes to the world. FOL functions.
- **World History/Situation**: Sequence of actions. FOL terms.
- **Function do()**: Is the new situation $s_{t+1} = do(a, s_{t})$

## The Poss() function.
**Definition**:
$Poss(a, s)$: It is possible to do action a on situation s,

**Example**
$Poss(pickup(x, r),s) \supset [(\forall z)\neg holding(r, z, s)]\land \neg heavy(x) \land NextTo(x,r,s)$

"If it is **possible** for a robot r to pick up object x on situation s, then on situation s the robot r is not holding anything AND the object is not heavy AND on situation s the robot r is next to object x"

## Different Types of Axioms
### Action Precondition Axioms
What has to happen for me to be able to do an action.

**Example**: $Poss(pickup(x, r),s) \supset [(\forall z)\neg holding(r, z, s)]\land \neg heavy(x) \land NextTo(x,r,s)$

### Effect Axioms
What happens once I do an action.

**Example**: $poss(pickup(x, r), s) \supset holding(r, x, do(pickup(x, r)))$

### Frame Axioms
What doesn't change when I do an action.

**Example**: $holding(r, x, s) \supset holding(r, x, do(paint(r', x', c), s))$
**Meaning**: If the robot r holds object x on situation s, then when robot r' paints object x' of color c, the robot r is still holding object x. Another robot painting another object, doesn't affect when my robot is holding some object.

## The Frame Problem
There are a lot of *frame axioms* (because doing some action doesn't affect a lot of things).

### Problem
The frame problem has **two** parts:
1. Who writes the axioms has to think and write every single *frame axiom*.
2. The system has to be able to *efficiently* use that many axioms to reason.

### Solution
Somehow find a way to systematically use the *efect axioms* to write the *frame axioms*.
