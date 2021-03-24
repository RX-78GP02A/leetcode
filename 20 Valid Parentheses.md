---
Difficulty: Easy
Related Topics:
  "String": https://leetcode.com/tag/string
  "Stack": https://leetcode.com/tag/stack
Similar Questions:
  "Generate Parentheses": https://leetcode.com/problems/generate-parentheses
  "Longest Valid Parentheses": https://leetcode.com/problems/longest-valid-parentheses
  "Remove Invalid Parentheses": https://leetcode.com/problems/remove-invalid-parentheses
---

## [20. Valid Parentheses](https://leetcode.com/problems/valid-parentheses/description/)

### Problem:

Given a string containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.

Note that an empty string is also considered valid.

**Example 1:**

```
Input: "()"
Output: true
```

**Example 2:**

```
Input: "()[]{}"
Output: true
```

**Example 3:**

```
Input: "(]"
Output: false
```

**Example 4:**

```
Input: "([)]"
Output: false
```

**Example 5:**

```
Input: "{[]}"
Output: true
```

### Solution:

Stack 101.

We want to compare a close bracket to the last open bracket.

We use a stack to store open brackets: first in, last out.

```javascript
/**
 * @param {string} s
 * @return {boolean}
 */

// Stack is an abstract data type that serves as a collection of elements

// with two main principal operations:
// Push, which adds an element to the collection, and
// Pop, which removes the most recently added element that was not yet removed.


// created a funcion called isValid passes in a string called (s)
var isValid = function(s) {
    // intialized an array called stack 
    var stack = []; 
    // creating an object called pairs that represents each character based on styled bracket
    const pairs = {
     '}':'{',
     ']':'[',
     ')':'(',
    }
    
  // the for...of statement creates a loop iterating over iterable objects
  for (const valid of s) {
    // created an a varible to track if brackets are open 
    const open = pairs[valid] 
    // conditiontal that if a bracket is open 
    if (open) {
      // if the stack removes the most recently added element is not equal to open return boolean
      // !== (is not) compared two variables and but it ignores the datatype of variable.
      if (stack.pop() !== open) {
        // return boolean false 
        return false
      }
    } else {
      // creates the new element of the collection 
      stack.push(valid)
    }
  }
  return stack.length <= 0
};
