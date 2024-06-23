
**Problem Number: 328
Relevant Tags: [[02 - DS - X - Linked List]]
<h1> Problem Description </h1>
Given the `head` of a singly linked list, group all the nodes with odd indices together followed by the nodes with even indices, and return _the reordered list_.

The **first** node is considered **odd**, and the **second** node is **even**, and so on.

Note that the relative order inside both the even and odd groups should remain as it was in the input.

You must solve the problem in `O(1)` extra space complexity and `O(n)` time complexity.

**Example 1:**

![](https://assets.leetcode.com/uploads/2021/03/10/oddeven-linked-list.jpg)

**Input:** head = [1,2,3,4,5]
**Output:** [1,3,5,2,4]

**Example 2:**

![](https://assets.leetcode.com/uploads/2021/03/10/oddeven2-linked-list.jpg)

**Input:** head = [2,1,3,5,6,4,7]
**Output:** [2,3,6,7,1,5,4]

**Constraints:**

- The number of nodes in the linked list is in the range `[0, 104]`.
- `-106 <= Node.val <= 106`

-----
Seems relatively simple - first save the head.next of the first node, then set .next of the first node to .next.next to skip all the odd nodes. When the head becomes null, you've reached the end of the list, and you want to set the new head to the saved pointer that was the second node - then set that one to .next.next until you reach the end of the list.

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
    public ListNode oddEvenList(ListNode head) {

        if (head == null || head.next == null) return head;

        ListNode ans = new ListNode(0);
        ans.next = head;

        ListNode evenHead = new ListNode(0);
        ListNode even = head.next;
        evenHead.next = even;

        while (head.next != null && head.next.next != null) {
            head.next = head.next.next;
            even.next = even.next.next;
            even = even.next;
            head = head.next;
            
        }

        head.next = evenHead.next;
        return ans.next;
    }
}
```