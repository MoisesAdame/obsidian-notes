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
Given a group $G$, if it is commutative $\forall x, y \in \mathcal{G}: x \otimes y = y \otimes x$, then it is an *abelian group*.

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
Considering a vector space $V$ with $\mathbf{x_{1}}, \cdots, \mathbf{x_{n}} \in V$. Those vectors are considered *linearly dependent* if there exists a non-trivial way ($\lambda_{i} = \cdots = \lambda_{n} = 0$) that their *linear combination* yields $\mathbf{0}$, that is to say:
$$
\mathbf{0} = \sum_{i = 1}^{n} \lambda_{i} \cdot \mathbf{x_{i}}
$$

## Definition of Span
Given a vector space $V$ and set of vectors $\mathcal{A} = \{ \mathbf{x_{1}}, \cdots, \mathbf{x_{n}} \} \in V$. Then, if every $\mathbf{v} \in V$ can be expressed as a linear combination of $\mathcal{A}$, we say that $V = span[A]$.

## Definition of Basis
A *generating set* $\mathcal{A}$ of $V$ is called *minimal* if there exists no smaller set $\tilde{A} \subseteq A \subseteq \mathcal{V}$. As well, every linearly independent generating set of $V$ is minimal and is called a **basis of $V$**. It is *minimal* if the set is linearly independent

## Definition of a Linear Mapping
For vector spaces $V$ and $W$ a mapping $\Phi: V \to W$ is called a linear mapping or linear transformation if:
$$
\forall \mathbf{x}, \mathbf{y} \in V \forall \alpha, \beta \in \mathbb{R}: \Phi(\alpha \mathbf{x} + \beta \mathbf{y}) = \alpha \Phi(\mathbf{x}) + \beta \Phi(\mathbf{y})
$$

## Rank & Dimension
They both describe very similar concepts. The **rank** is the number of linearly independent columns in a matrix. The **dimension** is the number of different directions you can go, for example $A = span\left[\begin{pmatrix} 1 & 0 \end{pmatrix}^T, \begin{pmatrix} 0 & 1 \end{pmatrix}^T \right]$. The dimension is 2.
$$
A = 
\begin{pmatrix}
1 & 0 & 1 \\
0 & 1 & 1 \\
0 & 0 & 0 \\
\end{pmatrix}
$$

Here, the $rank(A) = 2$.

## Change of Basis
Suppose we have a linear transformation $A_{\phi}: V \to W$ (this means that goes form the vector space $V$ to $W$). BUT!!! this linear transformation only works from and to using the following bases (They span over $V$ and $W$ respectively):
$$
B = \begin{pmatrix}b_{1}, b_{2}, \cdots, b_{n}\end{pmatrix}
$$
$$
C = \begin{pmatrix}c_{1}, c_{2}, \cdots, c_{m}\end{pmatrix}
$$

We will define the following ordered bases, they too, span the vector spaces $V$ and $W$ respectively:

$$
B' = \begin{pmatrix}b_{1}', b_{2}', \cdots, b_{n}'\end{pmatrix}
$$
$$
C' = \begin{pmatrix}c_{1}', c_{2}', \cdots, c_{m}'\end{pmatrix}
$$
### Brief Example
The following is an example. We have two basis, both belong to $\mathbb{R}^2$, we are going to call the first one $E$ (for extended) and the second one $N$ (for normal), defined as follows:
$$
E = \left(
\begin{pmatrix}
2 \\
0 \\
\end{pmatrix}, 
\begin{pmatrix}
0 \\
2 \\
\end{pmatrix}
\right)
$$
$$
N = \left(
\begin{pmatrix}
1 \\
0 \\
\end{pmatrix}, 
\begin{pmatrix}
0 \\
1 \\
\end{pmatrix}
\right)
$$
If we use the vectors of $E$ as the column for a linear transformation $A_{E}$ and we multiply a vector, what do we get?
$$
\begin{pmatrix}
2 & 0 \\
0 & 2 \\
\end{pmatrix}
\begin{pmatrix}
4 \\
2
\end{pmatrix}
=
\begin{pmatrix}
8 \\
4
\end{pmatrix}
$$

As we can see, the linear transformation $A_{E}$ takes the vector from $E \to N$.
### End of Example

Resuming our proof, we can see that using the columns of $B'$ we have a linear transformation that we'll call $S : B' \to B$. We know that $A_{\phi}: B \to C$ and, knowing that another linear transformation that we'll call $T$, which uses the columns of $C'$ goes from: $T: C' \to C$ if we obtain its inverse, we'll get: $T^{-1}: C \to C'$, which, put together looks like: $B' \to B \to C \to C'$. (Remember that the operations go form right to left, because this is matrix multiplication), thus:
$$
A_{\phi}' = T^{-1}A_{\phi}S
$$

## Relation Between Invertibility and Determinant




