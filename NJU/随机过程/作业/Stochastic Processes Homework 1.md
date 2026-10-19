## Problem 1
### Part 1 (Showing Increments are Stationary and Independent.)
Following the *axiom (ii) of Definition 1*, we know that the **increments are independent**. Additionally, following axiom (iii) of Definition 1, we can see that number of events in any interval of length $t$ is Poisson distributed with mean $\lambda t$, which means that the **increments are stationary**.

### Part 2 (Obtaining $P\{ N(h) = 1 \}$)
Let $s = 0$, then using the *Definition 1 axiom (iii)*, we get:
$$
P\{ N(0 + t) - N(0) = n\} = e^{-\lambda t} \frac{(\lambda t)^n}{n!}
$$

Because of axiom (i) of Definition 1, we get:
$$
P\{ N(t) - 0 = n\} = e^{-\lambda t} \frac{(\lambda t)^n}{n!}
$$

$$
P\{ N(t) = n\} = e^{-\lambda t} \frac{(\lambda t)^n}{n!}
$$

Now, let $n = 1$
$$
P\{ N(t) = 1\} = e^{-\lambda t} \frac{(\lambda t)^1}{1!} = e^{-\lambda t} \lambda t
$$

Using the exponential Taylor expansion, we get:
$$
P\{ N(t) = 1\} = e^{-\lambda t} \lambda t = \lambda t \left(1 - \lambda t + \frac{(\lambda t )^2}{2!} - \frac{(\lambda t )^3}{3!} + \cdots \right)
$$
$$
P\{ N(t) = 1\} = \lambda t - (\lambda t)^2 + \frac{(\lambda t )^3}{2!} -\frac{(\lambda t )^4}{3!} + \cdots
$$
Let 
$$
f(x) = - x^2 + \frac{x^3}{2!} -\frac{x^4}{3!} + \cdots
$$

We can see that if we obtain the following limit:
$$
\lim_{ x \to 0 }\left( \frac{f(x)}{x} \right) = \lim_{ x \to 0 } \left( - x + \frac{x^2}{2!} -\frac{x^3}{3!} + \cdots \right) = 0
$$

That is why we get
$$
P\{ N(t) = 1\} = \lambda t + o(t)
$$

If we change variables from $t = h$, then we get, matching the *axiom (iii) of Definition 2*.
$$
P\{ N(h) = 1\} = \lambda h + o(h)
$$

### Part 3 (Obtaining $P\{ N(h) \geq 2 \}$)
Let $s = 0$, then using the *Definition 1 axiom (iii)*, we get:
$$
P\{ N(0 + t) - N(0) = n\} = e^{-\lambda t} \frac{(\lambda t)^n}{n!}
$$
$$
P\{ N(t) = n\} = e^{-\lambda t} \frac{(\lambda t)^n}{n!}
$$

Now, to obtain $P\{ N(h) \geq 2 \}$ we know that:
$$
P\{ N(h) \geq 2 \} = P\{ N(t) = 2\} + P\{ N(t) = 3\} + \cdots
$$

Which would yield in
$$
P\{ N(h) \geq 2 \} = e^{-\lambda h} \frac{(\lambda h)^2}{2!} + e^{-\lambda h} \frac{(\lambda h)^3}{3!} + \cdots
$$
$$
P\{ N(h) \geq 2 \} = e^{-\lambda h} \left( \frac{(\lambda h)^2}{2!} +  \frac{(\lambda h)^3}{3!} + \cdots \right)
$$

Because of the Taylor Expansion of $e^{\lambda h}$, we know that:

$$
P\{ N(h) \geq 2 \} = e^{-\lambda h} \left( e^{\lambda h} -\lambda h - 1\right)
$$

If we distribute the $e^{-\lambda h}$ inside the parenthesis, we get:
$$
P\{ N(h) \geq 2 \} = 1 -\lambda h e^{-\lambda h}  - e^{-\lambda h} = 1 - e^{-\lambda h }(\lambda h + 1)
$$

