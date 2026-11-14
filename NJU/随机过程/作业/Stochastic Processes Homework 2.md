**学生：** Moisés Adame Aguilar
**学号：** 522026375001

---
## Probelm 1
### Statement
$$
\lim_{ t \to \infty } P\{ Y(t) \leq x\}
$$

### Proof
Lets say we have an alternating renewal process $\{ X_{n}, n\geq 1\}$ where $X_{n} = Z_{n} + Y_{n}$, and the states on and off are defined as follows:
- **On $Z_n$**: Is when $Y(t) < x$
- **Off $Y_n$**: Is when $Y(t) \geq x$

We have then 2 possible scenarios:
- $x \geq X$: The *"off" time* is dictated by $X$.
- $x < X$: The *"off" time* is dicated by $x$.

Applying the Alternating Renewal Process Theorem, we get:
$$
\lim_{ t \to \infty } P\{ Y(t) \leq x \} = \frac{\mathbb{E}[Y_{n}]}{\mathbb{E}[X_{n}]}
$$

Since we have two possible scenarios for the "off" time, then $Y_{n} = \text{min}\{ x, X \}$ and because all the cycles are *identically distributed*, we know that $\mathbb{E}[X_{n}]=\mathbb{E}[X]=\mu$, so we get:
$$
\lim_{ t \to \infty } P\{ Y(t) \leq x \} = \frac{\mathbb{E}[\text{min}\{ x, X \}]}{\mu}
$$

Given that $\text{min}\{ x, X \}$ is a nonnegative random variable, we can apply the following identity for the expected value $\mathbb{E}[Y]=\int_{0}^\infty P\{ Y > y \}dy$
$$
\lim_{ t \to \infty } P\{ Y(t) \leq x \} = \frac{1}{\mu} \int_{0}^\infty P\{ \text{min}\{ x, X \} > y \}dy
$$

To solve this integral, we first need to understand $P\{ \text{min}\{ x, X \} > y \}$. Given the defiinition of the $\text{min}\{ \cdot \}$ function, we can rewrite the probability as $P\{ x > y \land X >y \}$. Because $x$ is a constant, this implies that when $y \in [x, \infty)$ the probability is $0$, because $x > y$ is false. Additionally, when $y \in [0, x)$ since $x > y$ is true, the probability is $P\{ X > y \}$, therefore:
$$
\lim_{ t \to \infty } P\{ Y(t) \leq x \} = \frac{1}{\mu} \int_{0}^x P\{ X > y \}dy
$$

Concluding that:
$$
\lim_{ t \to \infty } P\{ Y(t) \leq x \} = \frac{1}{\mu} \int_{0}^x \bar{F}(y)dy
$$





