---
tags:
  - stochastic-process
  - key-renewal-theorem
  - lattice-random-variable
  - blackwells-theorem
---
Date: 2026-11-12 : 20:03
***
## Lattice
A random variable $X$ is said to be a **lattice** ifthere exists a $d\geq0$ such that
$$
\sum_{n = 0}^\infty P\{ X=nd \} = 1
$$

The **largest d** with this property is the period of $X$.

It has this name, because the random variable takes the shape of a grid:
$$
0d, 1d,2d, 3d,\dots
$$

## Blackwell's Theorem
### Statement
**If $F$ is NOT lattice**:
$$
m(t+a) - m(t)=\frac{a}{\mu}
$$

**If $F$ is lattce with period d**:
$$
\mathbb{R}[\text{number of renewals at } nd] = \frac{d}{\mu}
$$

### Sketch Proof