Expanding $e^{-\lambda h}$ in its Taylor Expansion we get:
$$
P\{ N(h) \geq 2 \} = 1-(\lambda h+1)\left(1 - (\lambda h) + \frac{(\lambda h)^2}{2!} - \frac{(\lambda h)^3}{3!} + \cdots \right)
$$

After distributing the $(\lambda h+1)$ inside the parenthesis we get:
$$
\begin{align}
P\{ N(h) \geq 2 \} & = 1 + \left[-(1 + \lambda h) + (\lambda h)(1 + \lambda h) - \frac{(\lambda h)^2}{2!}(1 + \lambda h) + \frac{(\lambda h)^3}{3!}(1 + \lambda h) + \cdots \right] \\ 
& = 1 + \left[-1 - \lambda h + (\lambda h) + (\lambda h)^2 - \frac{(\lambda h)^2}{2!}(1 + \lambda h) + \frac{(\lambda h)^3}{3!}(1 + \lambda h) + \cdots \right] \\
& = (\lambda h)^2 - \frac{(\lambda h)^2}{2!}(1 + \lambda h) + \frac{(\lambda h)^3}{3!}(1 + \lambda h) + \cdots
\end{align}
$$
Obtaining the limit as $h \to 0$
$$
\lim_{ h \to 0 } \left[\frac{1}{h}\left((\lambda h)^2 - \frac{(\lambda h)^2}{2!}(1 + \lambda h) + \frac{(\lambda h)^3}{3!}(1 + \lambda h) + \cdots \right)\right] = 0
$$

Showing that:
$$
P\{ N(h) \geq 2 \} = o(h)
$$

## Problem 2
### Solution 1 ($P\{ N(t) \geq n \} = P\{ S_{n}  \leq t\}$)
We know that $S_{n} \leq t$ is equivalent to $N(t) \geq n$, that is why, their probabilities are equal:
$$
P\{ S_{n} \leq t \} = P\{ N(t) \geq n \}
$$

Given the fact that:
$$
P\{ N(t) \geq n \} = e^{-\lambda t}\frac{(\lambda t)^n}{n!} + e^{-\lambda t}\frac{(\lambda t)^{n+1}}{(n+1)!} + e^{-\lambda t}\frac{(\lambda t)^{n+2}}{(n+2)!} + \cdots
$$

After differentiating, we obtain the density function of $S_{n}$, which is:
$$
f_{S_{n}}(t) = \frac{d}{dt}\left(e^{-\lambda t}\frac{(\lambda t)^n}{n!} + e^{-\lambda t}\frac{(\lambda t)^{n+1}}{(n+1)!} + e^{-\lambda t}\frac{(\lambda t)^{n+2}}{(n+2)!} + \cdots\right)
$$
$$
f_{S_{n}}(t) = e^{-\lambda t} \left(-\lambda \frac{(\lambda t)^n}{n!}  +\lambda\frac{(\lambda t)^{n-1}}{(n-1)!} \right) + e^{-\lambda t} \left(-\lambda \frac{(\lambda t)^{n+1}}{(n+1)!}  +\lambda\frac{(\lambda t)^{n}}{(n)!} \right) + \\ e^{-\lambda t} \left(-\lambda \frac{(\lambda t)^{n+2}}{(n+2)!}  +\lambda\frac{(\lambda t)^{n+1}}{(n+1)!} \right) + \cdots
$$

$$
f_{S_{n}}(t) = e^{-\lambda t}\lambda\frac{(\lambda t)^{n-1}}{(n-1)!}
$$

And thus, we see that $S_{n}$ has a gamma distribution with parameters $\lambda$ and $n$

### Solution 2 (Moment Generating Functions)
#### Part 1 (Obtaining the MGF of $S_{n}$)
We can obtain the Moment Generating Function of $S_{n}$ as follows:
$$
M_{S_{n}}(t) = \mathbb{E}[e^{tS_{n}}] = \mathbb{E}[e^{t(X_{1} + X_{2} + \cdots X_{n})}] = \mathbb{E}[e^{tX_{1}} e^{tX_{2}} \cdots e^{tX_{n}} ]
$$

