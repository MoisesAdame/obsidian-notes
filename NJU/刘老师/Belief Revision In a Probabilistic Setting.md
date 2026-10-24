---
tags:
---
Date: 2026-10-24 : 10:20
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
1. if $w, w'\in[K]$, then $w' \preceq_{K} w$. Members have to be in the **same layer**.
2. If $w \in [K]$ and $w' \not\in [K]$, then $w \prec_{K} w'$.

### Katsuno-Mendelson Theorem
#### Definition
A revision operator $*$ satisifies the AGM Conditions (1 - 8) iff there exists a faithful assignment that maps each belief set $K$ to a total peorder $\preceq_{K}$, such that:
$$
[K*\phi] =min([\phi],\preceq_{K})
$$

**NOTE:** This min() is now the smallest out of two numbers.

**Real Definition:**
$$
min([\phi],\preceq_{K}) = \{ w \in W : w\models\phi \text{ and } \nexists w' \in [\phi] st. w' \prec_{K}w\}
$$



## Summary
### Part 1: The problem & The Belief Notion
The **paper's central question** is, can *qualitative* AGM belief revision (the formulas and postulates), and its iterated revision (PD postulates) be recovered from a purely probabilistic (*quantitative*) semantics? 

For instance in this context an **epistemic state** is defined as a tuple $\mathcal{K}=\langle W,P\rangle$, where $W=2^{ \mathcal{P} }$ are the wolrds and $\mathcal{P}$ are the atomic formulas. Aditionnaly $P$ are the probabilities associated to the worlds $W$.

