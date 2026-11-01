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

#### Forgetting as Progression
##### Definition 1: Preidcate
- Why? Because if we forget a predicate, we have a new theory that will entail new conlusions (weaker conclusions).
- Syntactically: $forget(P, \phi) \equiv \exists V.\phi^P_{V}$ (This $V$ is a second order variable that we can choose to be true).
- Example: If $\phi = P(a) \land Q(b)$, then we substitute all the P's for V's $forget(P, \phi) \equiv \exists V.(V(a) \land Q(b)) \equiv Q(b)$)

#### Defining Progression with FOL
It has been showed that this can be done wehn the SSA's are either:
- Strongly Context Free: 
- Local Effect:

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


## Questions
### Section 2.2
1. In definition of Basic action theory, what is the difference the initial situation $s_{0}$ the initial theory $\Sigma_{0}$?



