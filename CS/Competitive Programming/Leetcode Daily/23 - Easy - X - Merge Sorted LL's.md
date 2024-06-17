
**Problem Number: 21
Relevant Tags: [[02 - DS - X - Linked List]]
<h1> Problem Description </h1>
You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists into one **sorted** list. The list should be made by splicing together the nodes of the first two lists.

Return _the head of the merged linked list_.

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/10/03/merge_ex1.jpg)

**Input:** list1 = [1,2,4], list2 = [1,3,4]
**Output:** [1,1,2,3,4,4]

**Example 2:**

**Input:** list1 = [], list2 = []
**Output:** []

**Example 3:**

**Input:** list1 = [], list2 = [0]
**Output:** [0]

**Constraints:**

- The number of nodes in both lists is in the range `[0, 50]`.
- `-100 <= Node.val <= 100`
- Both `list1` and `list2` are sorted in **non-decreasing** order.

-----

Use a loop -  start from the head of list1, while list2 != null:

if list2 <= list1.next, store list1.next and have list1 point to list2, then have list2.next point to next

otherwise, list2 is greater than list1 which means the order of the pointer doesn't change and you continue by having list1, or the current head point to list1.next

<h1> Solution </h1>
