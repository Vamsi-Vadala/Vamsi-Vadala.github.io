---
title: "Contains Duplicate - DSA"
date: 2025-03-21
categories: [LeetCode,DSA]
tags: [Array, Hashset]
---

## Problem
You can find the problem here [Leetcode - Contains Duplicate](https://leetcode.com/problems/contains-duplicate/description/).
So basically we need to return `True` if there exist an element with frequency of at least 2 or `False` if all the elements occur only once.

---

## My Approach
So my thought process for this problem goes like this --- First there shouldn't be any duplicates in the given array. So if we convert into a `Hashset`[^1] which is nothing but a unique collection of all elements, then the length of both elements must match, if the given array contains all unique elements i.e., no duplicates.

### Solution Implementation

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        if len(set(nums)) == len(nums):
            return False
        else:
            return True

```
### Drawbacks/Problems
This method works but there are some drawback in terms of efficiency --- My method traverses the whole list unnecessarily even when an early exit condition is triggered. For example if the array values are \[1,1,1,2,3\] an efficient code can exit on checking second element.

---

## Optimal Solution
We can use the python's set (Hashset) to store each element one by one until a duplicate is found. The access time for an element in set is `O(1)`. Similarly adding an element into set is also `O(1)` time.

### Solution Implementation
```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        seen = set()
        for num in nums:
            if num in seen:
                return True
            seen.add(num)
        return False

```
The condition `num in seen` has an access time of `O(1)` as well as for `seen.add(num)`. This doesn't iterate the whole `nums`
array until unless the given array is unique. 

---
[^1]: A data structure that stores only unique keys, using hashing for fast lookup.