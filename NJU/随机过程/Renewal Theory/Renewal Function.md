---
tags:
  - stochastic-process
  - renewal-process
---
Date: 2026-11-11 : 16:59
***
## Definition
### For this, we need to prove that $\mathbb{E}[X] =\sum_{k = 1}^\infty P\{ X \geq k \}$
$$
\begin{align}
\mathbb{E}[X]
= & \sum_{k =1}^\infty k P\{ X = k \} \quad & \text{(1)}\\
= & \sum_{k =1}^\infty  \underbrace{P\{ X = k \} + P\{ X = k \} + \cdots + P\{ X = k \}}_{k \text{ times}}\quad & \text{(2)} \\
= & \sum_{k =1}^\infty \sum_{n = 1}^kP\{ X = k \} \\
= & P\{ X = 1 \} + \quad & \text{(3)}\\
& P \{ X = 2 \} + P \{ X = 2 \}+ \\
& P \{ X = 3 \} + P \{ X = 3 \} + + P \{ X = 3 \} + \\
& \vdots \\
= & P\{ X\geq 1 \} + P\{ X\geq 2 \} + P\{ X\geq 3 \} + \cdots \quad & \text{(4)}\\
= & \sum_{k = 1}^\infty P\{ X\geq k \}
\end{align}
$$

1. Definition of expected value.
2. $k P\{ X = k \}$ is the same as summing $P\{ X = k \}$, $k$ times.
3. Sum the colums 
4. Express them as probability of $X\geq$

### Proof of $m(t)$
$$
\begin{align}
m(t) = & \mathbb{E}[N(t)] \\
= & \sum_{k = 1}^\infty P\{ N(t) \geq k \} & \quad \text{(1)}\\
= & \sum_{k = 1}^\infty P\{ S_{k} \leq t \} & \quad \text{(2)}\\
= & \sum_{k = 1}^\infty F_{k}(t) \quad & \text{(3)}\\
\end{align}
$$

1. Use the identity we just proved.
2. Use $N(t)\geq n \iff S_{n}\leq t$
3. Use $P\{ S_{n}\leq k\} =F_{n}(t)$, where $F_{n}$ is the nth convolution of the distribution F.

## Properties
- Uniquely determines the renewal process. One To One correspondance between the interrarival distributions $F$ and the mean value $m(t)$.
- $m(t) < \infty$ for all $t < \infty$

## Renewal Function
$$
\begin{align*}
\mathbb{E}[N(t)]
& = \mathbb{E}[\mathbb{E}[N(t) | X_{1}]]\\
& = \int_{0}^\infty \mathbb{E}[N(t) | X_{1} = x]f(x)dx
\end{align*}
$$