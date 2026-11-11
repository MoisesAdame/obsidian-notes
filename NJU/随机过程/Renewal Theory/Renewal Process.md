---
tags:
  - stochastic-process
  - renewal-process
---
Date: 2026-11-11 : 15:27
***
## Definition
A counting process $\{ N(t), t\geq 0 \}$ whose interarrival times ($X_{1}, X_{2},\dots,X_{n}$) are independent and identically distributed wrt to a distribution $F$.

Denote $S_{n} = X_{1} + X_{2} + \cdots + X_{n}$

## When $n\to \infty$
By the **Law of Large Numbers**, given the fact that $\mu = \mathbb{E}[X_{k}], k\geq 1$, we have:
$$
P\left( \lim_{ n \to \infty }\frac{S_{n}}{n} \right) = P\left( \lim_{ n \to \infty }\frac{X_{1} + X_{2} + \cdots + X_{n}}{n} \right) =\mu
$$

## When $t\to \infty$, can I have finite events?
$$
\begin{align*}
P\{ N(\infty) < \infty \}
& = P\{ X_{n} = \infty \text{ for some } n\} \quad &(1)\\
& = P\left\{ \bigcup_{i = 1}^\infty \{ X_{i}=\infty \}\right\}\quad &(2)\\
& \leq \sum_{i=1}^\infty P\{ X_{i}=\infty \}\quad &(3)\\
& = 0 \quad &(4)\\
\end{align*}
$$

1. We are assuming that we had $n$ finite events. And that the time between some of them was infinite.
2. Because we said *some* is the same as saying *or*.
3. Boole's Inequality $P(A \cup B) \leq P(A) +P(B)$
4. Given that we assume that the interrarrival times are finite, the probabiliy of them being infinite is 0.

**Conclussion**: Its impossible to have finite events when time tens to infnity.

## Distribution of $N(t)$


