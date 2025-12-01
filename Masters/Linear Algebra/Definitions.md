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

## Definition of a (Real-Valued) Vector Space
A real-valued vector space $V = (\mathcal{V, +,\cdot})$ is a set $\mathcal{V}$ with two operations:
$$
+: \mathcal{V} \times \mathcal{V} \rightarrow \mathcal{V}
$$
$$
\cdot: \mathbb{R} \times \mathcal{V} \rightarrow \mathcal{V}
$$
Where:
1. $(\mathcal{V}, +)$ is an *abelian group*.
2. Distributivity
	1. $\forall \lambda \in \mathbb{R} \mathbf{x}, \mathbf{y} \in \mathcal{V}: \lambda(\mathbf{x} + \mathbf{y}) = \lambda \mathbf{x} + \lambda \mathbf{y}$
	2. $\forall \alpha, \beta \in \mathbb{R} \mathbf{x}\in \mathcal{V}: (\alpha + \beta)\mathbf{x} = \alpha \mathbf{x} + \beta \mathbf{y}$
3. Associativity: $\forall \alpha, \beta \in \mathbb{R} \mathbf{x} \in \mathcal{V}: \alpha(\beta \mathbf{x}) = (\alpha \beta)\mathbf{x}$
4. Neutral element: $\forall \mathbf{x} \in \mathcal{V}: 1 \mathbf{x} = x$

## Definition of a Vector Subspace
Let $V = (\mathcal{V}, +, \cdot)$ be a vector space and $\mathcal{U} \subseteq \mathcal{V}$, where $\mathcal{U} \neq \emptyset$. Then $U = (\mathcal{U}, +, \cdot)$ is called a *vector subspace of V*.

## Definition of Linear Combination
Given the vector space $V$ and a finite number of vectors $\mathbf{x_{1}}, \cdots, \mathbf{x_{n}}$. Then, every $\mathbf{v}$ of the form:
$$
\mathbf{v} = \sum_{i = 1}^{n} \lambda_{i} \cdot \mathbf{x_{i}}
$$
With $\lambda_{i}, \cdots, \lambda_{n} \in \mathbb{R}$ is a linear combination of the vectors $\mathbf{x_{1}}, \cdots, \mathbf{x_{n}}$.

## Linear Dependence
Considering a vector space $V$ with $\mathbf{x_{1}}, \cdots, \mathbf{x_{n}} \in V$. 