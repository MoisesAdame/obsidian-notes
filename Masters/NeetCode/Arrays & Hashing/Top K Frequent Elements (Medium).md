---
tags:
---
Date: 2026-04-27 : 23:17
***
## Problem 
Link: https://neetcode.io/problems/top-k-elements-in-list/question?list=neetcode150

Given an integer array `nums` and an integer `k`, return the `k` most frequent elements within the array.

The test cases are generated such that the answer is always **unique**.

You may return the output in **any order**.

## Solution Thought Process
Step 1: Create a hash map to count how many times each value occurs.
Step 2: Create a linked list for our bucket sort of the same size of `nums`. That is because a number can occur from $[1, len(nums)]$.
Step 3: Iterate over the hash map and populate the linked list according to the number of occurrences.
Step 4: Traverse the linked list (from big to small) and every time you find a number let `k-1`