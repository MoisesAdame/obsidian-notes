---
tags:
---
Date: 2025-11-30 : 11:13
***
## Definition of a Group
Considering a set $\mathcal{G}$ and an operation $\otimes : \mathcal{G} \times \mathcal{G} \rightarrow \mathcal{G}$. Then $G := (\mathcal{G}, \otimes)$ is called a group if the following hold:
1. **Closure of $\mathcal{G}$ under $\otimes$:** $\forall x, y \in \mathcal{G}: x \otimes y \in \mathcal{G}$ 
2. **Associativity:** $\forall x, y, z \in \mathcal{G}: (x \otimes y) \otimes z = x \otimes (y \otimes z)$
3. **Neutral Element:** $\exists e \in \mathcal{G} \forall x \in \mathcal{G} : x \otimes e = y$
4. **Inverse Element:** $\forall x \in \mathcal{G} \exists y \in \mathcal{G}: x \otimes y = e$

## Definition of an Abelian Group
Given a group $G$, then if it is commutative $\forall x, y \in \mathcal{G}: x \otimes y = y \otimes x$, then it is an *abelian group*.

