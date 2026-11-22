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
\boxed{X_{t}=\sum_{i=0}^{\infty} \phi^i\epsilon_{t-i}}
$$
### Question 1.2
#### Statement
To which category of ARIMA(p, d, q) does each of the following processes belong? Are they stationary/invertible?
	a) $X_{t}=\frac{5}{6}X_{t-1}-\frac{1}{6}X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}$
	b) $X_{t}=\frac{4}{3}X_{t-1}-\frac{1}{3}X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}$
	c) $X_{t}=2X_{t-1}-X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}-\frac{1}{4}\epsilon_{t-2}$

#### Solution
##### a) $X_{t}=\frac{5}{6}X_{t-1}-\frac{1}{6}X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}$
The process can be rewritten as
$$
X_{t}-\frac{5}{6}X_{t-1}+\frac{1}{6}X_{t-2}=\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}
$$
$$
\implies X_{t} \left( 1-\frac{5}{6}B + \frac{1}{6}B^2 \right) = \epsilon_{t} \left( 1 - \frac{1}{4}B \right)
$$



Which is an **ARMA(2,1)** process, meaning that it is an **ARIMA(2,0,1)** process

The characteristic equation of the left side (AR model) is
$$
\begin{align}
& \Phi(z) = 1-\frac{5}{6}z+\frac{1}{6}z^2 \\
& \implies \left( 1-\frac{1}{3}z \right)\left( 1-\frac{1}{2}z \right)=0 \\
& \implies z_{1}=3, \quad z_{2} =2
\end{align}
$$

Because the roots of the charcateristic euqation of the AR part are outside of the unit circle, we conclude thath the process is **stationary**.

The characteristic equation of the right side (MA model) is
$$
\begin{align}
& \Theta(z)=1-\frac{1}{4}z \\
& \implies 1-\frac{1}{4}z=0 \\
& \implies z_{1}=4
\end{align}
$$

Because the root of the charcateristic equation of the MA part are outside of the unit circle, we conclude thath the process is **invertible**.

$$
\boxed{\text{ARIMA(2,0,1), invertible, stationary}}
$$

##### b) $X_{t}=\frac{4}{3}X_{t-1}-\frac{1}{3}X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}$
The process can be rewritten as
$$
X_{t}-\frac{4}{3}X_{t-1}+\frac{1}{3}X_{t-2}=\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}
$$

Which is an **ARMA(1,1)** process, meaning that it is an **ARIMA(1,0,1)** process.

The characteristic equation of the left side (AR model) is
$$
\begin{align}
& \Phi(z) = 1-\frac{4}{3}z+\frac{1}{3}z^2 \\
& \implies \left( 1-z \right)\left( 1-\frac{1}{3}z \right)=0 \\
& \implies z_{1}=1, \quad z_{2} =3
\end{align}
$$

Because the roots of the charcateristic euqation of the AR part are outside of the unit circle, we conclude that the process is **invertible**.

The characteristic equation of the right side (MA model) is
$$
\begin{align}
& \Theta(z)=1-\frac{1}{4}z \\
& \implies 1-\frac{1}{4}z=0 \\
& \implies z_{1}=4
\end{align}
$$

Because the root of the charcateristic equation of the MA part are outside of the unit circle, we conclude thath the process is **stationary**.


$$
\boxed{\text{ARIMA(1,0,1), reversible, stationary}}
$$


