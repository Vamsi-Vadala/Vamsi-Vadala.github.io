---
title: "Valid Anagram - DSA"
date: 2025-03-22
categories: [LeetCode, DSA]
tags: [String, Hashmap, Anagram]
---

## Problem

You can find the problem here --- [Leetcode - Valid Anagram](https://leetcode.com/problems/valid-anagram/description/)

We need to return `True` if string `t` is an **anagram** of string `s`, else return `False`.

An anagram is a word or phrase formed by rearranging the letters of another, using all original letters exactly once.

---

## My Initial Approach

The most intuitive way to solve this is to compare the **frequency** of each character in both strings. If the frequency map is the same for both strings, then one is an anagram of the other.

### Code Using Python's `Counter`:

```python
from collections import Counter

class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return Counter(s) == Counter(t)
```
But my approach uses prebuilt function (which is the main reason most people use this language) `Counter` which is a fancy way of using dictionaries to store frequencies of a hashable objects. Under the hood this uses a optimal approach(But you are not exactly doing all the thinking) to solve this problem.

---

### Optimal Approach 
From the problem we can see that it only uses small letters from english alphabets. Which is of the size 26, so if we build an array corresponding to letter order i.e., at index 0 we store the count of a, at index 1 we store the count of b and so on from the first word while reducing the corresponding count by 1 for every letter in second word you'll end up calculating the frequencies of letters for both words. And finally if all are zeros in the final array then its an anagram or else its not.

See the below code for the explanation

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        if len(s) != len(t):
            return False
        
        count = [0] * 26
        for i in range(len(s)):
            count[ord(s[i]) - ord('a')] += 1
            count[ord(t[i]) - ord('a')] -= 1
        
        return all(x == 0 for x in count)
```
The `ord` function calculates the **Unicode code point(Integer Equivalent)**. This method uses same time complexity as my Initial approach but in space complexity it uses only `O(1)` which is better than my initial approach which takes up memory space of `O(n)`