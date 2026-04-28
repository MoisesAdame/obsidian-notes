---
tags:
---
Date: 2026-04-27 : 22:38
***
## Problem
Link: https://neetcode.io/problems/validate-parentheses/question
You are given a string `s` consisting of the following characters: `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`.

The input string `s` is valid if and only if:

1. Every open bracket is closed by the same type of close bracket.
2. Open brackets are closed in the correct order.
3. Every close bracket has a corresponding open bracket of the same type.

Return `true` if `s` is a valid string, and `false` otherwise.

## Solution Thought Process
If top of the stack has with `)`, `]` or `}`: False
If not, and the letter we encounter is the opposite of the top of the stack: pop()
Else: append()

## Code
```python
def isValid(self, s: str) -> bool:
      opposite = {
	      ')': '(',
	      '}': '{',
	      ']': '['
	}
	stack = []
    for letter in s:
	    # Si tiene algo y ese algo es ')', ']' '}', Falso
	    if stack and stack[-1] in opposite:
			return False     
		
		if stack and letter in opposite 
			and stack[-1] == opposite[letter]:
			stack.pop()
		
		else:
			stack.append(letter)
			    
	return len(stack) == 0
```