Because $X_{k}, k \in [n]$ are independent, we can say:
$$
\mathbb{E}[e^{tX_{1}} e^{tX_{2}} \cdots e^{tX_{n}} ] = \mathbb{E}[e^{tX_{1}}]\mathbb{E}[e^{tX_{2}}] \cdots \mathbb{E}[e^{tX_{n}}]
$$

Now, let's obtain the Moment Generating Function of $X_{k}$. 
$$
\begin{align}
M_{X_{k}}(t) & = \mathbb{E}[e^{tX_{k}}]  \\
& = \int_{0}^{\infty}e^{tx}\lambda e^{-\lambda x}dx  \\
& = \lambda \int_{0}^{\infty}e^{x(t-\lambda)}dx  \\
& = \frac{\lambda}{t-\lambda}e^{x(t-\lambda)} \Big|_{0}^\infty \\
& = \frac{\lambda}{t-\lambda}\left(\lim_{ x \to \infty } (e^{x(t-\lambda)}) - e^{0} \right)  \\
& = \frac{\lambda}{t-\lambda}\left(\lim_{ x \to \infty } (e^{x(t-\lambda)}) - e^{0} \right)  \\
\end{align}
$$

For the previous limit to converge we need $t < \lambda$, that way, we have:
$$
M_{X_{k}}(t) = \frac{\lambda}{t - \lambda} (0 - 1) = \frac{\lambda}{\lambda - t}
$$

Because $X_{k}, k\geq_{1}$ are identically distributed, we can say:
$$
M_{S_{n}}(t) = \left( \frac{\lambda}{\lambda - t}\right)^n
$$
#### Part 2 (Obtain MGF of Gamma Distribution)
As we know, the probability density function for the Gamma Distribution is the following:
$$
f_{X}(x) = \frac{\lambda^n x^{n-1}e^{-\lambda x}}{(n-1)!}
$$

To obtain its Moment Generating Function:
$$
M_{X}(t) = \mathbb{E}[e^{tX}] = \int_{0}^{\infty}e^{xt}\frac{\lambda^n x^{n-1}e^{-\lambda x}}{(n-1)!}dx
$$

Pulling out the constants and manipulating the inside of the integral, we get:
$$
\frac{\lambda^n}{(n-1)!}\int_{0}^{\infty}e^{x (t-\lambda)} x^{n-1}dx
$$

Letting $u = x(\lambda-t)$, having $t < \lambda$:
$$
\frac{\lambda^n}{(n-1)!}\int_{0}^{\infty}e^{-u} \left( \frac{u}{\lambda-t} \right)^{n-1} \frac{du}{\lambda - t}
$$

Manipulating the constants
$$
\frac{\lambda^n}{(n-1)! (\lambda-t)^n}\int_{0}^{\infty}e^{-u} u^{n-1} du
$$

By the definition of the gamma function, we know:
$$
\Gamma(n) = \int_{0}^{\infty}t^{n-1}e^{-t}dt
$$

Given that $\Gamma(n) = (n-1)!$, the MGF of the gamma distribution is:
$$
\begin{align}
M_{X}(t) & = \frac{\lambda^n}{(n-1)! (\lambda-t)^n} \Gamma(n)  \\
& = \frac{\lambda^n (n-1)!}{(n-1)! (\lambda-t)^n} \\
& = \left(\frac{\lambda}{\lambda-t}\right)^n
\end{align}
$$

Because the property of **uniqueness if the Moment Generating Functions** we can say that $S_{n}$ has a gamma distribution with parameters $n$ and $\lambda$, because:
$$
M_{S_{n}}(t) = M_{X}(t) = \left(\frac{\lambda}{\lambda-t}\right)^n
$$

## Problem 3
For this proof, we will use the first Definition of a Poisson Process, each part of the proof will consist on verifying each of the three conditions stablished by the definition

