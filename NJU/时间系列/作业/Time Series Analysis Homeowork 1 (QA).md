**学生：** Moisés Adame Aguilar
**学号：** 522026375001

---
## Exercise 1
### Question 1.1
#### Statement
Rewrite the process $\{ X_{t} \}$ defined by
$$
X_{t}-\phi X_{t-1}=\epsilon_{t}
$$

such that $\{ X_{t} \}$ is exclusively described by past values of $\{ \epsilon_{t} \}$. If $\{ \epsilon_{t} \}$ is white noise, $X_{t}$ is siad to be expressed in an MA form

#### Solution
First, we can rearrange the terms as follows
$$
X_{t}=\epsilon_{t}+\phi X_{t-1}
$$

Then, we can substitute into $X_{t-1}=\epsilon_{t-1}+\phi X_{t-2}$, obtaining
$$
X_{t}=\epsilon_{t}+\phi (\epsilon_{t-1}+\phi X_{t-2}) =\epsilon_{t}+\phi \epsilon_{t-1}+\phi^2 X_{t-2}
$$

Again, plugging in $X_{t-2}=\epsilon_{t-2}+\phi X_{t-3}$
$$
X_{t}=\epsilon_{t}+\phi \epsilon_{t-1}+\phi^2 (\epsilon_{t-2}+\phi X_{t-3})= \epsilon_{t}+\phi \epsilon_{t-1}+\phi^2\epsilon_{t-2}+\phi^3 X_{t-3}
$$

As we can see a pattern arises, such that
$$
X_{t}=\sum_{i=0}^{\infty} \phi^i\epsilon_{t-i}
$$
### Question 1.2
#### Statement
To which category of ARIMA(p, d, q) does each of the following processes belong? Are they stationary/invertible?
	a) $X_{t}=\frac{5}{6}X_{t-1}-\frac{1}{6}X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}$
	b) $X_{t}=\frac{4}{3}X_{t-1}-\frac{1}{3}X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}$
	c) $X_{t}=2X_{t-1}-X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}-\frac{1}{4}\epsilon_{t-2}$

#### Solution
##### a) $X_{t}=\frac{5}{6}X_{t-1}-\frac{1}{6}X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}$
