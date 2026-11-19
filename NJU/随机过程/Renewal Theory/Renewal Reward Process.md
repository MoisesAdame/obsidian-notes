---
tags:
  - stochastic-process
  - renewal-reward-process
---
Date: 2026-11-13 : 12:16
***
## Definition
A **renewal reward process** $\{ R(t), t\geq 0 \}$ is a renewal process $\{ N(t), t\geq 0 \}$, having interarrival times $X_{n}, n\geq1$ such that every time a renewal occurs, we get a reward $R_{n}$. With the following properties:
1. Rewards are iid.
2. Reward may be dependent on $X_{n}$

The total earned rewards by time $t$ is:
$$
R(t) = \sum_{i=1}^{N(t)} R_{i}
$$
---
## Proposition 1
### Statement
If $\mathbb{E}[R]<\infty$ and $\mathbb{E}[X]<\infty$, then:
1. $\lim_{ t \to \infty } \frac{R(t)}{t} = \frac{\mathbb{E}[R]}{\mathbb{E}[X]}$
2. $\lim_{ t \to \infty } \frac{\mathbb{E}[R(t)]}{t}=\frac{\mathbb{E}[R]}{\mathbb{E}[X]}$

### Proof of 1
Reqriting, we get:
$$
\frac{R(t)}{t} = \frac{\sum_{i=1}^{N(t)} R_{i}}{N(t)} \cdot \frac{N(t)}{t}
$$

By the **strong law of large numbers**, when $t\to \infty$, $\frac{\sum_{i=1}^{N(t)} R_{i}}{N(t)}=\mathbb{E}[R]$

By **proposition 1** from [[Elementary Renewal Theorem]], we know that $t\to \infty$ $\frac{N(t)}{t} = \frac{1}{\mathbb{E}[X]}$, that is why:
$$
\lim_{ t \to \infty } \frac{R(t)}{t} = \frac{\mathbb{E}[R]}{\mathbb{E}[X]}
$$



