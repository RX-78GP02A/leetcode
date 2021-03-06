---
Difficulty: Easy
Related Topics:
  "Array": https://leetcode.com/tag/array
  "Hash Table": https://leetcode.com/tag/hash-table
---

## [1. Two Sum](https://leetcode.com/problems/two-sum/description/)

### Problem:

Given an array of integers, return **indices** of the two numbers such that they add up to a specific target.

You may assume that each input would have **exactly** one solution, and you may not use the *same* element twice.

**Example:**

```
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

### Solution:

Map the numbers to their indices as we iterate, so that we can look them back up in O(1) time complexity.

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
  const indicies = {}
  
  for (let i = 0; i < nums.length; i++) {
    const num = nums[i]
    if (indicies[target - num] != null) {
      return [indicies[target - num], i]
    }
    indicies[num] = i
  }
};
```
