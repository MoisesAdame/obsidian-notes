---
tags:
---
Date: 2024-11-19 : 12:30
***
## 2.1 Sample Spaces
**Definition:** The set of possible outcomes of an experiment.
**Example:** For a coin toss, $\Omega = \{ H, T \}$

## 2.2 Events
**Definition:** A subset of the sample space.
**Example:** When asking the month of a birthday of a set of people, while all the months are the sample space, $A = \{ Jan, Oct, Dec \}$ is a possible event because $A \subset \Omega$.

## 2.3 Probability
In general, we want to express how likely it is that an event occurs, that is done trough a *probability function*.

**Definition:** A *probability function $P$* on a finite sample space $\Omega$ assigns to each event $A \subset \Omega$ a number $0 \leq P(A) \leq 1$ such that:
1. $P(\Omega) = 1$
2. $P(A \cup B) = P(A) + P(B)$ if $A$ and $B$ are disjoint.

If $A$ and $B$ are not disjoint, to compute probabilities we have to use the following rule: $A = (A \cap B) \cup (A \cap B^{C})$, thus:
$$
P(A) = P(A \cap B) + P(A \cap B^{C})
$$

### The Probability of a Union
We know that $A \cup B = B \cup (A \cap B^{C})$, thus:
$$
P(A \cup B) = P(B) + P(A \cap B^{C})
$$
Considering the previous identity, we get:
$$
P(A \cup B) = P(B) + P(A) - P(A \cap B)
$$

Additionally we know that $A \cup A^{C} = \Omega$, which means:
$$
P(A) + P(A^{C}) = P(\Omega) = 1 \implies P(A) = 1 - P(A^{C})
$$
## 2.4 Products of Sample Spaces
Sometimes experiments are performed more than once, when that is the case we have to perform a **cartesian product** between the sample spaces, that is:
$$
\Omega = \Omega_{1} \times \Omega_{2} = \{ (\omega_{1}, \omega_{2}) : \omega_{1} \in \Omega_{1}, \omega_{2} \in \Omega_{2} \}
$$

If the experiments are not mutually influenced, and every scenario is equally likely, if $|\Omega_{1}| = r$ and $|\Omega_{2}| = s$, then the probability for any  scenario to occur is:
$$
P(\{ (\omega_{x}, \omega_{y} )\}) = \frac{1}{rs}
$$

## 2.5 An Infinite Sample Space
This can happen for example in an experiment of *how many coin tosses, until we get tails*. Here the sample space is $\Omega = \mathbb{N} - \{ 0 \}$. What is the probability function for this scenario?

Let generalize it to $n$, where $(H, H, H, \dots, T)$, our sample space would be:
$$
\Omega = \{ H, T \} \times \{ H, T \} \times \cdots \times \{ H, T \}
$$

Considering that the probability of getting tails is $p$ and getting head is $1 - p$, we get:
$$
P(\{ n \}) = p (1-p)^{n - 1}
$$

Now, how would you calculate $P(\Omega)$? Thats were the definition of P is extended:

**Definition:** A *probability function* on an infinite (or finite) sample space $\Omega$ assigns to each event $A$ in $\Omega$ a number $P(A)$ in $[0, 1]$, such that:
1. $P(\Omega) = 1$
2. $P\left( \bigcup_{i = 1}^{\infty}A_{i} \right) = \sum_{i = 1}^{\infty}P(A_{i})$ if $A_{1}, A_{2}, A_{3}, \dots$ are disjoint.

## 2.6 Exercises
#### Exercise 2.1: Let $A$ and $B$ be two events in a sample space for which $P(A) = 2/3$, $P(B) = 1/6$, and $P(A \cap B) = 1/9$. What is $P(A \cup B)$?

We know that $P(A \cup B) = P(A) + P(B) - P(A \cap B)$, then:
$$
P(A \cup B) = \frac{2}{3} + \frac{1}{6} - \frac{1}{9} = \frac{12 + 3 - 2}{18} = \frac{13}{18}
$$
#### Exercise 2.4: We consider events $A$, $B$, and $C$, which can occur in some experiment. Is it true that the probability that only A occurs (and not B or C) is equal to $P(A \cup B \cup C) − P(B) − P(C) + P(B \cap C)$?

We know that:
$$
P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B \cap C)
$$
If we plug this equation into the next one:
$$
P(A) = P(A \cup B \cup C) − P(B) − P(C) + P(B \cap C)
$$
We get:
$$
P(A \cap B \cap C) = P(B \cap C)
$$
Which, only holds if the sets are **disjoint**.

#### Exercise 2.7 Let $A$ and $B$ be two events. Suppose that $P(A) = 0.4$, $P(B) = 0.5$, and $P(A \cap B) = 0.1$. Find the probability that $A$ or $B$ occurs, but not both.

We want:
$$
(A^{C} \cap B) \cup (A \cap B^{C}) = (B - A \cup B) \cup (A - A \cup B)
$$

This means:
$$
P(B - A \cup B) + P(A - A \cup B) = (0.4 - 0.1) + (0.5 - 0.1) = 0.7
$$

This is the correct consideration, because if we did $P(A \cup B)$, then we would be considering A, B or both.

#### Exercise 2.8: Suppose the events $D_{1}$ and $D_{2}$ represent disasters, which are rare: $P(D_{1}) ≤ 10^{−6}$ and $P(D_{2}) ≤ 10^{−6}$. What can you say about the probability that at least one of the disasters occurs? What about the probability that they both occur?

For **at least one occurring** we have to consider:
$$
P(D_{1} \cup D_{2}) = P(D_{1}) + P(D_{2}) \leq 2 \cdot 10^{-6}
$$

