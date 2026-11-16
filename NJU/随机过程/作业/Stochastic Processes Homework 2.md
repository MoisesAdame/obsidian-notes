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
---
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
---
## Problem 3
### Statement
Consider flipping a coin independently, each time with probability $p$ comes up with $1$, and with probability $q = 1 −p$ comes up with $0$. Let $A = 1010$, $B = 0100$. Find $P(A \text{ before } B)$, i.e., the probability that pattern $A$ occurs before pattern $B$. (Here we set $p = \frac{1}{4}$.)

### Proof
Since we know that in order to calculate $P\{ A \text{ before } B\}$ we can just use the following equation:
$$
P\{ A \text{ before } B\} = \frac{\mathbb{E}[N_{B}] + \mathbb{E}[N_{A|B}] - \mathbb{E}[N_{A}]}{\mathbb{E}[N_{B|A}] + \mathbb{E}[N_{A|B}]}
$$

We just have to find the values of $\mathbb{E}[N_{A|B}]$, $\mathbb{E}[N_{B|A}]$, $\mathbb{E}[N_{A}]$ and $\mathbb{E}[N_{B}]$.

When trying to find $\mathbb{E}[N_{A|B}]$ we will find out that because there is no overlap when we start with $0100$ with $1010$, then $\mathbb{E}[N_{A|B}]$ is the same as $\mathbb{E}[N_{A}]$, that is:
$$
\mathbb{E}[N_{A|B}] = \mathbb{E}[N_{A}] = \mathbb{E}[N_{1010}] = \mathbb{E}[N_{1010|10}] + \mathbb{E}[N_{10}] = p^{-2}q^{-2} + p^{-1}q^{-1} = \frac{304}{9}
$$

When trying to find $\mathbb{E}[N_{B|A}]$ we can see that because there is an overlap with the three last digits of $A$, with the first three digits of $B$, since:
$$
\mathbb{E}[N_{0100}] = \mathbb{E}[N_{010}] + \mathbb{E}[N_{0100|010}]
$$

Rearranging, we get:
$$
\mathbb{E}[N_{B|A}] =\mathbb{E}[N_{0100|010}] = \mathbb{E}[N_{0100}] - \mathbb{E}[N_{010}] = p^{-1}q^{-3} - p^{-1}q^{-2} = \frac{64}{27}
$$

Finally, computing $\mathbb{E}[N_{B}]$ we get:
$$
\mathbb{E}[N_{B}] = \mathbb{E}[N_{0100}] = \mathbb{E}[N_{0}] +p^{-1}q^{-3} = q^{-1} + p^{-1}q^{-3} = \frac{292}{27}
$$

Resulting in:
$$
P\{ A \text{ before } B\} = \frac{\frac{292}{27} + \frac{304}{9} - \frac{304}{9}}{\frac{64}{27} + \frac{304}{9}} = \frac{73}{244}
$$
---
## Problem 4
### Statement
Let $Y_{1},Y_{2},\dots$ be i.i.d. with
$$
P\{ Y_{i} = 1 \} = P\{ Y_{i} = -1 \} = \frac{1}{2}
$$

and define
$$
Z_{0}=0, \quad Z_{n}=\sum_{i = 1}^n Y_{i}
$$

$\{ Z_{n}, n\geq0 \}$ is called the *symmetric random walk process*. 

Define
$$
u_{n} = P\{ Z_{2n}=0 \}={2n \choose n} \left( \frac{1}{2} \right)^{2n}
$$
Prove that
$$
P\{ Z_{1}\neq0, Z_{2}\neq0,\dots,Z_{2n}\neq0 \} = u_{n}
$$

### Proof
By the Ballot Theorem, the probability that the *first* return to 0 occurs at time $2j$ is $\frac{u_j}{2j-1}$. Therefore, we have:
$$
P(\text{hit 0 by time } 2n) = \sum_{j=1}^{n} \frac{u_j}{2j - 1}
$$

We can rewrite our original probability as
$$
P\{ Z_1 \neq 0, \dots, Z_{2n} \neq 0 \}= 1 - \sum_{j=1}^{n} \frac{u_j}{2j - 1}
$$

Then, we just have to prove that
$$
u_n = 1 - \sum_{j=1}^{n} \frac{u_j}{2j - 1}
$$

**Base case $n=1$:** Since $u_1 = \frac{1}{2}$:
$$
1 - \frac{u_1}{2(1)-1} = 1 - \frac{1}{2} = \frac{1}{2} = u_1
$$

**Inductive step:** Assuming that $u_n = 1 - \sum_{j=1}^{n} \frac{u_j}{2j - 1}$ holds for $n-1$:
$$
u_{n-1} = 1 - \sum_{j=1}^{n-1} \frac{u_j}{2j - 1}
$$
Then for $n$:
$$
1 - \sum_{j=1}^{n} \frac{u_j}{2j - 1} = \left(1 - \sum_{j=1}^{n-1} \frac{u_j}{2j - 1}\right) - \frac{u_n}{2n - 1} = u_{n-1} - \frac{u_n}{2n - 1}
$$

Since we know that $u_{n}=\frac{2n-1}{2n}u_{n-1}$, we can see that:
$$
1 - \sum_{j=1}^{n} \frac{u_j}{2j - 1} = \frac{u_{n}2n}{2n-1} - \frac{u_n}{2n - 1} = u_{n}
$$

