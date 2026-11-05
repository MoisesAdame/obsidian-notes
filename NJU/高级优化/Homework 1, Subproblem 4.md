---
tags:
---
Date: 2026-11-05 : 11:26
***
## Subproblem 4
**Part 1**
To obtain this closed form, first we have to obtain the:
$$
Q^\star = argmin_{Q}\left\{  \frac{1}{2}||Q- \Sigma||^2_{F} + \eta g(Q) \right\}
$$

By definition of $g$ it can be rewritten as:
$$
Q^\star = argmin_{Q}\left\{  \frac{1}{2}\|Q- \Sigma\|^2_{F} + \eta \tau \|Q\|_{*}  \right\}
$$
Now, to obtain it's closed form it is important to do an analysis of the singular values of $Q^*$, which would look as follows:
$$
[Q^\star]_{i} = argmin_{q_{i} \geq 0} \left\{  \frac{1}{2}(q_{i} -\sigma_{i})^2  + \mu \eta q_{i} \right\}
$$

Minimizing this we get:
$$
q_{i} - \sigma_{i} + \mu \eta = 0
$$

Thus:
$$
q_{i} = (\sigma_{i} - \mu \eta)_{+}
$$

**Part 2**


