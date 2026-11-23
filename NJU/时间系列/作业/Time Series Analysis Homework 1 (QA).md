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

Since the arima model is $d=0$ and the characteristic equation of the left side (AR model) is
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
\boxed{\text{ARIMA(2,0,1), stationary, invertible}}
$$

##### b) $X_{t}=\frac{4}{3}X_{t-1}-\frac{1}{3}X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}$
The process can be rewritten as
$$
X_{t}-\frac{4}{3}X_{t-1}+\frac{1}{3}X_{t-2}=\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}
$$
$$
\implies X_{t} \left( 1-\frac{4}{3}B + \frac{1}{3}B^2 \right) = \epsilon_{t} \left( 1 - \frac{1}{4}B \right)
$$
$$
\implies X_{t} \left( 1-\frac{1}{3}B \right)(1-B)^1 = \epsilon_{t} \left( 1 - \frac{1}{4}B \right)
$$


Meaning that it is an **ARIMA(1,1,1)** process.

Since the ARIMA model has $d\neq 0$, then it is **NOT stationary**.

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
\boxed{\text{ARIMA(1,1,1), NOT stationary, invertible}}
$$

##### c) $X_{t}=2X_{t-1}-X_{t-2}+\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}-\frac{1}{4}\epsilon_{t-2}$
The process can be rewritten as
$$
X_{t}-2X_{t-1}+X_{t-2}=\epsilon_{t}-\frac{1}{4}\epsilon_{t-1}-\frac{1}{4}\epsilon_{t-2}
$$
$$
\implies X_{t}(1-2B+B^2)=\epsilon_{t}\left( 1-\frac{1}{4}B-\frac{1}{4}B^2 \right)
$$
$$
\implies X_{t}(1-B)^2=\epsilon_{t}\left( 1-\frac{1}{4}B-\frac{1}{4}B^2 \right)
$$

Meaning that it is an **ARIMA(0,2,2)** process.

Since the ARIMA model has $d\neq 0$, then it is **NOT stationary**.

The characteristic equation of the right side (MA model) is
$$
\begin{align}
& \Theta(z)=1-\frac{1}{4}z-\frac{1}{4}z^2 \\
& \implies z^2+z-4=0 \\
& \implies z_{1}=\frac{-1+\sqrt{ 17 }}{2}\approx1.56, \quad z_{2}=\frac{-1-\sqrt{ 17 }}{2}\approx-2.56
\end{align}
$$

Because the roots of the charcateristic equation of the MA part are outside of the unit circle, we conclude thath the process is **invertible**.

$$
\boxed{\text{ARIMA(0, 2, 2), NOT stationary, invertible}}
$$
---
## Exercise 2
#### Statement
Let the following ARMA(1,1) be given by
$$
(1-\phi B)X_{t}=(1-\theta B)\epsilon_{t}
$$

with $\mathbb{E}[\epsilon_{t}]=0$ and $\text{Var}[\epsilon_{t}]=\sigma_{\epsilon}^2$

### Question 2.1
#### Statement
Rewrite the process into AR form.

#### Solution
First of all, we have to check for invertibility, since this property ensures that the proecess can be expressed as an $\text{AR}(\infty)$ process.

For this, we find roots of the characteristic formula of the MA part
$$
\Theta(z)=1-\theta z=0
$$
$$
\implies z_{1}=\frac{1}{\theta}
$$

In the case that $|\theta|<1$ we can say that the process can be rewritten as an $\text{AR}(\infty)$ process.. Otherwise it cannot.

For instance, assuming $|\theta|<1$, we can rewrite the process considering the following pattern
$$
\begin{align}
\epsilon_{t}= & X_{t}-\phi X_{t-1}+\theta\epsilon_{t-1} \\
= & X_{t}-\phi X_{t-1}+\theta(X_{t-1}-\phi X_{t-2}+\theta\epsilon_{t-2}) \\
= & X_{t}+ X_{t-1}(\theta-\phi) -\phi\theta X_{t-2}+\theta^2\epsilon_{t-2} \\
= & X_{t}+ X_{t-1}(\theta-\phi) -\phi\theta X_{t-2}+\theta^2(X_{t-2}-\phi X_{t-3}+\theta\epsilon_{t-3}) \\
= & X_{t}+ X_{t-1}(\theta-\phi) + X_{t-2}\theta(\theta-\phi)-\theta^2\phi X_{t-3}+\theta^3\epsilon_{t-3} \\
\vdots
\end{align}
$$

