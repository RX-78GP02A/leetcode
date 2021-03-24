---
Difficulty: Easy
Related Topics:
  "String": https://leetcode.com/tag/string
---

## [14. Longest Common Prefix](https://leetcode.com/problems/longest-common-prefix/description/)

### Problem:

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string `""`.

**Example 1:**

```
Input: ["flower","flow","flight"]
Output: "fl"
```

**Example 2:**

```
Input: ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```

**Note:**

All given inputs are in lowercase letters `a-z`.

### Solution:

```javascript

/**
 * @param {string[]} strs
 * @return {string}
 */
// created a function called longestCommonPrefix
var longestCommonPrefix = function (strs) {
  // created a initialized var called prefix
  let prefix = ''
  // if words is greater than 0
  if (strs.length > 0) {
    // iterate 
    for (let i = 0; ; i++) {
      const common = strs[0][i]
      if (!common) { return prefix }
      for (let j = 0; j < strs.length; j++) {
        if (strs[j][i] !== common) {
          return prefix
        }
      }
      prefix += common
    }
  }
  return prefix
};

```


