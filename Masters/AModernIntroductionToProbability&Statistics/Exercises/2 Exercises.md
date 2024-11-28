---
tags:
---
Date: 2024-11-26 : 20:17
***
##### Exercise 2.1: Let $A$ and $B$ be two events in a sample space for which $P(A) = 2/3$, $P(B) = 1/6$, and $P(A \cap B) = 1/9$. What is $P(A \cup B)$?

We know that $P(A \cup B) = P(A) + P(B) - P(A \cap B)$, then:
$$
P(A \cup B) = \frac{2}{3} + \frac{1}{6} - \frac{1}{9} = \frac{12 + 3 - 2}{18} = \frac{13}{18}
$$
##### Exercise 2.4: We consider events $A$, $B$, and $C$, which can occur in some experiment. Is it true that the probability that only A occurs (and not B or C) is equal to $P(A \cup B \cup C) − P(B) − P(C) + P(B \cap C)$?

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

##### Exercise 2.7 Let $A$ and $B$ be two events. Suppose that $P(A) = 0.4$, $P(B) = 0.5$, and $P(A \cap B) = 0.1$. Find the probability that $A$ or $B$ occurs, but not both.

We want:
$$
(A^{C} \cap B) \cup (A \cap B^{C}) = (B - A \cup B) \cup (A - A \cup B)
$$

This means:
$$
P(B - A \cup B) + P(A - A \cup B) = (0.4 - 0.1) + (0.5 - 0.1) = 0.7
$$

This is the correct consideration, because if we did $P(A \cup B)$, then we would be considering A, B or both.

##### Exercise 2.8: Suppose the events $D_{1}$ and $D_{2}$ represent disasters, which are rare: $P(D_{1}) ≤ 10^{−6}$ and $P(D_{2}) ≤ 10^{−6}$. What can you say about the probability that at least one of the disasters occurs? What about the probability that they both occur?

For **at least one occurring** we have to consider:
$$
P(D_{1} \cup D_{2}) = P(D_{1}) + P(D_{2}) \leq 2 \cdot 10^{-6}
$$

For both of them to occur, we have to consider that $D_{1}  \subset D_{2}$ or that $D_{2} \subset D_{1}$. Considering that we can say that:
$$
P(D_{1} \cap D_{2}) = min\{ P(D_{1}), P(D_{2}) \} \leq 10^{-6} 
$$
##### Exercise 2.9 We toss a coin three times. For this experiment we choose the sample space $\Omega = \{ HHH,THH,HTH,HHT,TTH,THT,HTT,TTT \}$. (a) Write down the set of outcomes corresponding to each of the following events: A, B, C and D. (b) Write down the set of outcomes corresponding to each of the following events: $A^{C}$, $A∪(C ∩D)$, and $A∩D^{C}$.

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
##### Exercise 2.10 In some sample space we consider two events $A$ and $B$. Let $C$ be the event that $A$ or $B$ occurs, but not both. Express $C$ in terms of $A$ and $B$, using only the basic operations “union,” “intersection,” and “complement.”
It can be originally expressed as follows:
$$
C = (A \cup B) \cap (A \cap B)^{C}
$$
Using DeMorgan's Laws we can simplify this expression to:
$$
C = A \cup B \cap (A^{C} \cup B^{C}) = A^{C}\cap(A \cup B) \cup B^{C}\cap(A \cup B) = (A^{C} \cap B) \cup (B^{C} \cap A)
$$
##### Exercise 2.11 An experiment has only two outcomes. The first has probability $p$ to occur, the second probability $p^{2}$. What is $p$?
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

##### Exercise 2.12 In the UEFA Euro 2004 playoffs draw 10 national football teams were matched in pairs. A lot of people complained that “the draw was not fair,” because each strong team had been matched with a weak team (this is commercially the most interesting). It was claimed that such a matching is extremely unlikely. We will compute the probability of this “dream draw” in this exercise. In the spirit of the three-envelope example of Section 2.1 we put the names of the 5 strong teams in envelopes labeled 1,2,3,4, and 5 and of the 5 weak teams in envelopes labeled 6, 7, 8, 9, and 10. We shuffle the 10 envelopes and then match the envelope on top with the next envelope, the third envelope with the fourth envelope, and so on. One particular way a “dream draw” occurs is when the five envelopes labeled 1,2,3,4,5 are in the odd numbered positions (in any order!) and the others are in the even numbered positions. This way corresponds to the situation where the first match of each strong team is a home match. Since for each pair there are two possibilities for the home match, the total number of possibilities for the “dream draw” is $2^{5} = 32$ times as large.
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