Concluding that the $\text{AR}(\infty)$ representation is
$$
\epsilon_{t}=X_{t}\left( 1+(\theta-\phi)\sum_{j=0}^{\infty} B^{j+1}\theta^j \right)
$$

### Question 2.2
#### Statement
Rewrite the process into an MA form and find an expressiuon for $\text{Var}[X_{t}]$

#### Solution
First of all, we have to check for *stationarity*, since this property ensures that the proecess can be expressed as an $\text{MA}(\infty)$ process.

For this, we find the roots the characteristic formula of the AR part
$$
\Phi(z)=1-\phi z=0
$$
$$
\implies z_{1}=\frac{1}{\phi}
$$

For this root to be outside the unit circle, $|\phi|<1$ has to hold, allowing the process to be rewritten as a $\text{MA}(\infty)$ process. Otherwise it canot be written as a $\text{MA}(\infty)$ process.

For instance, assuming $|\phi|<1$, we can rewrite the process considering the following pattern
$$
\begin{align}
X_{t}=&\epsilon_{t}-\theta \epsilon_{t-1}+\phi X_{t-1} \\
= & \epsilon_{t}-\theta \epsilon_{t-1} +\phi(\epsilon_{t-1}-\theta \epsilon_{t-2}+\phi X_{t-2}) \\
= & \epsilon_{t}+\epsilon_{t-1}(\phi-\theta)-\psi\theta\epsilon_{t-2}+\phi^2X_{t-2} \\
= & \epsilon_{t}+\epsilon_{t-1}(\phi-\theta)-\psi\theta\epsilon_{t-2}+\phi^2(\epsilon_{t-2}-\theta \epsilon_{t-3}+\phi X_{t-3}) \\
= & \epsilon_{t}+\epsilon_{t-1}(\phi-\theta)+\epsilon_{t-2}\phi(\phi-\theta) -\phi^2\theta\epsilon_{t-3}+\phi^3X_{t-3} \\
= & \epsilon_{t}+\epsilon_{t-1}(\phi-\theta)+\epsilon_{t-2}\phi(\phi-\theta) -\phi^2\theta\epsilon_{t-3}+\phi^3(\epsilon_{t-3}-\theta \epsilon_{t-4}+\phi X_{t-4}) \\
= & \epsilon_{t}+\epsilon_{t-1}(\phi-\theta)+\epsilon_{t-2}\phi(\phi-\theta) + \epsilon_{t-3}\phi^2(\phi-\theta)-\phi^3\theta\epsilon_{t-4}+\phi^4X_{t-4} \\
\vdots
\end{align}
$$

Concluding that the $\text{MA}(\infty)$ representation is
$$
\boxed{X_{t}=\epsilon_{t}\left( 1+(\phi-\theta)\sum_{j=0}^{\infty}\phi^jB^{j+1}  \right)}
$$

Aditionally, $\text{Var}[X_{t}]$ can be expressed as
$$
\text{Var}[X_{t}]=\text{Var}[\epsilon_{t}+\epsilon_{t-1}(\phi-\theta)+\epsilon_{t-2}\phi(\phi-\theta) + \epsilon_{t-3}\phi^2(\phi-\theta)+\cdots]
$$

Given the fact that the white noise terms are uncorrelated and their expected values are zero, we can rewrite the previous expression as
$$
\begin{align}
\text{Var}[X_{t}] & =\text{Var}[\epsilon_{t}]+\text{Var}[\epsilon_{t-1}(\phi-\theta)]+\text{Var}[\epsilon_{t-2}\phi(\phi-\theta)] + \text{Var}[\epsilon_{t-3}\phi^2(\phi-\theta)]+\cdots \\
& = \sigma_{\epsilon}^2 + \sigma_{\epsilon}^2(\phi-\theta)^2+\sigma_{\epsilon}^2\phi^2(\phi-\theta)^2+\sigma_{\epsilon}^2\phi^4(\phi-\theta)^2+\cdots \\
 & = \sigma_{\epsilon}^2\left(1+( \phi-\theta)^2 \sum_{j=0}^{\infty} \phi^{2j} \right)
