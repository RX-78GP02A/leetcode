---
Difficulty: Easy
Related Topics:
  "Linked List": https://leetcode.com/tag/linked-list
Similar Questions:
  "Merge k Sorted Lists": https://leetcode.com/problems/merge-k-sorted-lists
  "Merge Sorted Array": https://leetcode.com/problems/merge-sorted-array
  "Sort List": https://leetcode.com/problems/sort-list
  "Shortest Word Distance II": https://leetcode.com/problems/shortest-word-distance-ii
---

## [21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/description/)

### Problem:

Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.

Example:

```
Input: 1->2->4, 1->3->4
Output: 1->1->2->3->4->4
```

### Solution:

Keep tracking the head of two lists and keep moving the pointer of smaller one to the next node.

```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode} 
 */

// created a function that passes in two linked list 
var mergeTwoLists = function(l1, l2) {
    // created a new linked list called l3
    var l3 = new ListNode();
    // intialized the head of l3 
    var head = l3;
    // A && B returns the value A if A can be coerced into false; otherwise, it returns B.
    while(l1 !== null && l2 !== null){
        // conditional of l1.val less than or equal to l2.val
        if(l1.val <= l2.val){
            // set l3.next to l1
            l3.next = l1;
            l1 = l1.next;
        }
        else{
            // set l3.next to l2
            l3.next = l2;
            l2 = l2.next;
        }
        l3 = l3.next
    }
     // if not l1.next set to l2 
     if (!l1) l3.next = l2;
     // if not l1.next set to l1
     if (!l2) l3.next = l1;
    
    return head.next
};

// next is undefined ? <result if true> : <result if false>
// .val is <condition> ? <result if true> : <result if false>

```


