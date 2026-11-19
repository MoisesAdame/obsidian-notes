---
tags:
  - stochastic-process
  - renewal-process
---
Date: 2026-11-11 : 16:59
***

## 1. Useful Identity: $\mathbb{E}[X] = \sum_{k=1}^\infty P\{X \geq k\}$

For a non-negative integer-valued random variable $X$,

$$
\mathbb{E}[X] = \sum_{k=1}^\infty k\,P\{X = k\}.
$$

Rewrite $k\,P\{X=k\}$ as $P\{X=k\}$ summed $k$ times:

$$
\mathbb{E}[X]
= \sum_{k=1}^\infty \sum_{n=1}^k P\{X=k\}.
$$

Now sum **column-wise** instead of row-wise. The term $P\{X=k\}$ appears once for every $n \le k$, i.e. once in each row $k \ge n$. Summing over $k \ge n$ first gives

$$
\mathbb{E}[X]
= \sum_{n=1}^\infty \sum_{k=n}^\infty P\{X=k\}
= \sum_{n=1}^\infty P\{X \ge n\}.
$$

Equivalently, writing it out:

$$
\begin{aligned}
& P\{X=1\} \\
& P\{X=2\} + P\{X=2\} \\
& P\{X=3\} + P\{X=3\} + P\{X=3\} \\
& \vdots
\end{aligned}
$$

Column $n$ sums to $P\{X \ge n\}$. Hence

$$
\boxed{\mathbb{E}[X] = \sum_{k=1}^\infty P\{X \geq k\}}.
$$

---
## 2. The Renewal Function $m(t)$

Let $N(t)$ be the number of renewals by time $t$, $S_k$ the time of the $k$-th renewal, and $F_k$ the distribution of $S_k$ (the $k$-th convolution of the interarrival distribution $F$).

$$
\begin{aligned}
m(t) &= \mathbb{E}[N(t)] \\
&= \sum_{k=1}^\infty P\{N(t) \geq k\} && \text{(by the identity above)} \\
&= \sum_{k=1}^\infty P\{S_k \leq t\} && \text{(since } N(t)\ge k \iff S_k \le t\text{)} \\
&= \sum_{k=1}^\infty F_k(t) && \text{(definition of } F_k\text{)}.
\end{aligned}
$$

---
## 3. Properties

- **Uniqueness:** $m(t)$ uniquely determines the renewal process. There is a one-to-one correspondence between the interarrival distribution $F$ and the mean value function $m(t)$.
- **Finiteness:** $m(t) < \infty$ for all $t < \infty$.

---
## 4. The Renewal Equation

### Statement

$$
m(t) = F(t) + \int_0^\infty m(t-x)\,f(x)\,dx,
$$

where $F$ is the interarrival distribution and $f$ its density (assuming $F$ is continuous).

### Proof

Assume $F$ is continuous with density $f$. By the [[Law of Total Expectation]],

$$
\mathbb{E}[N(t)] = \mathbb{E}\big[\mathbb{E}[N(t) \mid X_1]\big]
= \int_0^\infty \mathbb{E}[N(t) \mid X_1 = x]\,f(x)\,dx.
$$

A renewal process probabilistically starts over when a renewal occurs, therefore:
$$
\mathbb{E}[N(t) \mid X_1 = x] = 1 + \mathbb{E}[N(t-x)] \quad (x \le t).
$$
- $+1$ comes from the fact that one event already happend.

Therefore,

$$
\begin{aligned}
m(t)
&= \int_0^t \big(1 + m(t-x)\big)\,f(x)\,dx \\
&= \int_0^t f(x)\,dx + \int_0^t m(t-x)\,f(x)\,dx \\
&= F(t) + \int_0^\infty m(t-x)\,f(x)\,dx,
\end{aligned}
$$

where the last step uses $f(x) = 0$ for $x < 0$ (so the upper limit can be extended to $\infty$) and $m(t-x) = 0$ for $x > t$.
