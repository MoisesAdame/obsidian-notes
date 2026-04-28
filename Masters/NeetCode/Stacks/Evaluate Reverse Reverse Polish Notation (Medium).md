---
tags:
---
Date: 2026-04-28 : 14:44
***
## Problem
Link: https://neetcode.io/problems/evaluate-reverse-polish-notation/question?list=neetcode150

You are given an array of strings `tokens` that represents a **valid** arithmetic expression in [Reverse Polish Notation](https://en.wikipedia.org/wiki/Reverse_Polish_notation).

Return the integer that represents the evaluation of the expression.

- The operands may be integers or the results of other operations.
- The operators include `'+'`, `'-'`, `'*'`, and `'/'`.
- Assume that division between integers always truncates toward zero.

## Solution Thought Process
Step 1: Iterate over the tokens and add them to the stack
Step 2: When an operator token is found in the top of the stack pop it as well as the left and right values.
Step 3: Execute the operation and push the result to the stack

## Code O(n)
```python
class Solution:
    def evalRPN(self, tokens: List[str]) -> int:
        stack = []
        operations = {
            '+': lambda x,y: x + y,
            '-': lambda x,y: x - y,
            '*': lambda x,y: x * y,
            '/': lambda x,y: x / y,
        }

        for token in tokens:
            stack.append(token)

            if stack and stack[-1] in operations:
                operation = stack.pop()
                right_val = float(stack.pop())
                left_val = float(stack.pop())

                res = operations[operation](left_val, right_val)
                stack.append(str(int(res)))

        return int(stack[-1])
```