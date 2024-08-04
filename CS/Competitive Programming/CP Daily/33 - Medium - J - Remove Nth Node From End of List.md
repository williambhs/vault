
**Problem Number: 19
Relevant Tags: [[02 - DS - X - Linked List]]
<h1> Problem Description </h1>
Given the `head` of a linked list, remove the `nth` node from the end of the list and return its head.

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/10/03/remove_ex1.jpg)

**Input:** head = [1,2,3,4,5], n = 2
**Output:** [1,2,3,5]

**Example 2:**

**Input:** head = [1], n = 1
**Output:** []

**Example 3:**

**Input:** head = [1,2], n = 1
**Output:** [1]

**Constraints:**

- The number of nodes in the list is `sz`.
- `1 <= sz <= 30`
- `0 <= Node.val <= 100`
- `1 <= n <= sz`

-----
Too depressed to write out my thought process. Solved in two pass come back later and implement one pass.

Ok one pass finished.
Man I feel like shit.
<h1> Solution </h1>
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {

       
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode fast = dummy;
        ListNode slow = dummy;

        for (int i = 0; i < n + 1; i++) {
            fast = fast.next;
        }

        while (fast != null) {
            slow = slow.next;
            fast = fast.next;
        }
        slow.next = slow.next.next;
        return dummy.next;
    }
}
```