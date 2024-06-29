
**Problem Number: 144
Relevant Tags: [[34 - Easy - O - Binary Tree Inorder Traversal]]
<h1> Problem Description </h1>
Given the `root` of a binary tree, return _the preorder traversal of its nodes' values_.

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/09/15/inorder_1.jpg)

**Input:** root = [1,null,2,3]
**Output:** [1,2,3]

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
More Binary Tree practice. Going to try and implement both iterative and recursive solutions for good practice.

<h1> Solution </h1>
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
    public List<Integer> preorderTraversal(TreeNode root) {
        ArrayList<Integer> list = new ArrayList<>();
        if (root == null) return list;
        Stack<TreeNode> st = new Stack<>();
        TreeNode curr = root;
        st.push(root);

        while (!st.isEmpty()) {
        
            curr = st.pop();
            list.add(curr.val);
            if (curr.right != null) st.push(curr.right);
            if (curr.left != null) st.push(curr.left);
            
        }
        return list;

        
    }
}
```
