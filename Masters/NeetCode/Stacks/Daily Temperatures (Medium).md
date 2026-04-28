---
tags:
---
Date: 2026-04-28 : 14:55
***
## Problem 
Link: https://neetcode.io/problems/daily-temperatures/question?list=neetcode150

You are given an array of integers `temperatures` where `temperatures[i]` represents the daily temperatures on the `ith` day.

Return an array `result` where `result[i]` is the number of days after the `ith` day before a warmer temperature appears on a future day. If there is no day in the future where a warmer temperature will appear for the `ith` day, set `result[i]` to `0` instead.

## Thought Process
Step 1: Initialize array `result` with zeros.
Step 2: Initialize the `stack`.
Step 3: Iterate over `temperatures` using the `enumerate()` to know index and value.
Step 4: Check the top of `stack` and if current t is smaller than top append it. If not, pop until current is smaller than top, append it and check the difference of indices, that difference is put on the popped temperature index in `result`

