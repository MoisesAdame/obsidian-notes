## Problem 1 (Definition 1 -> Definition 2)
### Part 1 (Obtaining $P\{ N(h) = 1 \}$)
Let $s = 0$, then using the Definition 1 section (iii), we get:
$$
P\{ N(0 + t) - N(0) = n\} = e^{-\lambda t} \frac{(\lambda t)^n}{n!}
$$

Because of condition (i), we get:
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
P\{ N(t) = 1\} = e^{-\lambda t} \lambda t = \lambda t \left(1 - \lambda t + \frac{(\lambda t )^2}{2!} + \frac{(\lambda t )^3}{3!} + \cdots \right)
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

That is why we get (The point (iii) of Definition 2)
$$
P\{ N(t) = 1\} = \lambda t + o(t)
$$

If we change variables from $t = h$, then we get:
$$
P\{ N(h) = 1\} = \lambda h + o(h)
$$

### Part 2 (Obtaining $P\{ N(h) \geq 2 \}$)
Let $s = 0$, then using the Definition 1 section (iii), we get:
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
P\{ N(h) \geq 2 \} = e^{-\lambda h} \frac{(\lambda t)^2}{2!} + e^{-\lambda h} \frac{(\lambda t)^3}{3!} + \cdots
$$
$$
P\{ N(h) \geq 2 \} = e^{-\lambda h} \left( \frac{(\lambda t)^2}{2!} +  \frac{(\lambda t)^3}{3!} + \cdots \right)
$$
Because of the Taylor Expansion of $e^{\lambda t}$, we know that:

$$
P\{ N(h) \geq 2 \} = e^{-\lambda h} \left( e^{\lambda h} -\lambda h - 1\right)
$$

If we distribute the $e^{-\lambda h}$ inside the parenthesis, we would get:
$$
P\{ N(h) \geq 2 \} = 1 -\lambda h e^{-\lambda h}  - e^{-\lambda h} = 1 - e^{-\lambda h }(\lambda h + 1)
$$

Expanding $e^{-\lambda h}$ in its Taylor Expansion we get:
$$
P\{ N(h) \geq 2 \} = 1-(\lambda h+1)\left(1 - (\lambda h) + \frac{(\lambda h)^2}{2!} - \frac{(\lambda h)^3}{3!} + \cdots \right)
$$

After distributing the $(\lambda h+1)$ parenthsis we get:
$$
P\{ N(h) \geq 2 \} = 1 + \left(-(\lambda h) + (\lambda h)^2 - \frac{(\lambda h)^3}{2!} + \frac{(\lambda h)^4}{3!} + \cdots \right) + \left(-1 + (\lambda h) - \frac{(\lambda h)^2}{2!} + \frac{(\lambda h)^3}{3!} + \cdots \right)
$$

Analizing this, we can se that $1$ and $-1$ cancel each other and also $-(\lambda h)$ and $-(\lambda h)$ cancel each other, thus, we get:
$$
P\{ N(h) \geq 2 \} =  \left( (\lambda h)^2 - \frac{(\lambda h)^3}{2!} + \frac{(\lambda h)^4}{3!} + \cdots \right) + \left( - \frac{(\lambda h)^2}{2!} + \frac{(\lambda h)^3}{3!} + \cdots \right)
$$

Then, it is easy to see that:
$$
P\{ N(h) \geq 2 \} = o(h)
$$

## Problem 2 (Gamma Function)
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
f_{S_{n}}(t) = e^{-\lambda t} \left(-\lambda \frac{(\lambda t)^n}{n!}  +\lambda\frac{(\lambda t)^{n-1}}{(n-1)!} \right) + e^{-\lambda t} \left(-\lambda \frac{(\lambda t)^{n+1}}{(n+1)!}  +\lambda\frac{(\lambda t)^{n}}{(n)!} \right) + e^{-\lambda t} \left(-\lambda \frac{(\lambda t)^{n+2}}{(n+2)!}  +\lambda\frac{(\lambda t)^{n+1}}{(n+1)!} \right) + \cdots
$$
$$
f_{S_{n}}(t) = e^{-\lambda t}\lambda\frac{(\lambda t)^{n-1}}{(n-1)!}
$$

