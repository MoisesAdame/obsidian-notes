**学生：** Moisés Adame Aguilar
**学号：** 522026375001

---
## Problem 1
### Statement
Consider a renewal process, define:
$A(t) = t−S_{N(t)}$: time from $t$ since the last renewal, called “age” at $t$, 
$Y(t) = S_{N(t)+1} − t$: time from $t$ until the next renewal, called “residual life” at $t$. 

Find:
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

## Problem 2
### Statement
Consider flipping a coin independently, each time with probability $p$ comes up with $1$, and with probability $q = 1 −p$ comes up with $0$. Find $E[N_{11\dots1}]$, i.e., the expected time until pattern $11\dots1$ ($k$ consecutive $1$s) occurs for the first time.

### Proof
Since the ocurrance of a pattern, that is, the apperance of $11\dots1$ ($k-1$ consecutive $1$s) influences the next ocurrance of the pattern, then:
$$
\mathbb{E}[N_{11\dots1}] = \mathbb{E}[N_{\underbrace{11\dots1}_{k \text{ times}}|\underbrace{11\dots1}_{k-1 \text{ times}}}] + \mathbb{E}[N_{\underbrace{11\dots1}_{k-1 \text{ times}}}]
$$

This reasoning can be extended, which results in:
$$
\mathbb{E}[N_{11\dots1}] = \frac{1}{p^k} + \frac{1}{p^{k-1}} +\cdots + \frac{1}{p^{1}}
$$
## Problem 3
### Statement
Consider flipping a coin independently, each time with probability $p$ comes up with $1$, and with probability $q = 1 −p$ comes up with $0$. Let $A = 1010$, $B = 0100$. Find $P(A \text{ before } B)$, i.e., the probability that pattern $A$ occurs before pattern $B$. (Here we set $p = \frac{1}{4}$.)

### Proof
Since we know that in order to calculate $P\{ A \text{ before } B\}$ wer can just use the following equation:
$$
P\{ A \text{ before } B\} = \frac{\mathbb{E}[N_{B}] + \mathbb{E}[N_{A|B}] - \mathbb{E}[N_{A}]}{\mathbb{E}[N_{B|A}] + \mathbb{E}[N_{A|B}]}
$$

We just have to finde the values of $\mathbb{E}[N_{A|B}]$, $\mathbb{E}[N_{B|A}]$, $\mathbb{E}[N_{A}]$ and $\mathbb{E}[N_{B}]$.

For instance
$$
\begin{align}
\mathbb{E}[N_{A|B}] & = \mathbb{E}[\text{additional number to 1010 starting with 0100}] \\
& = \mathbb{E}[N_{1010}] - \mathbb{E}[N_{0100}] \\
& = \mathbb{E}[N_{1010|10}] + \mathbb{E}[N_{10}] - \mathbb{E}[N_{0100}] \\
& = p^{-2}q^{-2}+ p^{-1}q^{-2} - \mathbb{E}[N_{0100}]
\end{align}
$$





