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

**Expressions** of $\mathcal{L}$ can be: *Terms* (describe individuals, thus have functions) or *Well Formed Formulas* (describe relations, thus have predicates).

Two important *types of terms*:
- **Ground Term**: A term without variables.
- **Primitive Term**: A ground term with only one function.

Three important *types of wff's*:
- **Atoms**: They are of the form $P(t_{1}, \dots, t_{k})$, where $t_{i}$ is a term and $P$ is a predicate.
- **Ground Atoms**: An atom without variables.
- **Primitive Atom**: An atom where every $t_{i}$ is a standard name.

**Sentences** are wff's with no free variables. They can have a *truth value*, so they represent knowledge.

### Domain of Quantification
**Assumption**: Every object has its own standard name. This means that there are not unnamable objects.

### World
In propositional logic one specifies the *interpretation* by giving each atomic sentence a truth value, after which you can calculate the truth value for the non atomic sentences.

Inf FOL you need to specify two things:
- *Truth value* for each *primitive atom*.
- *Standard name* for each *primitive term*.

Those assignments are the **world state** or **worlds**.

### Evaluating sentnces
A sentence $\alpha$ is modelled by a world $w$ iff that sentence is true in that world.
$$
w \models P(t_{1}, \dots, t_{k}) \iff w[P(t_{1}, \dots, t_{k})] = 1
$$