And thus, we see that $S_{n}$ has a gamma distribution with parameters $\lambda$ and $n$

### Solution 2 (Moment Generating Functions)
#### Part 1 (Obtain MGF of $S_{n}$)
We can obtain the Moment Generating Function of $S_{n}$ as follows:
$$
M_{S_{n}}(t) = \mathbb{E}[e^{tS_{n}}] = \mathbb{E}[e^{t(X_{1} + X_{2} + \cdots X_{n})}] = \mathbb{E}[e^{tX_{1}} e^{tX_{2}} \cdots e^{tX_{n}} ]
$$

Because $X_{k}, k\geq_{1}$ are independent, we can say:
$$
\mathbb{E}[e^{tX_{1}} e^{tX_{2}} \cdots e^{tX_{n}} ][e^{tX_{1}} e^{tX_{2}} \cdots e^{tX_{n}} ] = \mathbb{E}[e^{tX_{1}}]\mathbb{E}[e^{tX_{2}}] \cdots \mathbb{E}[e^{tX_{n}}]
$$

Now, lets obtain the Moment Generating Function of $X_{k}$. 
$$
M_{X_{k}}(t) = \mathbb{E}[e^{tX_{k}}] = \int_{0}^{\infty}e^{tx}\lambda e^{-\lambda x}dx = \lambda \int_{0}^{\infty}e^{x(t-\lambda)}
dx = \frac{\lambda}{t-\lambda}e^{x(t-\lambda)} \Big|_{0}^\infty$$

For the following to converge we need $t < \lambda$, that way, we have:
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
f_{X}(x) = \lambda e^{-\lambda x}\frac{(\lambda x)^{n-1}}{(n-1)!}
$$

To obtain its Moment Generating Function:
$$
M_{X}(t) = \mathbb{E}[e^{tX}] = \int_{0}^{\infty}e^{xt}\lambda e^{-\lambda x}\frac{(\lambda x)^{n-1}}{(n-1)!}dx
$$

We can manipulate the terms inside the integral, so the integral we have to solve is:
$$
\int_{0}^{\infty}e^{x t} \cdot \frac{\lambda^n x^{n-1}e^{-\lambda x}}{(n-1)!}dx
$$

Pulling out the constants and manipulating the inside of the integral, we get:
$$
\frac{\lambda^n}{(n-1)!}\int_{0}^{\infty}e^{x (t-\lambda)} x^{n-1}dt
$$

Letting $u = x(\lambda-t)$:
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

This leads that the MGF of the gamma distribution is:
$$
M_{X}(t) = \frac{\lambda^n}{(n-1)!} \Gamma(n) = \left(\frac{\lambda}{\lambda-t}\right)^n
$$

Because the property of **uniqueness if the Moment Generating Functions** we can say that $S_{n}$ has a gamma distribution with parameters $n$ and $\lambda$, because:
$$
M_{S_{n}}(t) = M_{X}(t) = \left(\frac{\lambda}{\lambda-t}\right)^n
$$

## Problem 3 (Independent Poisson Process)
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

Now, because by definition $N_{i}(t_{k+1}) - N_{i}(t_{k})$ where $i \in \{ 1, 2, \dots, n \}$ is independent and $N_{i}$, $N_{j}$ where $i \neq j$ are independent, then the vector
$$
N_{1}()
$$

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
(\lambda_{1} + \lambda_{2} + \cdots + \lambda_{n})^{a} = \sum_{a_{1} + a_{2} + \cdots + a_{n} = a} \frac{a!}{a_{1}! a_{2}! \cdots a_{n!}} \lambda_{1}^{a_{1}}\lambda_{2}^{a_{2}} \cdots \lambda_{n}^{a_{n}}
$$

Then:
$$
= e^{-t(\lambda_{1}+\lambda_{2}+\cdots+\lambda_{n})} \frac{(t(\lambda_{1} + \lambda_{2} + \cdots + \lambda_{n}))^{a}}{a!}
$$

Obtaining a Poisson Distribution whose rate is $\sum_{i = 1}^{n} \lambda_{i}$





