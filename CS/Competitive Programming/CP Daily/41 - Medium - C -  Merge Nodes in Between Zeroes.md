
**Problem Number: 2181
Relevant Tags: [[02 - DS - X - Linked List]]
<h1> Problem Description </h1>
You are given the `head` of a linked list, which contains a series of integers **separated** by `0`'s. The **beginning** and **end** of the linked list will have `Node.val == 0`.

For **every** two consecutive `0`'s, **merge** all the nodes lying in between them into a single node whose value is the **sum** of all the merged nodes. The modified list should not contain any `0`'s.

Return _the_ `head` _of the modified linked list_.

**Example 1:**

![](https://assets.leetcode.com/uploads/2022/02/02/ex1-1.png)

**Input:** head = [0,3,1,0,4,5,2,0]
**Output:** [4,11]
**Explanation:** 
The above figure represents the given linked list. The modified list contains
- The sum of the nodes marked in green: 3 + 1 = 4.
- The sum of the nodes marked in red: 4 + 5 + 2 = 11.

**Example 2:**

![](https://assets.leetcode.com/uploads/2022/02/02/ex2-1.png)

**Input:** head = [0,1,0,3,0,2,2,0]
**Output:** [1,3,4]
**Explanation:** 
The above figure represents the given linked list. The modified list contains
- The sum of the nodes marked in green: 1 = 1.
- The sum of the nodes marked in red: 3 = 3.
- The sum of the nodes marked in yellow: 2 + 2 = 4.

**Constraints:**

- The number of nodes in the list is in the range `[3, 2 * 105]`.
- `0 <= Node.val <= 1000`
- There are **no** two consecutive nodes with `Node.val == 0`.
- The **beginning** and **end** of the linked list have `Node.val == 0`.

-----
Originally was going to use a counter for zeroes but doesn't seem to be needed - instead keep a counter for the sum of all nodes and start from head->next, then when you see a zero make a temporary node that points to the node after the zero, point head->next to a new node that's the sum of all the nodes so far, then set -> next of the new node to the temporary node after the zero. Your new node is the head, and after each iteration head becomes head->next.

<h1> Solution </h1>
```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* mergeNodes(ListNode* head) {
        int currSum{0};
        head = head->next;
        ListNode* temp = head;
        ListNode* dummy = new ListNode();
        dummy->next = temp;

        while (head != nullptr) {
            currSum += head->val;
            if (head->val == 0) {

                // new node
                ListNode* sum = new ListNode();
                sum->val = currSum;

                // node after new node skips the 0
                sum->next = head->next;

                // set head to the new node
                head = sum->next;

                // temp points to the new node
                temp->next = sum;
                temp = temp->next;
                currSum = 0;
            }
            else {
                head = head->next;
            }
        }
        return dummy->next->next;
    }
};
```
