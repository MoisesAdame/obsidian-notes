---
tags:
  - stochastic-process
  - key-renewal-theorem
  - lattice-random-variable
  - blackwells-theorem
  - directly-riemann-integrable
---
Date: 2026-11-12 : 20:03
***
## 1. Lattice
A random variable $X$ is said to be a **lattice** ifthere exists a $d\geq0$ such that
$$
\sum_{n = 0}^\infty P\{ X=nd \} = 1
$$

The **largest d** with this property is the period of $X$.

It has this name, because the random variable takes the shape of a grid:
$$
0d, 1d,2d, 3d,\dots
$$

---
## 2. Blackwell's Theorem
### Statement
**If $F$ is NOT lattice**:
$$
\lim_{ t \to \infty } m(t+a) - m(t)=\frac{a}{\mu}
$$

**If $F$ is lattce with period d**:
$$
\lim_{ n \to \infty } \mathbb{E}[\text{number of renewals at } nd] = \frac{d}{\mu}
$$

### Sketch Proof
By the following diagram we know

![[image-6.jpg|400]]

$$
\begin{align}
S_{N(t) + 1}=t+Y(t) \\
S_{N(t+a) + 1}=t+a+Y'(t)
\end{align}
$$

Taking the expected value on both sides we get:
$$
\begin{align}
\mathbb{E}[S_{N(t) + 1}]=\mathbb{E}[t+Y(t)] \\
\mathbb{E}[S_{N(t+a) + 1}]=\mathbb{E}[t+a+Y'(t)]
\end{align}
$$

By Wald's Equation listed here [[Stopping Time]], we get:
$$
\begin{align}
\mathbb{E}[N(t) + 1]\mathbb{E}[X]=\mathbb{E}[t+Y(t)] \\
\mathbb{E}[N(t+a) + 1]\mathbb{E}[X]=\mathbb{E}[t+a+Y'(t)]
\end{align}
$$

This can be rewritten as:
$$
\begin{align}
\mu[N(t) + 1]=t+\mathbb{E}[Y(t)] \\
\mu[N(t+a) + 1]=t+a+\mathbb{E}[Y'(t)]
\end{align}
$$

Now, taking the difference of the equation from the bottom with the equation on the top:
$$
\mu[N(t+a) + 1] - \mu[N(t) + 1]=a+\mathbb{E}[Y'(t)]-\mathbb{E}[Y(t)] \\
$$

Dividing both sides by $\mu$we get:
$$
N(t+a) - N(t)=\frac{1}{\mu}(a+\mathbb{E}[Y'(t)]-\mathbb{E}[Y(t)]) \\
$$

I'll leave the proof here in order to save time, but as we can see, if we bound that equation, we can obtain the limits easily.

---
## 3. Directly Riemann Integrable
Let $h$ be a function defined on $[0, \infty]$. For any $a>0$, let $M_{n}(a)$ and $m_{n}(a)$ be the supremum (smallest upper bound) and infimum (largest lower bound) in the interval $(n-1)a \leq t \leq na$ for $a \geq 0$. That is:
$$
\begin{align}
M_{n}(a) = \text{sup}\{ h(t) : (n-1)a \leq t \leq na \} \\
m_{n}(a) = \text{inf}\{ h(t) : (n-1)a \leq t \leq na \} \\
\end{align}
$$

Then we say $h$ is **Directly Riemann Integrable** if:
$$
\lim_{ a \to 0 } \sum_{n=1}^\infty M_{n}(a) = \lim_{ a \to 0 } \sum_{n=1}^\infty m_{n}(a)
$$

**Diagram**
![[image-7.jpg| 400]]
---
## 4. Key Renewal Theorem
### Statement
If $F$ is *not lattice*, and if $h(t)$ is *dereclty Riemann integrable*, then:
$$
\lim_{ t \to \infty } \int_{0}^th(t-x)dm(x)=\frac{1}{\mu}\int_0^1h(t)dt
$$
Where:
- $m(x)$ is the renewal function.
- $\mu$ is the mean of the distribution $F$.
- $h(t)$ is any direcatly Riemann Integrable function.