##### Exercise 2.14 Consider the Monty Hall “experiment” described in Section 1.3. The door behind which the car is parked we label a, the other two b and c. As the sample space we choose a product space $\Omega = \{ a, b, c \} \times \{ a, b, c \}$.  Here the first entry gives the choice of the candidate, and the second entry the choice of the quizmaster.
(A) Make a 3×3 table in which you write the probabilities of the outcomes. N.B. You should realize that the candidate does not know that the car is in a, but the quizmaster will never open the door labeled a because he knows that the car is there. You may assume that the quizmaster makes an arbitrary choice between the doors labeled b and c, when the candidate chooses door a.

|     | a   | b   | c   |
| --- | --- | --- | --- |
| a   | 0   | 1/6 | 1/6 |
| b   | 0   | 0   | 1/3 |
| c   | 0   | 1/3 | 0   |
|     |     |     |     |
##### Exercise 2.15 The rule $P(A ∪ B) = P(A) + P(B) − P(A ∩ B)$ from Section 2.3 is often useful to compute the probability of the union of two events. What would be the corresponding rule for three events $A$, $B$, and $C$? It should start with $P(A ∪ B ∪ C) = P(A) + P(B) + P(C) − · · ·$. *Hint: you could use the sum rule suitably, or you could make a diagram as in*

Let's say that $D = A \cup B$, then:
$$
P(D \cup C) = P(D) + P(C) - P(D \cap C)
$$
Then we get:
$$
P(D \cup C) = P(A \cup B) + P(C) - P(D \cap C)
$$
$$
P(D \cup C) = P(A) + P(B) - P(A \cap B) + P(C) - P(D \cap C)
$$
$$
P(D \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P((A \cap C) \cup (B \cap C))
$$
$$
P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - P(B \cap C) + P(A \cap B \cap C)
$$

##### Exercise 2.16 Three events $E$, $F$, and $G$ cannot occur simultaneously. Further it is known that $P(E∩F) = P(F ∩G) = P(E∩G) = 1/3$. Can you determine $P(E)$?  *Hint: if you try to use the formula of Exercise 2.15 then it seems that you do not have enough information; make a diagram instead.*

If the events cannot occur simultaneously, the we can say:
$$
P(E \cap F \cap G) = 0
$$
Considering the previous equation we know that:
$$
P(E \cup F \cup G) = P(E) + P(F) + P(G) - P(E \cap F) - P(E \cap G) - P(F \cap G) + P(E \cap F \cap G)
$$
Also:
$$
P(F \cup G) = P(F) + P(G) - P(F \cap G)
$$
$$
P(E \cup F \cup G) = P(E) + P(F \cup G) - \frac{2}{3}
$$
Then, we know that:
$$
P(E) = P(E \cup F \cup G) - P(F \cup G) + \frac{2}{3}
$$
##### Exercise 2.17 A post office has two counters where customers can buy stamps, etc. If you are interested in the number of customers in the two queues that will form for the counters, what would you take as sample space?
Given the fact that the number of customers is a Natural number, and both of the counters can have this number of customers, our sample space would be:
$$
\Omega = \mathbb{N} \times \mathbb{N}
$$
##### Exercise 2.18 In a laboratory, two experiments are repeated every day of the week in different rooms until at least one is successful, the probability of success being $p$ for each experiment. Supposing that the experiments in different rooms and on different days are performed independently of each other, what is the probability that the laboratory scores its first successful experiment on day $n$?
Lets assume we do the experiments but they fail $n - 1$ times, when the day $n$ comes one of them is successful, but the other is not, then we would have:
$$
P(n) = p 
$$