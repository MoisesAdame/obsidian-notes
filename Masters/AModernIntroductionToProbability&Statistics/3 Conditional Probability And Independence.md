---
tags:
  - probability
  - probability/conditional-probability
---
Date: 2024-11-28 : 14:46
***
## 3.1 Conditional Probability
Sometimes, something that happened influences the probability, that  is called *conditional probability*. If this is not the case and probability stays the same as before, we have *independence*.

Assume we have the following sets $L = \{ Jan, Mar, May, Jul, Aug, Oct, Dec \}$ and $R = \{ Jan, Feb, Mar, Apr, Sep, Oct, Nov, Dec \}$. It is easy to compute the probability of getting either $L$ or $R$. But what if someone tells us that he was bro in a month from the set $L$, the what is the probability of his birthday belonging to $R$. Because $L$ reduces the scope, then we have a different probability $R \cap L = \{ Jan, Mar, Oct, Dec \}$ then:
$$
P(R | L) = \frac{4}{7}
$$

Now, let's consider the three envelope problem. We have two events $A = \{ 213, 312 \}$ envelope 1 is in the middle and $B = \{ 123, 321 \}$ envelope 2 is in the middle. Because there are 6 possible combinations we know $P(A) = P(B) = \frac{1}{3}$. Now, assume we know that the envelopes are not in order, then what are the probabilities of both $A$ and $B$ occurring. Let $C = \{ 132, 213, 231, 312 \}$. We know that:
$$
P(A | C) = \frac{P(A \cap C)}{P(C)} = \frac{\frac{2}{6}}{\frac{4}{6}} = \frac{1}{2}
$$
$$
P(B | C) = \frac{P(B \cap C)}{P(C)} = \frac{0}{\frac{4}{6}} = 0
$$
These results obey intuition, because it is impossible to get an envelope from the set $B$ if the envelopes are not in order, while it is a 50/50 chance if we use the set $A$.

>[!NOTE] Definition of Conditional Probability
>The **Conditional Probability** of A given B is:
>$P(A | B) = \frac{P(A \cap B)}{P(B)}$
>provided that $P(B) > 0$

We now that for normal probabilities $P(A) + P(A^{C}) = 1$, but for conditional probability, it is possible to prove that:
$$
P(A | C) + P(A^{C} | C) = 1
$$

## 3.2 The Multiplication Rule
>[!NOTE] Definition of the Multiplication Rule
>For any events $A$ and $C$:
>$P(A \cap C) = P(A | C) \cdot P(C)$

Assume we want to know the probability on **no coincident b-days**. For two people is easy, we just:
$$
P(B_{2}) = 1 - \frac{1}{365}
$$

For three people it gets a little more tricky, lets say we need $A_{3} \cap B_{2} = B_{3}$, which using the *Multiplication Rule* can be expressed as follows:
$$
P(B_{3}) = P(A_{3} \cap B_{2}) = P(A_{3} | B_{2}) \cdot P(B_{2})
$$






## 3.6 Exercises
Here: [[3 Exercises]]

