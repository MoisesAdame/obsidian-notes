---
tags:
---
Date: 2024-11-28 : 14:56
***
##### Quick Exercise 3.1 Let $N = R^{C}$ What is the conditional probability of $P(N | L)$
We know that $N$ is:
$$
N = R^{C} = \{ May, Jun, Jul, Aug \}
$$
Thus, following the conditional probability formula, we get:
$$
P(N | L) = \frac{P(N \cap L)}{P(L)} = \frac{\frac{3}{12}}{\frac{7}{12}} = \frac{3}{7}
$$
##### Quick Exercise 3.2 Calculate $P(C | A)$ and $P(C^{C} | A ∪ B)$.
For $P(C | A)$ we just have to apply the conditional probability function, shown as follows:
$$
P(C | A) = \frac{P(C \cap A)}{P(A)} = \frac{\frac{2}{6}}{\frac{2}{6}} = 1
$$
For the next section, we just have to obtain both $C^{C}$ and $A \cup B$ as follows:
$$
C^{C} = \{ 123, 321 \}
$$
$$
A \cup B = \{ 123, 321, 312, 213 \}
$$
Now, we just apply the conditional probability formula:
$$
P(C^{C} | A \cup B) = \frac{P(C^{C} \cap (A \cup B))}{P(A \cup B)} = \frac{\frac{2}{6}}{\frac{4}{6}}=\frac{1}{2}
$$

##### Quick Exercise 3.3 Show that $P(A | C) + P(A^{C} | C) = 1$
We know that:
$$
P(A | C) + P(A^{C} | C) = \frac{P(A \cap C)}{P(C)} + \frac{P(A^{C} \cap C)}{P(C)} = \frac{P(C \cap (A \cup A^{C}))}{P(C)}
$$
We know that $A \cup A^{C} = \Omega$, and consequently, $\Omega \cap C = C$, which means that:
$$
P(A | C) + P(A^{C} | C) = \frac{P(C)}{P(C)} = 1
$$

