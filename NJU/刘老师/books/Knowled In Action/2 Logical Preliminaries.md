---
tags:
  - first-order-logic
  - second-order-logic
---
Date: 2026-11-02 : 16:37
***
## First Order Logic
#### Syntax
The vocabulary is divided in:
- *Logical symbols* (parenthesis, connectives, variables, equality)
- *Parameters* (quantifiers, predicates and functions)

A *sentence* is a formula with no free variables.

The *dot notation* for quantifier makes easier for us to not write parentehis, indicates the preceding quantifier has maximum scope, for example:
$$
[(\forall x)(\exists x).A(x, y)\land B(x, y)\supset C(x,y)] \land R(x, y)
$$

Is the same as:
$$
[(\forall x)(\exists x)[A(x, y)\land B(x, y)\supset C(x,y)]] \land R(x, y)
$$

#### Semantics
A **structure** $\mathcal{S}$ (also called *interpretation*) is a function whose domain are the *parameters* (functions, predicates) of our language. For isntance $S(P)$ gives us the tuples where $P$ is true and $S(f)$ returns the actual function.

It is defined by:
1. The universe: $\lvert \mathcal{S} \rvert$
2. For $n$-ary predicates: $P^\mathcal{S}\subseteq \lvert \mathcal{S} \rvert^n$ (all the combinations where predicate $P$ is true).
3. For $n$-ary functions: $f^\mathcal{S} : \lvert \mathcal{S} \rvert^n \to \lvert \mathcal{S} \rvert$ (for example in situation calculus actions are functions, thus $a_{1} = \text{PickUp}(x, y)$, where $a_{1} \in \lvert \mathcal{S} \rvert$)