### Part 1 (N(0) = 0)
Given the fact that $N(t) = N_{1}(t)+N_{2}(t)+ \cdots +N_{n}(t)$, we have to obtain $N(0)$, thus:
$$
N(0) = N_{1}(0)+N_{2}(0)+ \cdots +N_{n}(0)
$$
Because $\{ N_{i}(t), t\geq 0\}$ where $i \in \{ 1,2,\dots,n \}$ is a Poisson Process, then, by definition $N_{i}(0) = 0$
$$
N(0) = 0 + 0 + \cdots + 0 = 0
$$
Thus, verifying the first condition.

### Part 2 (The Process Has Independent Increments)
Given some $t_{k} < t_{k+1}$ where $k \in \mathbb{N}$ we can say that the difference between increments in $N$ looks as follows:
$$
N(t_{k+1}) - N(t_{k}) = \sum_{i = 1}^{n}N_{i}(t_{k+1}) - N_{i}(t_{k})
$$

Now, because by definition $N_{i}(t_{k+1}) - N_{i}(t_{k})$ where $i \in \{ 1, 2, \dots, n \}$ is independent and $N_{i}$, $N_{j}$ where $i \neq j$ are independent, then the vector of increments $[N_{1}(t_{k + 1}) - N_{1}(t_{k}), \dots, N_{n}(t_{k + 1}) - N_{n}(t_{k})]$ is independent of any previous increments.

Since $N(t_{k+1}) - N(t_{k})$ is the sum of the components of the vector presented above, then $N(t_{k+1}) - N(t_{k})$ is independent of the past increments for all $k \in \mathbb{N}$.

### Part 3 (The number of events in any interval of length $t$ is Poisson distributed with mean $\lambda t$)
$$
P\{ N(s + t) - N(s) = a\} = P\{ (N_{1}(s + t) - N_{1}(s)) + \cdots + (N_{n}(s + t) - N_{n}(s))= a\}
$$

Now, let $a = \sum_{i = 1}^{n} a_{i}$, so we can say:
$$
P\{ (N_{1}(s + t) - N_{1}(s)) + \cdots + (N_{n}(s + t) - N_{n}(s))= a\} = \sum _{a_{1} + a_{2} + \cdots + a_{n} = a}P\{ (N_{1}(s + t) - N_{1}(s)) = a_{1}, \dots, (N_{n}(s + t) - N_{n}(s))= a_{n}\} 
$$

By independence, we can say:
$$
= \sum _{a_{1} + a_{2} + \cdots + a_{n} = a} P\{ (N_{1}(s + t) - N_{1}(s)) = a_{1}\} \cdots P\{(N_{n}(s + t) - N_{n}(s))= a_{n}\} 
$$

By the definition of each $N_{i}$:
$$
= \sum _{a_{1} + a_{2} + \cdots + a_{n} = a} e^{-\lambda_{1}t} \frac{(\lambda_{1} t)^{a_{1}}}{a_{1}!} \cdots e^{-\lambda_{n}t} \frac{(\lambda_{n} t)^{a_{n}}}{a_{n}!}
$$

Rearranging some terms, we get:
$$
= e^{-t(\lambda_{1}+\lambda_{2}+\cdots+\lambda_{n})} t^{a_{1} + a_{2} + \cdots + a_{n}} \sum _{a_{1} + a_{2} + \cdots + a_{n} = a} \frac{\lambda_{1}^{a_{1}}\lambda_{2}^{a_{2}} \cdots \lambda_{n}^{a_{n}}}{a_{1}!a_{2}!\cdots a_{n}!} 
$$

Given that we know that the multinomial theorem has this form:
$$
(\lambda_{1} + \lambda_{2} + \cdots + \lambda_{n})^{a} = \sum_{a_{1} + a_{2} + \cdots + a_{n} = a} \frac{a!}{a_{1}! a_{2}! \cdots a_{n}!} \lambda_{1}^{a_{1}}\lambda_{2}^{a_{2}} \cdots \lambda_{n}^{a_{n}}
$$

