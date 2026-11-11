---
tags:
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

Aditionally, $N(t) \to \infty$, when $t\to \infty$.

## Elementary Renewal Theorem
