---
tags:
  - stochastic-process
  - alternating-renewal-process
  - renewal-process
---
Date: 2026-11-13 : 12:04
***
## Definition
This is a special case of [[Regenerative Process]] where we have a system that can be in two states first state $Z_{1}$ and then, the remaining time it stays on state $Y_{1}$ and so on.

Suppose we have *random vectors* $(Z_{n}, Y_{n}), n\geq1$ where the sequences $\{ Z_{n} \}$ and $\{ Y_{n} \}$ are iid, but we allow $Z_{n}$ and $Y_{n}$ to be dependent.

The expected values are:
- $\mathbb{E}[Z] =\mathbb{E}[Z_{n}]$
- $\mathbb{E}[Y] =\mathbb{E}[Y_{n}]$

**Diagram**
![[NJU/随机过程/Renewal Theory/images/image-8.png|400]]

---
## Theorem
As described in proposition 1 of [[Regenerative Process]] on the long run, the proportion of time on a given state, is the expected value of time in that state, divide by the expected value of the whole cycle, in this case:

If $P(t) = P\{ \text{system is on (state Z)at time t} \}$, then:
$$
\lim_{ t \to \infty } P(t) = \frac{\mathbb{E}[Z]}{\mathbb{E}[Z] +\mathbb{E}[Y]}
$$

## Excess Life $Y(t)$ and Age at $t$ $A(t)$
**Diagram**
![[NJU/随机过程/Renewal Theory/images/image-9.png]]

**Formulas**
$$
\begin{align}
Y(t) & = S_{N(t) + 1} - t \\
A(t) & = S_{N(t)} + t
\end{align}
$$

### Deriving $\lim_{ t \to \infty }P\{ A(t) \leq x\}$
Since $x$ is a real number, it can be bigger or smaller or equal to $X$, Considering the previosly mentioned theorem
$$
\lim_{ t \to \infty } P(A(t) \leq x) = \frac{\mathbb{E}[\text{min}\{ X, x \}]}{\mathbb{E}[X]}
$$

By definition of expected value:
$$
\lim_{ t \to \infty } P(A(t) \leq x) = \frac{1}{\mathbb{E}[X]} \int_{0}^\infty P\{ \text{min}\{ X, x \} > y \} dy
$$

What is inside of the integral can be rewritten as:
$$
\{ \text{min}\{ X, x \} > y \}  = \{ X > y \} \cap \{ x > y \}
$$

Since $x$ is a constant:
$$
 P\{ \text{min}\{ X, x \} > y \} =
 \begin{cases}
 P\{ X > y \}, & 0\leq y < x \\
 0, & y \geq x
 \end{cases}
$$