Then:
$$
= e^{-t(\lambda_{1}+\lambda_{2}+\cdots+\lambda_{n})} \frac{(t(\lambda_{1} + \lambda_{2} + \cdots + \lambda_{n}))^{a}}{a!}
$$

Obtaining a Poisson Distribution whose rate is $\sum_{i = 1}^{n} \lambda_{i}$

## Problem 4
### Part 1 (Obtaining the Moment Generating Function of $N(t + h)$ using Definition 1)
For the following problem, we'll analyze the Moment Generating Functions that can be obtained from the Definition N1 of the Non-Homogeneous Poisson Process, thus, let:
$$
M_{t+h}(x) = \mathbb{E}[e^{xN(t+h)}]
$$
$$
= \mathbb{E}[e^{x(N(t+h) - N(t) + N(t))}] = \mathbb{E}[e^{x(N(t+h) - N(t))} e^{xN(t)}]
$$

By independent increments:
$$
= \mathbb{E}[e^{x(N(t+h) - N(t))}] \mathbb{E}[e^{xN(t)}]
$$

By plugging in the value of the expression $\mathbb{E}[e^{x(N(t+h) - N(t))}]$, obtained using the conditions of the Definition 1 of a Non-Homogeneous Poisson Process, we get:
$$
= \left(e^{x \times 0} (1-\lambda(t)h + o(h))  + e^{x \times 1}  ( \lambda(t)h + o(h)) + e^{x \times 2} o(h) + e^{x \times 3} o(h) + \cdots\right)\mathbb{E}[e^{xN(t)}]
$$

Manipulating the previous expression we get
$$
= (1 - \lambda(t)h + e^x \lambda(t)h + o(h))\mathbb{E}[e^{xN(t)}] 
$$

Let $M_{t}(x) = \mathbb{E}[e^{xN(t)}]$, then we get:
$$
M_{t+h}(x) = M_{t}(x) - M_{t}(x)\lambda(t)h + e^x \lambda(t) h M_{t}(x) + M_{t}(x)o(h)
$$

Dividing both sides of the previous expression by $h$ and obtaining the limit as $h \to 0$, we get:
$$
\lim_{ h \to 0 } \left(\frac{M_{t+h}(x) - M_{t}(x)}{h}\right) = \lim_{ h \to 0 } \left(- M_{t}(x)\lambda(t) + e^x \lambda(t) M_{t}(x) + \frac{o(h)}{h} M_{t}(x)\right)
$$
$$
\frac{\partial M_{t}(x)}{\partial t} = - M_{t}(x)\lambda(t) + e^x \lambda(t) M_{t}(x) 
$$

Having to solve the following differential equation:
$$
\frac{1}{M_{t}(x)} \frac{\partial M_{t}(x)}{\partial t} = e^x\lambda(t) - \lambda(t) = \lambda(t) (e^x - 1)
$$

Integrating both sides with respect to $t$.
$$
\int_{0}^t \frac{1}{M_{t}(x)} \frac{\partial M_{t}(x)}{\partial t} dt = \int_{0}^t\lambda(t) (e^x - 1)dt
$$

Letting $m(t) = \int_{0}^t \lambda(x)dx$.
$$
\ln[M_{t}(x)] \Big|_{0}^t = (e^x - 1)m(t)
$$
$$
\ln[\mathbb{E}[e^{xN(t)}]] -  \ln[\mathbb{E}[e^{xN(0)}]] = (e^x - 1)m(t)
$$

Using the *axiom (i) of Definition N1*, we know that:
$$
\ln[\mathbb{E}[e^{xN(t)}]] -  \ln[\mathbb{E}[e^0]] = \ln[\mathbb{E}[e^{xN(t)}]] = (e^x - 1)m(t)
$$

By manipulating the expression, we get that:
$$
\mathbb{E}[e^{xN(t)}]= e^{(e^x - 1)m(t)}
$$

