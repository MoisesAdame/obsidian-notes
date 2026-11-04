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