For both of them to occur, we have to consider that $D_{1}  \subset D_{2}$ or that $D_{2} \subset D_{1}$. Considering that we can say that:
$$
P(D_{1} \cap D_{2}) = min\{ P(D_{1}), P(D_{2}) \} \leq 10^{-6} 
$$
#### 2.9 We toss a coin three times. For this experiment we choose the sample space $\Omega = \{ HHH,THH,HTH,HHT,TTH,THT,HTT,TTT \}$. (a) Write down the set of outcomes corresponding to each of the following events: A, B, C and D. (b) Write down the set of outcomes corresponding to each of the following events: $A^{C}$, $A∪(C ∩D)$, and $A∩D^{C}$.

For a we can say that:
$$
A = \{ TTH, HTT, THT \}
$$
$$
B = \{ TTH, HTT, THT, TTT \}
$$
$$
C = \{ HHT, HHH, HTT, HTT \}
$$
$$
D = \{ THH, TTH, THT, TTT \}
$$
For b we can say:
$$
A^{C} = \{ HHH,THH,HTH,HHT,TTT \}
$$
$$
A \cup (C \cap D) = \{ TTH, HTT, THT \}
$$
#### Exercise 2.10 In some sample space we consider two events $A$ and $B$. Let $C$ be the event that $A$ or $B$ occurs, but not both. Express $C$ in terms of $A$ and $B$, using only the basic operations “union,” “intersection,” and “complement.”
It can be originally expressed as follows:
$$
C = (A \cup B) \cap (A \cap B)^{C}
$$
Using DeMorgan's Laws we can simplify this expression to:
$$
C = A \cup B \cap (A^{C} \cup B^{C}) = A^{C}\cap(A \cup B) \cup B^{C}\cap(A \cup B) = (A^{C} \cap B) \cup (B^{C} \cap A)
$$
#### Exercise 2.11 An experiment has only two outcomes. The first has probability $p$ to occur, the second probability $p^{2}$. What is $p$?
We know that if the first outcome has a probability of $p$ to occur, then the second outcome must have a probability of $1 - p$, thus, solving for $p$ given the information we have:
$$
1 - p = p^{2} \implies p^{2} + p - 1 = 0 
$$

Then after solving we get that:
$$
p = -\frac{1}{2} \pm \frac{\sqrt{ 5 }}{2}
$$
But because $0 \leq p \leq 1$, then:
$$
p = -\frac{1}{2} + \frac{\sqrt{ 5 }}{2}
$$

#### Exercise 2.12 In the UEFA Euro 2004 playoffs draw 10 national football teams were matched in pairs. A lot of people complained that “the draw was not fair,” because each strong team had been matched with a weak team (this is commercially the most interesting). It was claimed that such a matching is extremely unlikely. We will compute the probability of this “dream draw” in this exercise. In the spirit of the three-envelope example of Section 2.1 we put the names of the 5 strong teams in envelopes labeled 1,2,3,4, and 5 and of the 5 weak teams in envelopes labeled 6, 7, 8, 9, and 10. We shuffle the 10 envelopes and then match the envelope on top with the next envelope, the third envelope with the fourth envelope, and so on. One particular way a “dream draw” occurs is when the five envelopes labeled 1,2,3,4,5 are in the odd numbered positions (in any order!) and the others are in the even numbered positions. This way corresponds to the situation where the first match of each strong team is a home match. Since for each pair there are two possibilities for the home match, the total number of possibilities for the “dream draw” is $2^{5} = 32$ times as large.
(A) An outcome of this experiment is a sequence like 4,9,3,7,5,10,1,8,2,6 of labels of envelopes. What is the probability of an outcome?
Because there are a total of $10!$ possible outcomes, the probability of one of them occurring is $\frac{1}{10!}$.

(B) How many outcomes are there in the event “the five envelopes labeled 1, 2, 3, 4, 5 are in the odd positions in any order, and the envelopes labeled 6, 7, 8, 9, 10 are in the even positions—in any order”?
The following multiplication lets us see the number of outcomes for this situation:
$$
5 \times 5 \times 4 \times 4 \times 3 \times 3 \times 2 \times 2 \times 1 \times 1 \times = 5! \times 5!
$$
(C) What is the probability of a “dream draw”?
$$
P(\text{Dream Draw}) = 2^{5}\frac{5! \times 5!}{10!} 
$$

#### Exercise 2.14 Consider the Monty Hall “experiment” described in Section 1.3. The door behind which the car is parked we label a, the other two b and c. As the sample space we choose a product space $\Omega = \{ a, b, c \} \times \{ a, b, c \}$.  Here the first entry gives the choice of the candidate, and the second entry the choice of the quizmaster.
(A) Make a 3×3 table in which you write the probabilities of the outcomes. N.B. You should realize that the candidate does not know that the car is in a, but the quizmaster will never open the door labeled a because he knows that the car is there. You may assume that the quizmaster makes an arbitrary choice between the doors labeled b and c, when the candidate chooses door a.

|     | a   | b   | c   |
| --- | --- | --- | --- |
| a   | 0   | 1/6 | 1/6 |
| b   | 0   | 0   | 1/3 |
| c   | 0   | 1/3 | 0   |
|     |     |     |     |
#### Exercise 2.15 The rule $P(A ∪ B) = P(A) + P(B) − P(A ∩ B)$ from Section 2.3 is often useful to compute the probability of the union of two events. What would be the corresponding rule for three events $A$, $B$, and $C$? It should start with $P(A ∪ B ∪ C) = P(A) + P(B) + P(C) − · · ·$. Hint: you could use the sum rule suitably, or you could make a diagram as in

Let's say that $D = A \cup B$, then:
$$
P(D \cup C) = P(D) + P(C) - P(D \cap C)
$$