To find the MGF of the increment, we evaluate $N(t+s)$ and use independent increments:
$$
\mathbb{E}[e^{ x N(t + s) }] = \mathbb{E}[e^{ x [N(t + s) - N(t) + N(t)] }] = \mathbb{E}[e^{ x [N(t + s) - N(t)] }] \mathbb{E}[e^{ x [N(t)] }]
$$

Substituting the known MGFs:
$$
e^{(e^x - 1)m(t + s)} = \mathbb{E}[e^{ x [N(t + s) - N(t)] }]  e^{(e^x - 1)m(t)}
$$

Dividing both sides by $e^{(e^x - 1)m(t)}$
$$
\mathbb{E}[e^{ x [N(t + s) - N(t)] }] = e^{(e^x - 1)[m(t + s) - m(t)]}
$$

### Part 2 (Proving $N(t+s) - N(t)$ is Poisson distributed)
We know that the Moment Generating Function of a Poisson random variable $Y$ with mean $\Delta$ is:
$$
M_{Y}(x) = \mathbb{E}[e^{ xY }] = e^{ \Delta(e^{ x } - 1) }
$$

From Part 1, we established that the MGF of the increment $N(t+s) - N(t)$ is:
$$
\mathbb{E}[e^{ x [N(t + s) - N(t)] }] = e^{(e^x - 1)[m(t + s) - m(t)]}
$$

Notice that this takes the exact form of the Poisson MGF with mean $\Delta = m(t+s) - m(t)$

Finally, because the property of **uniqueness of the Moment Generating Functions** we can say that the random variable $N(t+s)−N(t)$ follows a Poisson with mean  $m(t+s) - m(t)$ distribution with mean $m(t+s)−m(t)$, therefore, the probability mass function is:
$$
P(N(t+s) - N(t) = n) = e^{-(m(t+s) - m(t))} \frac{(m(t+s) - m(t))^n}{n!}
$$

And the result is proven.

## Problem 5
### Part 1 (Verifying Axiom 1 from Definition N2)
Given the fact that at $N(0) = 0$, then we can assert that $N'(0) = 0$, that is, due to the fact that there are no events at time 0, the events that can be counted are 0.

### Part 2 (Verifying Axiom 2 from Definition N2)
We know that the **counted events** from the interval $(t, t+s]$ relies on the number of events from the interval $(t, t+s]$, because the latter is independent to the number of events prior to $t$, then we can conclude that the counted events from the interval $(t, t+s]$ is also independent from the number of events prior to $t$.

### Part 3 (Verifying Axiom 3 from Definition N2)
For this part we'll analyze the following probability $P\{ N'(t+s) - N'(t) = n\}$, that is
$$
\begin{align}
P\{ N'(t+s) - N'(t) = n\}  = &P\{ N'(t+s) - N'(t) = n, N(t+s) - N(t) = n\} + \\
& P\{ N'(t+s) - N'(t) = n, N(t+s) - N(t) = n + 1\} + \\
& P\{ N'(t+s) - N'(t) = n, N(t+s) - N(t) = n + 2\} + \\
& \vdots
\end{align}
$$

