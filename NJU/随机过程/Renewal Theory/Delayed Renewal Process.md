---
tags:
  - stochastic-process
  - delayed-renewal-process
---
Date: 2026-11-14 : 15:41
***
## Intuition
A Renewal Process where the *first interarrival time has a different distribution* than the rest.

## Definition
Let $\{ X_{n}, n = 1, 2,\dots \}$ be a seuqnce of independent *(not identically distributed)* random variables with $X_{1}$ having distribution $G$ and $X_{n}, n\geq 2$ having distribution $F$. We define:
$$
N_{D}(t) = \text{sup}\{ n: S_{n} \leq t \}
$$

So $\{ N_{D}(t), t \geq 0 \}$ is the *delayed renewal process*.