Proving that
$$
P\{ Z_{1}\neq0, Z_{2}\neq0,\dots,Z_{2n}\neq0 \} = u_{n}
$$
---
## Problem 5
### Statement
Express in words what the random variable $X_{N(t)+1}$ represents. (Hint: It is the length of which renewal interval?)

Show that:
$$
P\{ X_{N(t) + 1} \geq x \} \geq \bar{F}(x)
$$
### Proof
$X_{N(t)+1}$ represents the length of the renewal interval where the point of time $t$ is located.

To show that $P\{ X_{N(t) + 1} \geq x \} \geq \bar{F}(x)$ we first have to find the conditional probability of $X_{N(t) + 1} \geq x$ given that the age of the renewal process at $t$ is some constant $m$, that is:
$$
P\{ X_{N(t) + 1} \geq x | A(t)=m \}
$$

This means that our random variable has to be at least $m$ units of length, that is:
$$
P\{ X_{N(t) + 1} \geq x | A(t)=m \} = P\{ X_{N(t) + 1} \geq x | X_{N(t) + 1} \geq m \}
$$

Because the fact that we are in a renewal process, where random variables are identically distributed, we can then say that for any $X$ with distribution $F$ the following holds:
$$
P\{ X_{N(t) + 1} \geq x | X_{N(t) + 1} \geq m \} = P\{ X \geq x | X \geq m \}
$$

By conditional probability we know:
$$
P\{ X \geq x | X \geq m \} = \frac{P\{ X \geq x, X \geq m \}}{P\{ X \geq m \}}
$$

Now, if $x\geq m$, then $P\{ X \geq x, X \geq m \} = P\{ X \geq x\}$, that is:
$$
P\{ X \geq x | X \geq m \} = \frac{P\{ X \geq x\}}{P\{ X \geq m \}}
$$

Since $P\{ X \geq m \} \leq 1$ and $P\{ X \geq x\} \leq 1$, we then can say that 
$$
P\{ X \geq x | X \geq m \} \geq P\{ X \geq x\} = \bar{F}(x)
$$

Concluding finally that
$$
P\{ X_{N(t) + 1} \geq x \}\geq \bar{F}(x)
$$
---
## Problem 6
### Statement
Two new GPU workers start running in parallel at time 0. When one worker fails, it stays out of service while the other continues to run. Once both workers have failed, they are immediately replaced by two new workers, which start running together. The lifetimes of all workers, including all newly installed workers, are mutually independent and exponentially distributed with rate 1. 

Show that the fraction of time in $[0,t]$ during which exactly one worker is running con verges almost surely as $t\to \infty$, and find its limit. 

**Hint:** Treat each replacement of the pair as a renewal. Let reward accrue at rate 1 when exactly one worker is running and at rate 0 otherwise.

### Proof
For the following analysis we are going to consider a renewal reward process where every process is a alternating renewal process. We can think of it as having two states:
- **On**: Both workers are on service.
- **Off**: Only one worker is on service.

Since we earn at a rate of 1 only when one worker is on service, this means that the **off time** is equal to the **reward** per renewal process.

Now, in order to apply  the **renewal reward process theorem**, we first need to obtain $\mathbb{E}[R]$ and $\mathbb{E}[X]$. Since the reward time per cycle is exactly the off time, we know that: 
$$
\mathbb{E}[R]=\mathbb{E}[\text{"off" time}]=1<\infty
$$

In the other hand the expected time of the length of a cycle can be tought of as $\mathbb{E}[X]=\mathbb{E}[\text{"on" time}]+\mathbb{E}[\text{"off" time}]$, where the on time is just the $\text{min}\{ W_{1}, W_{2} \}$ where $W_{1}$ and $W_{2}$ are iid random variables representing the work lifetime of each worker respectively, then we can say:
$$
\begin{align}
\mathbb{E}[X]&=\mathbb{E}[\text{"on" time}]+\mathbb{E}[\text{"off" time}] \\
& = 1 + \mathbb{E}[\text{min}\{ W_{1}, W_{2} \}] \\
& = 1 + \int_{0}^\infty P\{ \text{min}\{ W_{1}, W_{2} \} > y\}dy \\
& = 1 + \int_{0}^\infty P\{ W_{1} > y \land W_{2} > y \}dy \\
& = 1 + \int_{0}^\infty P\{ W_{1} > y \}P\{ W_{2} > y \}dy \\
& = 1 + \int_{0}^\infty P\{ W_{1} > y \}^2dy \\
& = 1 + \int_{0}^\infty (e^{ -y })^2dy \\
& = 1 + \int_{0}^\infty e^{ -2y }dy \\
& = 1 + \frac{1}{2} \\
& = \frac{3}{2}
\end{align}
$$

Since $\mathbb{E}[R]=1<\infty$ and $\mathbb{E}[X]=\frac{3}{2}<\infty$, then we can apply, which states that, with probability 1,
$$
\frac{R(t)}{t} \to \frac{\mathbb{E}[R]}{\mathbb{E}[X]}\quad\text{as } t\to \infty
$$

Which, applied to our problem, we can say:
$$
\frac{\text{"off" time at [0, t]}}{t} \to \frac{\mathbb{E}[R]}{\mathbb{E}[X]}=\frac{2}{3}\quad\text{as } t\to \infty
$$