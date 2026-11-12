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

## Frame Problem: Pednault Proposal
### Example
We have the following *state* axioms for different lights that whose state is moddled by `on()` and the action that affects this is `flip()`, thus:
$$
on(x, s) \land x = y \supset \neg on(x, do(flip(y), s))
$$
$$
\neg on(x, s) \land y = x \supset on(x, do(flip(y), s))
$$

Now let say that both $on(x, s)$ and $\neg on(x, do(flip(y), s))$ are true. Because the axioms are always true, the only way for $\neg on(x, do(flip(y), s))$ to be true is that $on(x, s) \land x = y$ was true. We can see it in the following way:
$$
A = on(x, s) \land x = y, \quad B = \neg on(x, do(flip(y), s))
$$

Because they are an axiom, we know:
$$
A \to B \equiv T
$$

Then, for $B$ to be true, by the truth table, $A$ can have any value. But because of the axioms **ONLY** if $on(x, s) \land x = y$ is true, then $\neg on(x, do(flip(y), s))$ is also true.

Then our conclusion is:
$$
on(x, s) \land \neg on(x, do(flip(y), s)) \supset on(x, s) \land x = y
$$

Then if we say $P: on(x, s)$, $\neg Q: \neg on(x, do(flip(y), s))$ and $R: x=y$, thenwe have:
$$
\begin{align*}
& P \land \neg Q \supset P\land R\\
& \implies \neg(P \land \neg Q ) \lor ( P\land R)\\
& \implies \neg P \lor Q \lor ( P\land R)\\
& \implies (\neg P \lor Q \lor P) \land (\neg P \lor Q \lor R) \\
& \implies (T\lor Q ) \land (\neg P \lor Q \lor R) \\
& \implies T \land (\neg P \lor Q \lor R) \\
& \implies \neg P \lor Q \lor R \\
& \implies \neg (P \land \neg R) \lor Q \\
& \implies P \land \neg R \supset Q \\
\end{align*}
$$
Which means:
$$
on(x, s) \land x \neq y \supset on(x, do(flip(y), s))
$$

This is a **frame axiom** because it tells you that light $x$ remains on when you flip another light $y$.

### Generalization
Given the following positive and negative *state axioms* for the action $A(\vec{y})$ and the fluent $F(\vec{x}, s)$:
$$
\varepsilon_F^+(\vec{x}, \vec{y}, s) \supset F(\vec{x}, do(A(\vec{y}), s)) \quad \text{(P.1)}
$$
$$
\varepsilon_F^-(\vec{x}, \vec{y}, s) \supset \neg F(\vec{x}, do(A(\vec{y}), s)) \quad \text{(P.2)}
$$

If we let $F(\vec{x}, s)$ and $\neg F(\vec{x}, do(A(\vec{y}), s))$ to be true, then we can conclude that:
$$
F(\vec{x}, s) \land \neg F(\vec{x}, do(A(\vec{y}), s)) \supset \varepsilon_F^-(\vec{x}, \vec{y}, s)
$$

Which can be retwritten as: **A FRAME AXIOM**
$$
F(\vec{x}, s) \land \neg \varepsilon_F^-(\vec{x}, \vec{y}, s) \supset F(\vec{x}, do(A(\vec{y}), s))
$$

For the possitive case we can say:
$$
\neg F(\vec{x}, s) \land \neg \varepsilon_F^+(\vec{x}, \vec{y}, s) \supset \neg F(\vec{x}, do(A(\vec{y}), s))
$$

This frame axioms can only be optained by the **Causal Completness Assuption**, whic states that the axioms (P.1) and (P.2) specify all the casual laws that relate action $A$ and fluent $F$

### The Problem
If there is no relation between one action and one fluent, we have to do something like this:
$$
false \supset broken(x, do(paint(y, c), s))
$$

Which is basically the same as enumerating all of the frame axioms.

## Frame Problem: Reiter's Solution
### Example 1
For the fluent `broken(x,s)` we have the following *positive effect axioms*:
$$
fragile(x) \supset broken(x, do(drop(r, x), s))
$$
$$
nextTo(x, b, s) \supset broken(x, do(explode(b)))
$$

We can rewrite them as a logical expression:
$$
\begin{align}
[(\exists r) & [a = drop(r, x) \land fragile(x)] \\
& \lor (\exists b)  [a = explode(b) \land nextTo(x, b, s)]]\\ 
& \supset broken(x, do(a, s))
\end{align}
$$

For the *negative effect axioms* we have:
$$
\neg broken(x, do(repair(r, x), s))
$$

Written as a logical expression:
$$
(\exists r)[a = repair(r, x)] \supset \neg broken(x, do(a, s))
$$

Supposing that $\neg broken(x, s)$ and $broken(x, do(a, s))$ are true, then $[(\exists r)  [a = drop(r, x) \land fragile(x)]  \lor (\exists b)  [a = explode(b) \land nextTo(x, b, s)]]$ must be true, letting us conclude that:
$$
\begin{align}
\neg broken(x, s) \land & broken(x, do(a, s)) \supset \\
&[(\exists r)  [a = drop(r, x) \land fragile(x)]  \lor (\exists b)  [a = explode(b) \land nextTo(x, b, s)]]
\end{align}
$$

Which is a **Explanation Closure Axiom**.

### Example 2
We wrote all the **positive effect axioms** in just one logical expression:
$$
\begin{align}
[(\exists r) & [a = drop(r, x) \land fragile(x)] \\
& \lor (\exists b)  [a = explode(b) \land nextTo(x, b, s)]]\\ 
& \supset broken(x, do(a, s))
\end{align}
$$

We can rewrite this in a more general way for **positive** and **negative effect axioms**:
$$
(+) \quad \gamma_{F}^+(\vec{x}, a, s) \supset F(\vec{x}, do(a, s))
$$
$$
(-) \quad \gamma_{F}^-(\vec{x}, a, s) \supset \neg F(\vec{x}, do(a, s))
$$
### Transformation of Effect Axioms to Normal Form
