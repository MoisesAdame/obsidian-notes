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
Given an epistemic state $\mathcal{K}$ with a world $W$ we say that $X$ is a possible world set wrt $W' \subseteq W$ if $X$ is the *minimal P-Stable Set* wrt $$
