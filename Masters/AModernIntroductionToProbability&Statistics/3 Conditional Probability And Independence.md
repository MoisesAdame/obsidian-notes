---
tags:
---
Date: 2024-11-28 : 14:46
***
## 3.1 Conditional Probability
Sometimes, something that happened influences the probability, that  is called *conditional probability*. If this is not the case and probability stays the same as before, we have *independence*.

Assume we have the following sets $L = \{ Jan, Mar, May, Jul, Aug, Oct, Dec \}$ and $R = \{ Jan, Feb, Mar, Apr, Sep, Oct, Nov, Dec \}$. It is easy to compute the probability of getting either $L$ or $R$. But what if someone tells us that he was bro in a month from the set $L$, the what is the probability of his birthday belonging to $R$. Because $L$ reduces the scope, then we have a different probability $R \cap L = \{ Jan, Mar, Oct, Dec \}$ then:
$$
P(R | L) = \frac{4}{7}
$$

Now, let's consider the three envelope p