Let $W' \subseteq W$ and $X\subseteq W'$. If for all $w \in X, P(w)> P(W'\setminus X)$, then we can say **$X$ is P-stable with respect to $W'$**. Aditionally, if $W'=W$, then **$X$ is P-stable**. The reason for it to exist is that $P(\phi)>0.5$ breaks conjunction.

Related to this concept, we have the notion of **pw-belief set**, whic basically is the *minimal* P-stable set. For minimal we refer to the set with the less amount of elements. Some important resul that we get related to pw-belief set is that the belief set $K=Cn(W_{0})$ is geven by all the logical consecuences of the pw-belief set wrt $W$.

### Part 2: The AGM Level Results
Given some epistemic state $\mathcal{K}$ we can induce a total preorder $\preceq_{\mathcal{K}} = \langle W_{0}, W_{1}, \dots, W_{n}\rangle$ where $W_{0}$ is the *pw-belief set* and $W_{i}$ is the pw-belief set wrt $W\setminus \bigcup_{i=0}^{ i-1 }W_{i}$. Their **ordering** is the following: $w_{i}\preceq_{\mathcal{K}}w_{j} \iff w_{i} \in W_{i}, w_{j}\in W_{j}, i\leq j$.

**Theorem 12 (state to AGM)** tells us that if $K*\phi=Cn(min([\phi], \preceq_{K}))$, then $*$ satisfies the AGM postulates. **Theorem 13 (AGM to state)** tells us that given an $*$ that satisfies the AGM postulates, then the belief set $K$ is given by $K =Cn(W_{0})$. Together they form an iff.

Together, theorem 12 and 13 let us see that the AGM postulates are held iff our probabilistic construction is $K*\phi=Cn(min([\phi], \preceq_{K}))$

The relation between Theorems 12 and 13 and The KM Theorem is that Theorems 12 and 13 apply KM Theorem to the probabilistic setting.

### Part 3: The Dynamic Account (Jeffrey, C1/C2, Prop. 16, Thm 18)
The main taget of a revision by the epistemic level is that given our original epistmic state $\mathcal{K}=\langle W, P\rangle$, we obtain a new epistemic state $\mathcal{K'}=\langle W, P'\rangle$. Thus, after revising $\mathcal{K}$ by $\phi$, the new pw-belief set would be $min([\phi], \preceq_{\mathcal{K}})$

Jeffrey Conditioning help us update the world's probability. We use Jeffrey's rule that is defined as follows:

$$
P'(w) = \begin{cases}
\frac{s \cdot P(w)}{P(A)} & w\in A \\
\frac{(1-s) \cdot P(w)}{1- P(A)} & w\not\in A \\
\end{cases}
$$

In this case $s$ represents the *new probability assigned for $A$*. 

Now, the problem arises. How are we supposed to calculate $s$? This can be done by first properly defining our problem. We know that the new epistemic state's $W'_{0}=min([\phi], \preceq_{K})$. So, using this we can have two conditions:
1. **Condition 1:** $\forall w \in min([\phi], \preceq_{K}),  P'(w) > P'(W \setminus min([\phi], \preceq_{K}))$.
2. **Condition 2:** Given an $X' \subset min([\phi], \preceq_{K})$ $\forall x' \in X', P'(x')\leq P'(W \setminus X')$

By condition 1
We first have to question ourselves, what is $W$? We then can say that $W = [\neg \phi] \cup [\phi]$. Thus, $W \setminus min([\phi], \preceq_{K}) = [\neg \phi] \cup [\phi]\setminus min([\phi], \preceq_{K})$

Using this, we obtain $s$ lower bound.

By condition 2
We obtain $s$ upper bound.

Then, joing what we obtained from the calculation of $s$ upper and lower bounds, we can say that the feasability condition for a given formula $\phi$ being revised and accepeted by a epistemic state is that:
$$
P(w') - P(w) < P(min([\phi], \preceq_{\mathcal{K}}\setminus X')) 
$$

And when this condition fails, means that conditions **C1** and **C2** cannot be jointly satisfied, which implies that the Jeffrey's update cannot make $min([\phi], \preceq_{\mathcal{K}})$ be the new pw-belief set, which for instance makes the operator not satisfy all of the AGM postulates.

### Part 4: Iterated Revision (§4.4): DPW, Table 2, ε-device
#### Question 14
The main difference between **AGM and DP** is that the first one works with **belief sets** and the second onw, works with **total preorder $\preceq_{K}$**.

#### Question 15
The reason why the **probabilistic account cannot satisfy DPS1** is because that after applying Jeffrey's rule, the worlds that are not inside $[\phi]$ get two higher layers, so for instance if in the original belief set two worlds where in the same layer, but one of the was not in $[\phi]$, then, after applyingg Jeffreys rule the world that was inside and didn't belong to $[\phi]$ will be pushed up making the equation not hold.

In table two, we can see how before revision $w_{5}$ and $w_{7}$ both belong to the same layer, but after revision, $w_{5}$ and $w_{7}$ end up in different layers, making the equation not hold.

*dont know how to answer part c*

#### Question 16
The **independence towards revision** means that they belong to totally different layers in the total preorder.

The reason of existance of the **$\epsilon$ device** is that originally the probabilities of $w_{1}$ to $w_{4}$ summed 1, the sammed happend to the probabilities of $w_{5}$ to $w_{8}$. Now, in order for building a new epistemic state where we can have worlds from $w_{1}$ to $w_{8}$ we need their probabilitiers to sum 1so, by multiplying all the probabilities of the first group by $(1-\epsilon)$ and doing the same but with $\epsilon$, we get a new epistemic state that doesn't break any rules.

*dont know how to answer part c*

#### Question 17
*dont know how to answer part A*

It is weakend but just in the sense that instead of $\preceq_{\mathcal{K}}$, we have $\prec_{\mathcal{K}}$, but the implies stays the same.

**DPS4 does not need to be weakend** because $w_{1}$ is always going to be in a lower layer if $w_{2}$ does not belong to $[\phi]$. 

**DPW is weaker** because the worlds in the new epistemic state do not need to be in the same layer.

#### Question 18
Forces us to forget everything that we learned from $p_{1}, p_{2}, p_{2}, \dots,p_{100}$ and only learn that $\neg p_{1}$

*dont know how to answer part B*

## Synthesis
### What is the paper about?
The paper goes from a qualitative to a quantitative perspective in what revision is. It leverages AGM and DP postulates as well as Jeffrey's rule to express revision. The main result is that theorems 12 and 13 together show that $\mathcal{K} * \phi = Cn(min([\phi], \preceq_{\mathcal{K}})) \iff \text{Our operator holds for AGM postulates}$.

### The Static Theory
First we know that **P-stability** means that for all $w \in X$, int this case $X \subseteq W$, then $P(w) > P(W\setminus X)$, this leads to the definition of a **pw-belief set** which is basically the minimal p-stable set. Using this definitions, we can build on the new definition, that is the **total preorder**, which can be defined as $\preceq_{K} =\langle W_{0}, W_{1},\dots, W_{n}\rangle$, where $W_{0}$ is the pw-belief set wrt $W$ and for example $W_{3}$ is the pw-belief set wrt $W\setminus W_{0} \cup W_{1}\cup W_{2}$. Now, because of **KM Theorem**

