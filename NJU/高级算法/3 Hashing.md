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
- What is the expected value given that we have N different balls :: $\mathbb{E}(C) =  {N \choose 2} \frac{1}{m}$ esto es por que hay  ${N \choose 2}$ diferentes pares (no ordenados) en total 

## Hash Families With Short Descriptions
#Q 
- A **hash family** has 2 elements :: 1) The set of hash functions 2) A rule for when to use which hash function.

### 

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
