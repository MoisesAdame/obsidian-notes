---
tags:
  - first-order-logic
---
Date: 2026-10-29 : 20:00
***
## Building Blocks
- **Constants**: Names for specific objects (a, b)
- **Variables**: Placeholders for the names.
- **Predicates**: Properties of or relations between objects (Loves (x, y))
- **Functions**: Map from one object to another (a = Father(b))
- **Terms**: Variables, standard names or functions applied to terms (best_friend(moy))

## Complex Concepts
### Standard Names
The **keys** of our database.

If all the *terms* are divided into *equivalence classes* (A set were all the objects are rsflexive, symetric and transitive, in plain words if best_friend(moy) and brother(chabellini) belomg to the same equivalence class, by symmetry we know that brother(chabellini) = best_friend(moy) implies best_friend(moy) = brother(chabellini)), then each equivalence class is one **standard name**.

### Syntax of $\mathcal{L}$
Divided in two:
- **Logical symbols**: Variables, standard names, equality ($=$) and logical connectives ($\forall, \exists,\neg,\vee$)
- **Non Logical Symbols**: Predicates, functions.

The **expressions** of $\mathcal{L}$ can be: *Terms* or *Well Formed Formulas*.