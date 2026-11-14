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
Lets say we have an alternating renewal process $\{ X_{n}, n\geq 1\}$ where $X_{n} = Z_{n} + Y_{n}$ and the states on and off are defined as follows:
- **On $Z_n$**: Is when $A(t)\leq x$
- **Off $Y_n$**: Is when $A(t) >x$

We have then 2 possible scenarios:
- $x \geq X$: The *on time* is dictated by $X$.
- $x < X$: The *on time* is dicated by $x$.

Applying the Alternating Renewal Process Theorem, we get:
$$
\lim_{ t \to \infty } P\{ A(t) \leq x \} = \frac{\mathbb{E}[Z_{n}]}{\mathbb{E}[X_{n}]}
$$

Since we have two possible scenarions for the on time, then $Z_{n} = \text{min}\{ x, X \}$ and because all the cycles are identically distributed, we know that $\mathbb{E}[X_{n}]=\mathbb{E}[X]=\mu$, so we get:
$$
\lim_{ t \to \infty } P\{ A(t) \leq x \} = \frac{\mathbb{E}[\text{min}\{ x, X \}]}{\mu}
$$

Given that $\text{min}\{ x, X \}$ is a nonnegative random variable, we can apply the following identity for the expected value $\mathbb{E}[Y]\int_{0}^\infty P\{ Y > y \}dy$
$$
\lim_{ t \to \infty } P\{ A(t) \leq x \} = \frac{1}{\mu} \int_{0}^\infty P\{ \text{min}\{ x, X \} > y \}dy
$$

To solve this integral, we first need to understand $P\{ \text{min}\{ x, X \} > y \}$. Given the defiinition of the $\text{min}\{ \cdot \}$ function, we can rewrite the probability as $P\{ x > y \land X >y \}$. Because $x$ is a constant, this implies that when $y \in [x, \infty)$ the probability is $0$ and when $y \in [0, x)$ the probability is $P\{ X > y \}$, therefore:
$$
\lim_{ t \to \infty } P\{ A(t) \leq x \} = \frac{1}{\mu} \int_{0}^x P\{ X > y \}dy
$$

Concluding that:
$$
\lim_{ t \to \infty } P\{ A(t) \leq x \} = \frac{1}{\mu} \int_{0}^x \bar{F}(y)dy
$$


