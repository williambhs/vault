
**Problem Number: 94
Relevant Tags: [[01 - C - X - Recursion]], [[02 - DS - O - Tree]]
<h1> Problem Description </h1>
Given the `root` of a binary tree, return _the inorder traversal of its nodes' values_.

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/09/15/inorder_1.jpg)

**Input:** root = [1,null,2,3]
**Output:** [1,3,2]

**Example 2:**

**Input:** root = []
**Output:** []

**Example 3:**

**Input:** root = [1]
**Output:** [1]

**Constraints:**

- The number of nodes in the tree is in the range `[0, 100]`.
- `-100 <= Node.val <= 100`

**Follow up:** Recursive solution is trivial, could you do it iteratively?

-----
Two solutions - one iterative, one recursive. Come back to implement the iterative version with stack later.

<h1> Solution </h1>
Recursive Solution: 

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        
        ArrayList<Integer> list = new ArrayList<>();
        dfs(root, list);
        return list;
    }

    public void dfs(TreeNode root, ArrayList<Integer> list) {

        if (root != null) {
            dfs(root.left, list);
            list.add(root.val);
            dfs(root.right, list);
        }
 
    }
}
```
