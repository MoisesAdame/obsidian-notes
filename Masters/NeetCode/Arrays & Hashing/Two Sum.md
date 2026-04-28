---
tags:
---
Date: 2026-04-27 : 21:58
***
## Problem
Link: https://neetcode.io/problems/two-integer-sum-ii/question?list=neetcode150
Given an array of integers `nums` and an integer `target`, return the indices `i` and `j` such that `nums[i] + nums[j] == target` and `i != j`.

You may assume that _every_ input has exactly one pair of indices `i` and `j` that satisfy the condition.

Return the answer with the smaller index first.

## Solution Thought Process
Define two indices `i = 0` and `j = i + 1`. Then go trough `nums` until `nums[i] + nums[j] == target`.

## Solution O(n^2)
```python
def two_sum(nums, target):
	for i in range(len(nums)):
		for j in range(i + 1, len(nums)):
			if nums[i] + nums[j] == target:
				return [i, j]
	
	return []
```
