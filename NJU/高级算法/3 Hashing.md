---
tags:
---
Date: 2026-09-07 : 16:51
***
## Random Maps, Collisions And The Birthday Scale
### Random Maps As A Model Of Hashing
#Q 
- Mathematical definition of a hash function as a map :: $h: U \to [m]$ where m are the keys
- What gives independent uniform values to different keys :: A Uniformly random map.
- A uniformly random map is what we use as an ideal model called :: Simple Hashing Universal Assumption (SHUA)
- Number of bits needed for storing each key from [m] :: $\lceil \log_{2}(m) \rceil$

### Birthday Calculation
#Q 
- Probability all balls (n) (persons) fall into different bins (m) (birthdays) :: $Pr(Dif Birthday) = \frac{m}{m} \frac{m - 1}{m} \cdots \frac{m - n + 1}{m} = \frac{m(m-1)\cdots(m-n+1)}{m^n} = \prod_{i = 0}^{n-1 }(1 - \frac{i}{m})$
- We know that $e^{-x} = 1 - x + O(x^2)$, so we can say that :: $Pr(Dif Birthday) \approx \prod_{i = 0}^{n-1 }\left( e^{-\frac{i}{m}} \right)$
- To obtain $\prod_{i = 0}^{n-1 }\left( e^{-\frac{i}{m}} \right)$ we just have to do the sum over the exponents, that could be translated into :: $\sum_{i = 1}^{n} \left( \frac{i}{m} \right) = \frac{1}{m}\sum_{i = 1}^{n}(i) = \frac{1}{m} \frac{n (n-1)}{2}$
- Thus, our final probability would be approximately :: $Pr(Dif Birthday) \approx e^{-\frac{n(n-1)}{2m}}$

### Collision Count
#Q 
- We have the random variable collision pairs as follows $X_{ij} = \{1 \text{ if } h(x_{i}) = h(x_{j}); 0 \text{ if otherwise}\}$ in that case because our hash functions are 2-universal, then the probability of them colliding is :: $Pr[h(x_{i}) = h(x_{j})] \leq \frac{1}{m}$
- What is the expected value given that we have N different balls :: $\mathbb{E}(C) =  {N \choose 2} \frac{1}{m}$ esto es por que hay  ${N \choose 2}$ diferentes pares (no ordenados) en total y cada uno tiene una probabilidad de colisión de $\frac{1}{m}$.
- What if $N = m$ (same number of balls and bins), then :: $\mathbb{E}(C) =  {N \choose 2} \frac{1}{m} = \frac{N!}{2! (N-2)!} \frac{1}{m}= \frac{N(N-1)}{2m} < \frac{N}{2}$

## Hash Families With Short Descriptions
#Q 
- A **hash family** has 2 elements :: 1) The set of hash functions 2) A rule for when to use which hash function.

### Two Distinct Randomness Requirements
#Q 
- A distribution of functions is **universal** if for all $x \neq y$ their probability of collision is :: $Pr[h(x) = h(y)] \leq \frac{1}{m}$ (m is the number of keys)
- A distribution of functions is **strong universal** if for all $x \neq y$ and any $a, b \in [m]$ their probability of obtaining the keys $a, b$ is :: $Pr[h(x) = a \text{ and } h(y) = b] \leq \frac{1}{m^2}$
- Strong universal hash functions can also be called :: pairwise independent and uniform.
- We can say that **strong universal** hash functions have higher requirements than **universal** hash functions because we can say that :: $a = b$

### k-Universal And Strongly k-Universal Hash Functions
#Q 
- A family of functions is **k-universal** if :: $Pr[h(x_{i}) = \cdots =h(x_{n})] \leq \frac{1}{m^{n - 1}}$
- A family of functions is **strongly k-universal** if :: $Pr[\bigwedge_{i = 1}^k \left(h(x_{i}) = a_{i}\right)] \leq \frac{1}{m^{k}}$

### Affine Hashing Over A Field
#Q 




## Flashcards
```aosr-deck-config
{
	"rule": {
		"conditions": {
			"all": [{
				"fact": "card",
				"operator": "regexMatch",
				"value": "NJU/高级算法/3 Hashing.md",
				"path": "$.path"
			}]
		},
		"event": {
			"type": "match"
		}
	}
}
```
