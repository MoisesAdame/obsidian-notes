---
tags:
---
Date: 2026-10-29 : 17:25
***
## How to Read
### First read
- Abtract + Section 1
- Section 2.2
- Section 3.1 + 3.2
- Section 4.1
- Section 4.2
- Section 4.2's final paragraph + Section 5

## Prerequisites
- [[Propositional Logic]]
- [[First Order Logic]]
- [[Situation Calculus]]
- [[Markov Networks]]

## Remarks
### Section 2.2
#### Definition: Basic Action Theory
Given a set of fluents $\mathcal{F} = \{ F_{1}, \dots, F_{n} \}$ a a BAT $\Sigma$ has:
- **Initial Theory $\Sigma_{0}$**: The initial set of fluents. (Closely related to the initial situation $s_{0}$).
- **Succesor State Axioms (SSA's) $\Sigma_{post}$**: $F(\vec{x}) \equiv \gamma^+(a, \vec{x}, s), \lor (F(\vec{x}, s) \land \gamma^-(a, \vec{x}, s))$ for every $F \in \mathcal{F}$. (Our axioms for each succesor tanking into accoun the frame problem)

#### Definition: Progression 
Given a Basic Action Theory $\Sigma_{0} \cup \Sigma_{post}$, $\Sigma_{0}'$ is the progressed theory if for every sentence $\phi$:
$$
\Sigma_{0} \cup \Sigma_{post} \models [t]\phi \iff \Sigma_{0}' \cup \Sigma_{post} \models \phi
$$

This definition can be seen from two perspectives (past = before progression, future = after progression):
- **Past Perspective**: The sentence $\phi$ holds after the action $t$ ($t[\phi]$) using the initial BAT.
- **Future Perspective**: We can entail  $\phi$ via the progressed BAT.

#### Theorem 2.6: Progression with SO Variables
The progression of $\Sigma_{0}$ wrt $t$ and $\Sigma_{post}$ is:
$$
\Sigma_{0}' =\exists \vec{V}.(\Sigma_{0})_{\vec{V}}^{\vec{F}} \land \bigwedge_{i} \forall \vec{x}. F_{i}(\vec{x}) \equiv (\gamma_{F_{i}}(\vec{x}, t))_{\vec{V}}^\vec{F}
$$

#### Forgetting as Progression
##### Definition 1: Preidcate
- Why? Because if we forget a predicate, we have a new theory that will entail new conlusions (weaker conclusions).
- Syntactically: $forget(P, \phi) \equiv \exists V.\phi^P_{V}$ (This $V$ is a second order variable that we can choose to be true).
- Example: If $\phi = P(a) \land Q(b)$, then we substitute all the P's for V's $forget(P, \phi) \equiv \exists V.(V(a) \land Q(b)) \equiv Q(b)$)

#### Defining Progression with FOL
It has been showed that this can be done wehn the SSA's are either:
- Strongly Context Free: $\gamma_{F}(\vec{x}, a) = \bigvee_{j}\exists \vec{u}_{j}.[a = A_{j}(\vec{u})_{j}]$
- Local Effect Condition: $\gamma_{F}(\vec{x}, a) = \bigvee_{j}\exists \vec{u}_{j}.[a = A_{j}(\vec{u})_{j} \land \phi_{j}(\vec{u}_{j})]$

#### Theorem 2.8: Forgetting a Predicate When There Is No Total Agreement
Let $\Delta = \{ t_{1}, \dots, t_{n} \}$ be a set of vector of ground terms, $P$ and $Q$ two predicates, $Q(\Delta)$ be the set $\{ Q(\vec{t}) | t \in \Delta \}$ and $P\approx_{\Delta} Q$ denote the formula $\vec{\forall}x \not\in \Delta \supset P(\vec{x}) \equiv Q(\vec{x})$. Then $forget(\phi \land P \approx_{\Delta}Q, Q) \iff forget(\phi, Q(\Delta))^Q_{P}$.

**Plain Words**: This means that if we have a sentence where the predicates $P$ and $Q$ totally agree (have the same truth value) ($\phi \land P \approx_{\Delta}Q$), except for a few ones ($Q(\Delta)$) and we forget all the $Q$'s. It is just the same as having the original sentence $\phi$ and forgetting all the not agreeing $Q$'s ($Q(\Delta)$) and then substituting all the $Q$'s for $P$'s.

**Example**:
$P$: $\text{sleeping}()$
$Q$: $\text{snoring}()$
$\phi$: $\text{sleeping}(petsock) \land \neg \text{snoring}(petsock)$
$\Delta$: $\{ petsock \}$
$P\approx_{\Delta}Q$: $\forall x \neq petsock \supset \text{sleeping}(x) \equiv \text{snoring}(x)$
$\phi \land P\approx_{\Delta}Q$: $\text{sleeping}(petsock) \land \neg \text{snoring}(petsock) \land \forall x \neq petsock \supset \text{sleeping}(x) \equiv \text{snoring}(x)$

### Section 3.1
#### Probabilistic Knowledge Base (PKB)
A set of static subjective fluent formulas without nested $\mathbf{B}$.
- Static: Current state. There is no $[a]$ or $\square$.
- Subjective: What the agent believes, not the objective world.
- No nested: There are no $\mathbf{B}(\mathbf{B(\theta : r_{1})}, r_{2})$

##### Types of PKBs
###### Fact-Independent PKB (FI-PKB)
It has a two theories:
- $T=\{ \mathbf{B}(\alpha_{1}:n_{1}), \dots, \mathbf{B}(\alpha_{k}:n_{k}) \}$.
- $T_{ind}$

Where:
- $T$ tells uss each fact $a_{i}$ is believed with a probability $n_{i}$.
- $T_{ind}$ tells us that the facts are *mutually independent*.

**NOT CLOSED UNDER PROGESSION**: Because adding new facts might add independencies between them.

###### World Representation PKB (WR-PKB)
 It has one theory:
- $T = \{ \mathbf{B}(\theta:r_{\theta}) : \theta \in \Theta\}$

Where:
- $\theta = \beta_{1} \land \beta_{2} \land \dots \land  \beta_{k}$.
- $\beta_{i} = \{ \alpha_{i}, \neg\alpha_{i} \}$ either our fact is true or false.
- $\Theta$ is all the possible combinations of $\theta$'s. There should be $2^k$.
- $r_{\theta}$ is the probability for each combination $\theta$.


## Questions
### Section 2.2
1. In definition of Basic action theory, what is the difference the initial situation $s_{0}$ the initial theory $\Sigma_{0}$?
2. How do you go from Theorem 2.6 to Theorem 2.9.

### Section 3.1
1. Are FI-PKB and WR-PKB the only types of PKB's?
2. Are WR-PKB closed under progression? If so, why?




