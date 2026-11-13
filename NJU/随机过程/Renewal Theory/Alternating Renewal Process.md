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


