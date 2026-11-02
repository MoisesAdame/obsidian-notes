---
tags:
  - first-order-logic
  - second-order-logic
---
Date: 2026-11-02 : 16:37
***
## Chapter's Tip
Reference material. You need: many-sorted logic and the reduction to unsorted logic, and **second-order logic for inductive definitions** (smallest set / intersection of all sets). This is why the foundational axioms and the `Do` macro for iteration are second-order. Skim 2.1 if you're comfortable; read 2.2.3 carefully.

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
##### Structure
A **structure** $\mathcal{S}$ (also called *interpretation*) is a function whose domain are the *parameters* (functions, predicates) of our language. For isntance $S(P)$ gives us the tuples where $P$ is true and $S(f)$ returns the actual function.

It is defined by:
1. The universe: $\lvert \mathcal{S} \rvert$
2. For $n$-ary predicates: $P^\mathcal{S}\subseteq \lvert \mathcal{S} \rvert^n$ (all the combinations where predicate $P$ is true).
3. For $n$-ary functions: $f^\mathcal{S} : \lvert \mathcal{S} \rvert^n \to \lvert \mathcal{S} \rvert$ (for example in situation calculus actions are functions, thus $a_{1} = \text{PickUp}(x, y)$, where $a_{1} \in \lvert \mathcal{S} \rvert$)

$\models_{\mathcal{S}} \sigma$: A sentence $\sigma$ is true on the struecture $\mathcal{S}$.

##### Attributes of a Sentence
- **Satisfiability**: A structure $\mathcal{S}$ satisfies $\sigma$ iff $\models_{\mathcal{S}} \sigma[s]$ for all $s$. In this case $s$ is a function defined as $s: V \to \lvert \mathcal{S} \rvert$ where $V$ are the variables. 
- **Models**: A structure $\mathcal{S}$ models $\sigma$ iff $\mathcal{S}$ satisifes $\sigma$.
- **Validity**: $\sigma$ is valid, written as $\models \sigma$ iff all the structures of our FOL are models of $\sigma$.
- **Unsatisfiability**: iff it has no models.
- **Logical Entailment**: Let $\Gamma$ be a set of sentences. $\Gamma \models \sigma$ iff evry model of $\Gamma$ is a model of $\sigma$.

##### Many-Sorted First Order Languages
The universe of our FOL is partitioned into **disjoint sub-universes**, for example one partition for variables, one for terms.

In situation calculus, this happens for situations, actions and other things.


