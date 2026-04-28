---
tags:
---
Date: 2026-04-28 : 16:24
***
## Problem 
Link: https://neetcode.io/problems/anagram-groups/question

Given an array of strings `strs`, group all _anagrams_ together into sublists. You may return the output in **any order**.

An **anagram** is a string that contains the exact same characters as another string, but the order of the characters can be different.

## Thought Process
Step 1: Define a `key_generator()` function whose purpose is generate the same key for two strings `a` and `b` that are anagrams. This can be done using an array of len() = 26, where every index is one letter of the alphabet. Then, the array is transformed into a string so that it can be hashable.

Step 2: Initiate a hash map whose keys are the keys we are going to generate using `key_generator()`.

Step 3: Iterate over `strs` generating the key. If the key not in the hash map, for that key instantiate an array whose first element is the current element of `strs`. If the key in the hash map, append the current element of `strs` to the previously defined array.

Step 4: Iterate over the hash map and append all the arrays contained in it to a new array called `res`.

## Code O(n * k)
```python
class Solution:
    def key_generator(self, string_1):
        # Initializing string_1 hash
        array = [0] * 26
        for letter in string_1:
            array[ord(letter) - 97] += 1

        # Array to string
        res = ""
        for val in array:
            res += str(val) + "#"

        return res

    def groupAnagrams(self, strs: List[str]):
        gropus = {}
        res = []
        for i in strs:
            gen_key = self.key_generator(i)
            if gen_key in gropus:
                gropus[gen_key].append(i)
            else:
                gropus[gen_key] = [i]
        
        for value in gropus.values():
            res.append(value)
        
        return res
```
