---
tags:
---
Date: 2026-10-20 : 20:09
***
## General Glossary 
### First Order Logic


### Belief State
The database. Its not a set of **logically independent facts**, instead it is a set of **axioms** that can help derive others.

What is accepted in it are not only the sentences but also their **lofical consequences**.

### Belief Revision
A **belief state** (a database) is a set of sentences considered true. When we encounter new knowledge, we can add it to our database, but adding this knowledge, impies that we have to **revise** our previous knowledge.

A belief revision **occurs** when a new piece of information that is **inconsistent** is added to the belief state.

### Belief Changes
#### (i) Expansion $K + \phi$
A new sentence $\phi$ is added to the belief system $K$.

Definition: $K+\phi = \{\psi : K \cup \{\phi\} \models \psi\}$
#### (ii) Revision $K*\phi$
A new sentence $\phi$ (that is inconsistent) with the belief system $K$ is added and old sentences are dropped.

#### (iii) Contraction $K\div\phi$
No new facts are added, we just drop some (maintaining logical closure).

### Logical Entailment and Logical Consequences of a Belief State
#### Logical Entailment $K\models\phi$
Means that $\phi$ is a logical consequence of $K$.

#### Logical Consequences $Cn(K)$
The output of this function is the set of all logical consequences of $K$.

$Cn(K) = \{ \phi : K\models\phi  \}$

#### Closed Under Logical Consequences
If $K \models \phi$, then $\phi \in K$. That is $\phi$ is **accepted** in $K$.
If $\neg \phi \in K$. That is $\phi$ is **rejected** in $K$.

### The Eight AGM Revision Postulates
#### 1. Closure
If $\phi$ is a sentence and $K$ a belief set, then $K*\phi$ is a belief set.

#### 2. Success
The new information must be accepted: $\phi \in K*\phi$.

#### 3. Inclusion
Revision should involve minimal change $K*\phi \subseteq K+\phi$.

#### 4. Vacuity
Formula: $\neg \phi \not\in K\implies K+\phi \subseteq K*\phi$

Plain words: If our new sentence doesn't contradict what we already believe, then revising $K$ with respect to $K$ is the same as just expand $K$ with respect to $\phi$. We don't have to drop anything.
#### 5. Consistency
If $\phi$ is *logically impossible* ($\vdash \neg \phi$), then it's revision produces a inconsistent belief set $K_{\bot}$.

Formula: $K*\phi = K_{\bot} \iff \vdash \neg \phi$.

#### 6. Extensionality
If $\phi \equiv \psi$ (logically equivalent), then $K*\phi = K*\psi$.

The other postulates are more complex.

## Paper's Glossary
### P-Stable Set
Given a world $W$ and a subset $X \subseteq W$, we say that $X$ is **P-Stable** if $\forall w \in X$ then, $P(w) > P(W-X)$

Given $W'\subseteq W$, then we say that for a given $X \subseteq W'$, $X$ is **P Stable wrt $W'$** if $\forall w \in X \implies P(w) > P(W' - X)$.

### PW-belief set
Given an epistemic state $\mathcal{K}$ with a world $W$ we say that $X$ is a possible world set wrt $W' \subseteq W$ if $X$ is the *minimal P-Stable Set wrt $W'$* is $X$ (minimal maeans with the lesser amount of elements).

### Induced total preorder $\preceq_{\mathcal{K}}$
Let $K = \left\langle W, P\right\rangle$ be an epistemic state, then its **induced total preorder** $\preceq_{\mathcal{K}} = \{ W_{0}, W_{1}, \dots, W_{n} \}$. Where $K_{0}$ is the pw-belief set wrt W. And $W_{i}$ is pw-belief set wrt $W - \bigcup_{0}^{i-1}W_{i}$.

### Jeffrey's Rule
Jeffreys rule is just a way of updating one given one world $w$'s probability.

It comes from the *law of total probability*, where$P(B) = P(B,A) + P(B,W-A) = P(A)P(B|A) + P(W-A)P(B|W-A)=P(A)P(B|A) + (1-P(A))P(B|W-A)$.

If we receive evidence that the new probability $P(A) = s$, then:
$$
P(B) = sP(B|A) + (1-s)P(B|W-A)
$$

Then we have:
$$
P(w) = \begin{cases}
\frac{sP(w)}{P(A)} & w \in A \\
\frac{(1-s)P(w)}{1-P(A)} & w \not\in A
\end{cases}
$$

In this case is said to be a *proposition*, but in the context of this paper, a proposition is a set of worlds, for example $[\phi]$.

### Constraints C1 and C2

### Faithful Assignment
#### Example
Let's say we have a set of *atomic formulas* $\mathcal{P} = \{ a, b \}$. In that case we have the following worlds $W=\{ \emptyset, \{ a \}, \{ b \}, \{ a, b \} \}$. They can be written as 00, 10, 01, 11.

Now let's say we calculated the **total preorder** $\preceq_{\mathcal{K}}={10, 01} ≻ {00} ≻ {11}$

Lets say now we pick a *belief set* (a set of formulas closed under deduction) $K = Cn(\{ a \vee b \})$, thus $[K] = \{ 11, 01, 10 \}$. Now we have to ask, is our preorder faithful to this?

The answer is **NO** because given $11 \in K$ and $00 \not\in K$, this does not hold: $11 \preceq_{\mathcal{K}} 00$. Because here we are saying 11 is better than 00, and in fact, in our total preorder 00 is better than 11.

**NOTE!** Do not read $\preceq$ as lesser or equal $\leq$.

#### Definition
A faithful assignment is a *total preorder* for a belief set $K$ ($\preceq_{K}$) satisfying the following properties:
1. if $w, w'\in[K]$, then $w \preceq_{K} w'$



