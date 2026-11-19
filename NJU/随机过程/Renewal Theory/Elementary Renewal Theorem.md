---
tags:
  - stochastic-process
  - elementary-renewal-theorem
  - excess-time
---
Date: 2026-11-11 : 18:40
***

## Theorem Statement
$$
P\left\{ \lim_{ t \to \infty } \frac{m(t)}{t} = \frac{1}{\mu }\right\}=1
$$

## Proposition 1
$$
P\left\{ \lim_{ t \to \infty } \frac{N(t)}{t} = \frac{1}{\mu }\right\}=1
$$

### Proof
If $N(t)=3$, this means that $S_{N(t)}$ is the time for the 3rd event, that means that $S_{N(t)}$ is the time for the last event. While $S_{N(t) + 1}$ is the time for the netx event after the last. Thus:
$$
S_{N(t)} \leq t < S_{N(t)+1}
$$

![[image-2.jpg|400]]

Dividing both inequalities by $N(t)$
$$
\frac{S_{N(t)}}{N(t)} \leq \frac{t}{N(t)} < \frac{S_{N(t)+1}}{N(t)}
$$

By the **Strong Law of Large Numbers**:
$$
\lim_{ N(t) \to \infty } \frac{S_{N(t)}}{N(t)} =\mu
$$

The right side of the inequality can be rewritten as:
$$
\frac{S_{N(t)+1}}{N(t)} = \frac{S_{N(t)+1}}{N(t)+1} \cdot \frac{N(t)+1}{N(t)}
$$

By the **Strong Law of Large Numbers**:
$$
\begin{align}
\lim_{ N(t) \to \infty } \frac{S_{N(t)+1}}{N(t)}
& = \lim_{ N(t) \to \infty }\frac{S_{N(t)+1}}{N(t)+1} \cdot \lim_{ N(t) \to \infty }\frac{N(t)+1}{N(t)} \\
& = \mu \cdot 1 \\
& =\mu
\end{align}
$$

By the squeeze therem:
$$
\lim_{ N(t) \to \infty } \frac{t}{N(t)} =\mu
$$

Thus:
$$
\lim_{ N(t) \to \infty } \frac{N(t)}{t} =\frac{1}{\mu}
$$

Additionally, $N(t) \to \infty$, when $t\to \infty$.

## Stopping Time 
Related notes: [[Stopping Time]]

## Proof of Elementary Renewal Theorem
Given the corollary from [[Stopping Time]], we know that
$$
\mathbb{E}[S_{N(t) + 1}] = \mathbb{E}[X] \mathbb{E}[N(t) + 1]
$$

Additionally, check out the following diagram:
![[NJU/随机过程/Renewal Theory/images/image-4.png|500]]

Thus we can express $S_{N(t) + 1}$ as:
$$
S_{N(t)+1} = t + Y(t)
$$

Where $Y(t)$ is the **excess-time** and is the time between moment $t$ and the stopping time.

Given that $\mu = \mathbb{E}[X]$ and $m(t) = \mathbb{E}[N(t)]$, so:
$$
\mathbb{E}[S_{N(t) + 1}] = \mathbb{E}[X] \mathbb{E}[N(t) + 1]
$$

The expected value is taken with respect to $N(t)$, this implies:
- $t$ and $1$ are treated as constants
- Since $m(t) = \mathbb{E}[N(t)]$, then $m(t) + 1 = \mathbb{E}[N(t)] + 1$ and by the properties of the expected value: $m(t) + 1 = \mathbb{E}[N(t) + 1]$
$$
\mathbb{E}[t + Y(t)] = \mu [m(t) + 1]
$$
$$
t + \mathbb{E}[Y(t)] = \mu [m(t) + 1]
$$

We can rewrite this as:
$$
\frac{m(t)}{t} = \frac{1}{\mu} - \frac{1}{t} + \frac{\mathbb{E}[Y(t)]}{t\mu}
$$

