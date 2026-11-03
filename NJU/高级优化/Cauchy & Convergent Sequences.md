---
tags:
  - cauchy-sequence
  - convergent-sequence
  - metric-space
---
Date: 2026-11-03 : 17:51
***
## Caunchy Sequence
Let $X$ be a [[Metric Space]], a sequence $\{ x_{t} \}$ is a Cauchy Sequence if $\forall \epsilon > 0, \exists N \in \mathbb{N}$ so that
$$
i,j \geq N \quad \text{s.t.} \quad d(x_{i}, x_{j}) < \epsilon
$$

**Clearly Speaking**: If I give you a really small number, you should be able to find two elements of the sequence, whose distance is smaller than that tiny number i gave you.

## Convergent Sequence
The sequence $\{ x_{n} \}$ converges to a poin $x \in X$ if:
$$
\lim_{ n \to \infty } d(x_{n}, x) = 0
$$