\end{align}

$$

Therefore
$$
\boxed{\text{Var}[X_{t}]=\sigma_{\epsilon}^2\left(1+( \phi-\theta)^2 \sum_{j=0}^{\infty} \phi^{2j} \right)}
$$


---
## Exercise 3
#### Statement
Consider the following ARMA(2, 1) process
$$
(1-1.2\bar{7}B+0.81B^2)X_{t}=(1-0.3)B\epsilon_{t}
$$

where $\{ \epsilon_{t} \}$ is white noise. Check if the process is stationary.

#### Solution
For this we have to analyze the roots of the AR part. Given its characteristic equation
$$
\Phi(z)=1-1.2\bar{7}z+0.81z^2
$$

We can rewrite the previous equatiuon as
$$
\Phi(z)=\frac{9^2}{10^2}z^2-\frac{23}{18}z+1=0
$$

Being the roots
$$
z_{1}=\frac{575}{729} - \frac{5i\sqrt{ 13019 }}{729}, \quad z_{2}=\frac{575}{729} + \frac{5i\sqrt{ 13019 }}{729}
$$

Therefore
$$
|z_{1}|=\frac{10}{9}, \quad |z_{2}|=\frac{10}{9}
$$

Because the roots are outside of the unit circle, then we can say that the process is **stationary**.

$$
\boxed{\text{The given ARMA(2, 1) process is stationary}}
$$
---
## Exercise 4
#### Statement
Consider a process $\{ X_{t} \}$ defined by
$$
(1-B+0.5B^2)X_{t}=(1+0.5B)\epsilon_{t}
$$

where $\{ \epsilon_{t} \}$ is white noise with $\mathbb{E}[\epsilon_{t}]=0$ and $\text{Var}[\epsilon_{t}]=\sigma_{\epsilon}^2$

### Question 4.1
#### Statement
Examine wheter $\{ X_{t} \}$ is stationary/invertible. Characterize the process.

#### Solution
##### Invertibility
To know if the process is invertible, we have to analyze the roots of the MA part, that is
$$
\Theta(z) = 1 + \frac{1}{2}z
$$

The root of the characteristic equation is
$$
z_{1}=-2
$$

Because the root is outside of the unit circle, then we can say that the current *process is invertible*.

##### Stationary
To know if the process is stationary, we have to analyze the roots of the AR part, that is
$$
\Psi(z)=1-z+\frac{1}{2}z^2
$$
The roots of the characteristic equation are
$$
z_{1}=1+i, \quad z_{2}=1-i
$$

Therefore
$$
|z_{1}|=\sqrt{ 2 }\approx1.4, \quad |z_{2}|=\sqrt{ 2 }\approx1.4
$$

Because the roots are outside of the unit circle, then we can say that the current *process is stationary*.

##### Charcaterization
Given that $\Psi(z)$ is a second degree polynomial and $\Theta(z)$ is a first degree polynomial, this is a **ARMA(2, 1)** process.

$$
\boxed{\text{ARMA(2, 1), stationary, invertible}}
$$

### Question 4.2
#### Statement
Determine the autocovariance and autocorrelation functions for $\{ X_{t} \}$. Sketch the autocorrelation function for $\text{lags}\leq 6$.

#### Solution
##### Autocovariance
Since we have the process
$$
X_{t}-X_{t-1}+0.5X_{t-2}=\epsilon_{t}+0.5\epsilon_{t-1}
$$

By mutiplying $\epsilon_{t-k}$ to both sides of the eqaution and obtainig the expected value we get
$$
\gamma_{\epsilon X}(k) - \gamma_{\epsilon X}(k - 1) + \gamma_{\epsilon Y}(k - 2) = 0
$$



By multiplying $X_{t-k}$ to both sides of the process equation and obtaining the expected value we get
$$
\gamma_{XX}(k) - \gamma_{XX}(k-1) + 0.5\gamma_{XX}(k-2)=\gamma_{\epsilon X}(k) +0.5 \gamma_{\epsilon X}(k - 1)
$$
