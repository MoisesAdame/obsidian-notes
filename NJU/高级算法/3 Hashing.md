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
- To obtain $\prod_{i = 0}^{n-1 }\left( e^{-\frac{i}{m}} \right)$ we just have to do the sum over the exponents, that could be translated into 

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
