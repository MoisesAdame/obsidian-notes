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
Given the following image:

![[NJU/随机过程/Renewal Theory/images/image-1.png|500]]

We can see that:
$$
N(t) \geq n \iff S_{n} \leq t
$$

Because between the moment $t$ and $S_{n}$ can happen more events, that is why the lower bound for $N(t)$ is $n$.

$$
\begin{align}
P\{ N(t) = n \} 
& = P\{ N(t) \geq n \} - P\{ N(t) \geq n+1 \} & \quad \text{(1)}\\
& = P\{ S_{n}\leq t \} - P\{ S_{n+1} \leq t \} & \quad \text{(2)} \\
& = F_{n}(t) - F_{n+1}(t) & \quad \text{(3)} \\
\end{align}
$$

2. Comes from $N(t) \geq n \iff S_{n} \leq t$, where $P(N(t) \geq n) = P(S_{n} \leq t)$.
3. Because $S_{n} = X_{1} + X_{2} + \cdots + X_{n}$ and all the X's are distribuited identically with respect to distribution $F$, then $P\{ S_{n}\leq t \}=P\{  X_{1} + X_{2} + \cdots + X_{n}\leq t \}$, which is a sum of different random variables, thus $F_{n}$ is the nth convoluyion of $F$.

## The mean value/renewal function $m(t)$ of $N(t)$
Notes: [[Renewal Function]]