For easier writability, will write $N'(t+s) - N'(t) = n$ as $N'_{n}(t;t+s)$, that is:
$$
\begin{align}
P\{ N'_{n}(t;t+s)\}  = &P\{ N'_{n}(t;t+s), N_{n}(t;t+s)\} + \\
& P\{ N'_{n}(t;t+s), N_{n + 1}(t;t+s)\} + \\
& P\{ N'_{n}(t;t+s), N_{n + 2}(t;t+s)\} + \\
& \vdots
\end{align}
$$

For the purpose of analyzing the behavior of each line, will generalize it as follows:
$$
P\{ N'_{n}(t;t+s), N_{n + m}(t;t+s) \} =  P\{ N'_{n}(t;t+s)| N_{n + m} (t;t+s) \} P\{ N_{n + m} (t;t+s) \} 
$$

Using the definition of the homogeneous poisson process we know that:
$$
P\{ N_{n + m} (t;t+s) \} = e^{- \lambda s} \frac{(\lambda s)^{n +m}}{(n + m)!}
$$

For the other part, in order to calculate $P\{ N'_{n}(t;t+s)| N_{n + m} (t;t+s) \}$ the probability of counting one event inside our interval $(t, t+s]$. For this, we have to use the fact that we have $N(t+s) - N(t) = n + m$ events, whose arrival times are the random variables $Y_{1}, Y_{2}, \dots, Y_{n+m}$, which are i.i.d over the interval $(t, t+s]$, that is why the probability that any specific event is counted is:
$$
p = \int_{t}^{t+s} \frac{1}{s} \frac{\lambda(y)}{\lambda}dy = \frac{m(t+s) - m(t)}{s \lambda}
$$

Considering this, because we have $n$ counted events and $m$ not counted ones, then:
$$
P\{ N'_{n}(t;t+s)| N_{n + m} (t;t+s) \} = {n + m\choose n} p^n (1-p)^m
$$

Thus:
$$
\begin{align}
P\{ N'_{n}(t;t+s), N_{n + m}(t;t+s) \} & = {n + m\choose n} p^n (1-p)^m e^{- \lambda s} \frac{(\lambda s)^{n +m}}{(n + m)!} \\
& = \frac{(n+m)!}{n! m!} \frac{(\lambda s)^{n +m}}{(n + m)!}p^n (1-p)^m e^{- \lambda s}  \\
& = \frac{(\lambda s)^{n +m}}{n! m!}p^n (1-p)^m e^{- \lambda s}
\end{align}
$$

So, we can rewrite $P\{ N'(t+s) - N'(t) = n\}$ as follows:
$$
\begin{align}
P\{ N'(t+s) - N'(t) = n\} & = \sum_{m = 0}^{\infty} \frac{(\lambda s)^{n +m}}{n! m!}p^n (1-p)^m e^{- \lambda s} \\
& = \frac{(\lambda s)^n}{n!} p^n e^{-\lambda s} \sum_{m = 0}^{\infty} \frac{(\lambda s[1- p])^m}{m!} \\
& = \frac{(\lambda s)^n}{n!} p^n e^{-\lambda s} e^{ \lambda s - \lambda s p } \\
& = \frac{(\lambda s p)^n}{n!} e^{ - \lambda s p }
\end{align}
$$

Using the previously obtained equation about $p$, we know that:
$$
\lambda s p = \lambda s \frac{m(t+s) - m(t)}{s \lambda} = m(t+s) - m(t)
$$

Thus,
$$
P\{ N'(t+s) - N'(t) = n\} = \frac{(m(t+s) - m(t))^n}{n!} e^{ - (m(t+s) - m(t))}
$$

And the result is proven.

## Problem 6
### Part 1 (Verifying Axiom 1 from Definition N2)
For this, we have to prove that $N(0) = N^{\star}(m(0))$.

Using the definition of $m(t)$, we know that:
$$
m(0) = \int_{0}^{0} \lambda(x)dx = 0
$$

This means that $N^{\star}(m(0)) = N^{\star}(0)$, which by *definition of the homogeneous Poisson Process* is $N^{\star}(0) = 0$, implying that $N(0) = 0$.

### Part 2 (Verifying Axiom 2 from Definition N2)
Let $t'_{i} = m(t_{i})$ and $t'_{i - 1} = m(t_{i - 1})$, because $t_{i} > t_{i - 1}$ and $\lambda(t) > 0$, we know that $t'_{i} > t'_{i - 1}$.

Now, we know that:
$$
N(t_{i}) - N(t_{i - 1})= N^\star(m(t_{i})) - N^\star(m(t_{i - 1})) = N^\star(t'_{i}) - N^\star(t'_{i-1})
$$

Since, $m(t)$ as it was shown earlier is non-decreasing, disjoint intervals in $t$ map to disjoint intervals in $t'$. That is to say, if $(t_{i-1}, t_{i}]$ and $(t_{j-1}, t_{j}]$ are disjoint, then $(m()t_{i-1}, t_{i}]$ and $(m(t_{j-1}), m(t_{j})]$ are also disjoint. Because of this, and due to the fact that $N^\star$ by *definition of the homogeneous Poisson Process*, is independent over disjoint intervals, then, $N(t)$ has independent increments. 

### Part 3 (Verifying Axiom 3 from Definition N2)
We know that:
$$
P\{ N(t + s) - N(t) = n \} = P\{ N^\star(m(t + s)) - N^\star(m(t)) = n \}
$$

Because by definition of the homogeneous poisson process $N^\star$ has has stationary increments, the distribution of $N(a) - N(b)$ only depends on the length $a - b$. That is why $N^\star(m(t + s)) - N^\star(m(t))$ has the same distribution as $N^\star(m(t + s) - m(t))$
By stationary increments of $N^\star$, we know that:
$$
P\{ N(t + s) - N(t) = n \} = P\{ N^\star(m(t + s) - m(t)) = n \}
$$

This, can be rewritten as follows (considering that $\lambda = 1$)
$$
P\{ N(t + s) - N(t) = n \} = e^{ -(m(t + s) - m(t)) } \frac{(m(t + s) - m(t))^n}{n!}
$$

And the result is proven.

## Problem 7
### Part 1 (Verifying Axiom 1 from Definition 1 of Homogeneous Poisson Distribution)
For this, we have to prove that $N^{\star}(0) = N(m^{-1}(0))$.

As seen in the **problem 6**, we showed how $m(0) = 0$, being easy to see that $m^{-1}(0) = 0$. By definition of the Non-Homogeneous Poisson Process, we know that $N(0) = 0$, hence $N^\star(0) = 0$.

### Part 2 (Verifying Axiom 2 from Definition 1 of Homogeneous Poisson Distribution)
#### Part 2.1 (Verifying Independent Increments)
Given $t_{0} < t_{1} < t_{2} < \cdots < t_{n}$, as we showed in the previous problem, for any $t_{i} > t_{i - 1}$, given the fact that $\lambda(t) > 0$, then $m(t_{i}) > m(t_{i -1})$. Thus $m^{-1}(t_{i}) > m^{-1}(t_{i-1})$.

Now, we can say that:
$$
N^\star(t_{i}) - N^\star(t_{i-1}) = N(m^{-1}(t_{i})) - N(m^{-1}(t_{i-1})
$$

By **definition N2**, we can say that because $N$ has independent increments over the disjoint intervals $(m^{-1}(t_{i}), m^{-1}(t_{i-1}]$, then $N^\star$ also does.

#### Part 2.2 (Verifying Stationary Increments)
We know that:
$$
N^\star(t+s) - N^\star(t) = N(m^{-1}(t+s)) - N(m^{-1}(t+s))
$$

By **definition N2** we know that:
$$
\begin{align}
P\{ N(m^{-1}(t+s)) - N(m^{-1}(t)) = n \} & = e^{ - (m(m^{-1}(t+s)) - m(m^{-1}(t))) } \frac{[m(m^{-1}(t+s)) - m(m^{-1}(t))]^n}{n!} \\
& = e^{ - (t + s - t) } \frac{(t + s - t)^n}{n!} \\
& = e^{ - s } \frac{s^n}{n!} \\
\end{align}
$$

This implies that $\forall s > 0$, $N(m^{-1}(t+s)) - N(m^{-1}(t+s))$ has the same distribution for all $t$, thus $N^\star$ has stationary increments.

### Part 3 (Verifying Axiom 3 from Definition 1 of Homogeneous Poisson Distribution)
As it was seen in the **part 2.2** of this proof:
$$
P\{ N^\star(t+s) - N^\star(t) = n \} = e^{ - s } \frac{s^n}{n!}
$$

Which implies that the number of events in any interval is poisson distributed with mean $\lambda s$ (in this case $\lambda = 1$), proving our result.




























