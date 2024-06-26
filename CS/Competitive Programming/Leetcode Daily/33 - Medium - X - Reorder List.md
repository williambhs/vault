
**Problem Number: 143
Relevant Tags: [[02 - DS - X - Linked List]]
<h1> Problem Description </h1>
You are given the head of a singly linked-list. The list can be represented as:

L0 → L1 → … → Ln - 1 → Ln

_Reorder the list to be on the following form:_

L0 → Ln → L1 → Ln - 1 → L2 → Ln - 2 → …

You may not modify the values in the list's nodes. Only nodes themselves may be changed.

**Example 1:**

![](https://assets.leetcode.com/uploads/2021/03/04/reorder1linked-list.jpg)

**Input:** head = [1,2,3,4]
**Output:** [1,4,2,3]

**Example 2:**

![](https://assets.leetcode.com/uploads/2021/03/09/reorder2-linked-list.jpg)

**Input:** head = [1,2,3,4,5]
**Output:** [1,5,2,4,3]

**Constraints:**

- The number of nodes in the list is in the range `[1, 5 * 104]`.
- `1 <= Node.val <= 1000`

-----
Three steps:
First, use a fast and slow pointer (turtle and hare approach) to find the middle of the list.
Next, reverse the second half of the list. 
Finally, merge the two list using two pointers and alternating.

<h1> Solution </h1>
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 * int val;
 * ListNode next;
 * ListNode() {}
 * ListNode(int val) { this.val = val; }
 * ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public void reorderList(ListNode head) {
        if (head == null || head.next == null) return;

        ListNode fast = head;
        
        ListNode slow = head;
        
        ListNode temp = head;
        ListNode prev = null;

        while (fast != null && fast.next != null)  {
            prev = slow;
            slow = slow.next;
            fast = fast.next.next;

        }
        // at the end of this slow is now in the middle which means it's the head of the
        // second list and prev is one before slow, so we set prev.next to null to break
        // the lists into two
        prev.next = null;

        ListNode l2 = reverse(slow);
        // now we should have two linked lists, one that's the second half reversed and
        // one that's the first half, so now we just merge them together - temp is the
        // head of the first list that we assigned earlier

        merge(temp, l2);

    }

    public ListNode reverse(ListNode head) {

        ListNode prev = null;
        while (head != null) {
            ListNode next = head.next;
            head.next = prev;
            prev = head;
            head = next;
        }

        return prev;
    }

    public void merge(ListNode l1, ListNode l2) {
        while (l1 != null) {
            ListNode l1n = l1.next;
            ListNode l2n = l2.next;

            l1.next = l2;
            if (l1n == null) break;
            l2.next = l1n;

            l1 = l1n;
            l2 = l2n;

        }
    }
}
``` 