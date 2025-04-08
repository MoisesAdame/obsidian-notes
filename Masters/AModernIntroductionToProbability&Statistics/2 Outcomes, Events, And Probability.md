---
tags:
  - probability
  - probability/sample-space
  - probability/event
  - probability/probability-function
---
Date: 2024-11-19 : 12:30
***
## 2.1 Sample Spaces
>[!NOTE] Definition of Sample Space
>The set of possible outcomes of an experiment.

**Example:** For a coin toss, $\Omega = \{ H, T \}$

## 2.2 Events
>[!NOTE] Definition of Event
>A subset of the sample space.

**Example:** When asking the month of a birthday of a set of people, while all the months are the sample space, $A = \{ Jan, Oct, Dec \}$ is a possible event because $A \subset \Omega$.

## 2.3 Probability
In general, we want to express how likely it is that an event occurs, that is done trough a *probability function*.

>[!NOTE] Definition of a Probability Function (Finite Sample Space)
>A *probability function $P$* on a finite sample space $\Omega$ assigns to each event $A \subset \Omega$ a number $0 \leq P(A) \leq 1$ such that:
>1. $P(\Omega) = 1$
>2. $P(A \cup B) = P(A) + P(B)$ if $A$ and $B$ are disjoint.

If $A$ and $B$ are not disjoint, to compute probabilities we have to use the following rule: $A = (A \cap B) \cup (A \cap B^{C})$, thus:
$$
P(A) = P(A \cap B) + P(A \cap B^{C})
$$

### The Probability of a Union
We know that $A \cup B = B \cup (A \cap B^{C})$, thus:
$$
P(A \cup B) = P(B) + P(A \cap B^{C})
$$
Considering the previous identity, we get:
$$
P(A \cup B) = P(B) + P(A) - P(A \cap B)
$$

Additionally we know that $A \cup A^{C} = \Omega$, which means:
$$
P(A) + P(A^{C}) = P(\Omega) = 1 \implies P(A) = 1 - P(A^{C})
$$


## 2.4 Products of Sample Spaces
Sometimes experiments are performed more than once, when that is the case we have to perform a **cartesian product** between the sample spaces, that is:
$$
\Omega = \Omega_{1} \times \Omega_{2} = \{ (\omega_{1}, \omega_{2}) : \omega_{1} \in \Omega_{1}, \omega_{2} \in \Omega_{2} \}
$$

If the experiments are not mutually influenced, and every scenario is equally likely, if $|\Omega_{1}| = r$ and $|\Omega_{2}| = s$, then the probability for any  scenario to occur is:
$$
P(\{ (\omega_{x}, \omega_{y} )\}) = \frac{1}{rs}
$$

## 2.5 An Infinite Sample Space
This can happen for example in an experiment of *how many coin tosses, until we get tails*. Here the sample space is $\Omega = \mathbb{N} - \{ 0 \}$. What is the probability function for this scenario?

Let generalize it to $n$, where $(H, H, H, \dots, T)$, our sample space would be:
$$
\Omega = \{ H, T \} \times \{ H, T \} \times \cdots \times \{ H, T \}
$$

Considering that the probability of getting tails is $p$ and getting head is $1 - p$, we get:
$$
P(\{ n \}) = p (1-p)^{n - 1}
$$

Now, how would you calculate $P(\Omega)$? Thats were the definition of P is extended:

>[!NOTE] Definition of a Probability Function (Infinite Sample Space)
>A *probability function* on an infinite sample space $\Omega$ assigns to each event $A$ in $\Omega$ a number $P(A)$ in $[0, 1]$, such that:
>1. $P(\Omega) = 1$
>2. $P\left( \bigcup_{i = 1}^{\infty}A_{i} \right) = \sum_{i = 1}^{\infty}P(A_{i})$ if $A_{1}, A_{2}, A_{3}, \dots$ are disjoint.

## 2.6 Exercises
Here: [[2 Exercises]]
