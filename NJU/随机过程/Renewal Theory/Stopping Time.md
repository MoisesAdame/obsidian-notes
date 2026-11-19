---
tags:
  - stochastic-process
  - stopping-time
---
Date: 2026-11-12 : 12:52
***
## Definition
A random variable $N$ is the **stopping time** of a series of random iid variables   $X_{1}, X_{2},\dots$ if the event $\{ N = n \}$ is independent of $X_{n+1}, X_{n+2}, \dots$ (Thus is dependent of $X_{1}, X_{2},\dots X_{n}$ ).

---
## Wald's Equation
### Statement
Let $X_{1}, X_{2},\dots$ be a series of iid random variables whose expected value is $\mathbb{E}[X] < \infty$ (finite) , $N$ is their stopping time and the expectation of the stopping time is $\mathbb{E}[N] < \infty$ (finite)
$$
\mathbb{E}\left[ \sum_{i = 1}^{N}X_{i} \right] =\mathbb{E}[N]\mathbb{E}[X]
$$

### Proof
Let:
$$
\mathbb{I}_{n} =
\begin{cases}
1 \quad \text{if } n\leq N \\
0 \quad \text{if } n > N
\end{cases}
$$
Then we can say that:
$$
\sum_{i = 1}^{N}X_{i} = \sum_{i = 1}^{\infty}X_{i}\mathbb{I}_{i}
$$

Taking the expected value of both sides
$$
\mathbb{E}\left[ \sum_{i = 1}^{N}X_{i} \right] = \mathbb{E}\left[ \sum_{i = 1}^{\infty}X_{i}\mathbb{I}_{i} \right]
$$

We know that $\mathbb{E}\left[ \sum X \right] = \sum \mathbb{E}[X]$, so:
$$
\mathbb{E}\left[ \sum_{i = 1}^{N}X_{i} \right] =  \sum_{i = 1}^{\infty}\mathbb{E}\left[X_{i}\mathbb{I}_{i} \right]
$$

$\mathbb{I}_{n}$ pregunta $X_{n-1}$ ya paró? Si no, $\mathbb{I}_{n} = 1$, si si, $\mathbb{I}_{n} = 0$. Por lo tanto, $\mathbb{I}_{n}$ es independiente de $X_{n}$, entonces:
$$
\mathbb{E}\left[ \sum_{i = 1}^{N}X_{i} \right] 
= \sum_{i = 1}^{\infty}\mathbb{E}\left[X_{i} \right]\mathbb{E}[\mathbb{I}_{i}] 
= \sum_{i = 1}^{\infty}\mathbb{E}\left[X \right]\mathbb{E}[\mathbb{I}_{i}]
= \mathbb{E}\left[X \right] \sum_{i = 1}^{\infty}\mathbb{E}[\mathbb{I}_{i}]
$$

Again, because of $\mathbb{E}\left[ \sum X \right] = \sum \mathbb{E}[X]$
$$
\mathbb{E}\left[ \sum_{i = 1}^{N}X_{i} \right]
= \mathbb{E}\left[X \right] \mathbb{E}\left[ \sum_{i = 1}^{\infty}\mathbb{I}_{i} \right]
$$

Concluding that:
$$
\mathbb{E}\left[ \sum_{i = 1}^{N}X_{i} \right]
= \mathbb{E}\left[X \right] \mathbb{E}\left[ N \right]
$$

---
## Stoping Time for Renewal Process
Let $X_{1}, X_{2},\dots$ be arrival times, of a renewal process. If we stop at the first renewal after time $t$, that is $N(t) + 1$, then we would stop after observing $X_{1}, X_{2},\dots, X_{N(t)+1}$

Then we can say:
$$
N(t) + 1 = n \iff N(t) = n - 1 \iff X_{1} + X_{2}+ \cdots+X_{N(t)} \leq t,X_{1} + X_{2}+ \cdots+X_{N(t) + 1} < t 
$$

![[image-3.jpeg|500]]

We can say $N(t) + 1$ is the stopping time of this renewal process because it is **only dependent** on $X_{1}, X_{2},\dots, X_{N(t)+1}$.

### Corollary
Applying **Wald's Equation**, we get:
$$
\mathbb{E}[S_{N(t) + 1}] = \mathbb{E}[X] \mathbb{E}[N(t) + 1]
$$

