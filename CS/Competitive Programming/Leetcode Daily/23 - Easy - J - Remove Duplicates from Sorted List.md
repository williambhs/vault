
**Problem Number: 83
Relevant Tags: [[02 - DS - X - Linked List]]
<h1> Problem Description </h1>
Given the `head` of a sorted linked list, _delete all duplicates such that each element appears only once_. Return _the linked list **sorted** as well_.

**Example 1:**

![](https://assets.leetcode.com/uploads/2021/01/04/list1.jpg)

**Input:** head = [1,1,2]
**Output:** [1,2]

**Example 2:**

![](https://assets.leetcode.com/uploads/2021/01/04/list2.jpg)

**Input:** head = [1,1,2,3,3]
**Output:** [1,2,3]

**Constraints:**

- The number of nodes in the list is in the range `[0, 300]`.
- `-100 <= Node.val <= 100`
- The list is guaranteed to be **sorted** in ascending order.

-----
Create dummy node so you can return the head of the list easily as you will be updating the head pointer as you traverse the list
Then if head is equal to the next value, set head.next to the one after that to skip that value. 

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
    public ListNode deleteDuplicates(ListNode head) {

        if (head == null) return head;

        ListNode curr = new ListNode(0);
        curr.next = head;

        while (head.next != null) {
            if (head.val == head.next.val) {
                head.next = head.next.next;
            }
            else {
                head = head.next;
            }
        }
        return curr.next;
    }
}
```