It is very difficult to calculate the limit of $\frac{\mathbb{E}[Y(t)]}{t\mu}$ as $t\to \infty$, so we will drop that term, that is:
$$
\frac{m(t)}{t} \geq \frac{1}{\mu} - \frac{1}{t}
$$

Tanking the limit:
$$
\lim_{ t \to \infty }\left( \frac{m(t)}{t}  \right)\geq \lim_{ t \to \infty } \left(  \frac{1}{\mu} - \frac{1}{t} \right) = \frac{1}{\mu}
$$

Because the interrarival times are finite we can assume that there is a $M$ such that $P\{ X_{i} < M \} = 1$ for all $i = 1, 2,\dots$. This implies that $P\{ Y(t) < M \} = 1$. Thus:
$$
\frac{m(t)}{t} \leq \frac{1}{\mu} - \frac{1}{t} + \frac{M}{t\mu}
$$

Taking the limit
$$
\lim_{ t \to \infty }\left( \frac{m(t)}{t}  \right) \leq \lim_{ t \to \infty } \left(  \frac{1}{\mu} - \frac{1}{t} + \frac{M}{t\mu} \right) = \frac{1}{\mu}
$$

Since:
$$
\frac{1}{\mu} \leq \lim_{ t \to \infty }\left( \frac{m(t)}{t}  \right) \leq \frac{1}{\mu}
$$

We conclude that:
$$
\lim_{ t \to \infty }\left( \frac{m(t)}{t}  \right) = \frac{1}{\mu}
$$
---
## Central Limit Theorem for Renewal process
### Statement
$$
\lim_{ t \to \infty } P\left\{ \frac{N(t) -t/\mu}{\sqrt{ t\sigma^2 /\mu^3}} < x\right\} = \frac{1}{\sqrt{ 2\pi }} \int_{-\infty}^x e^{ -x^2/2 }dx
$$

### Proof
Lets rewrite the probability as follows:
$$
P\left\{ N(t) < x\sqrt{ t\sigma^2 /\mu^3} +t/\mu\right\}
$$

Let $r = x\sqrt{ t\sigma^2 /\mu^3} +t/\mu$, so we get:
$$
P\left\{ N(t) < r\right\}
$$

Because $S_{n} > t \iff N(t) < n$
![[image-5.jpg|400]]

Then we can say:
$$
P\{ S_{r} > t\}
$$

This is the same as:
$$
P\left\{  \frac{S_{r} - r \mu}{\sigma \sqrt{ r }} > \frac{t - r \mu}{\sigma \sqrt{ r }} \right\}
$$

Plugging in $r = x\sqrt{ t\sigma^2 /\mu^3} +t/\mu$. we get:
$$
P\left\{  \frac{S_{r} - r \mu}{\sigma \sqrt{ r }} > -x \left( 1 + \frac{y\sigma}{\sqrt{ t\mu }} \right)^{-1/2} \right\} 
$$

Then we know that:
$$
\lim_{ t \to \infty } P\left\{  \frac{S_{r} - r \mu}{\sigma \sqrt{ r }} > -x \right\} = \int_{-x}^{\infty} \frac{1}{\sqrt{ 2\pi }}e^{ -x^2/2 }dx
$$

By symmetry, this is the same as:
$$
\lim_{ t \to \infty } P\left\{  \frac{S_{r} - r \mu}{\sigma \sqrt{ r }} > -x \right\} = \int_{-\infty}^{x} \frac{1}{\sqrt{ 2\pi }}e^{ -x^2/2 }dx
$$

So finally, we have:
$$
\lim_{ t \to \infty } P\left\{ \frac{N(t) -t/\mu}{\sqrt{ t\sigma^2 /\mu^3}} < x\right\} = \frac{1}{\sqrt{ 2\pi }} \int_{-\infty}^x e^{ -x^2/2 }dx
$$
