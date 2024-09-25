
**Relevant Tags:** [[04 - A - I - Depth First Search]]

----

Not to be confused with BST (Binary Search Tree) - a tree is used to organize/store data, consisting of nodes - the top one is called the root, and leaf nodes are nodes which do not have child nodes. 

Nodes that are predecessor of other nodes are called parent nodes, and the nodes that are their successors are called child nodes.

Trees are useful when you want to store information that naturally forms a hierarchy, and provide insertion/deletion.

There are three types of trees:

1 - Binary Tree: Each node can have a max of two children (left, right)

2 - Ternary Tree: Each node has at most three child nodes (left, mid, right)

3 - N-ary tree/Generic Tree: Each node is a DSA consisting of records/list of references to children

Basic Operations of Tree DSA:

Create (creates a tree)
Insert (inserts data in tree)
Search (searches for a value in the tree)
Traversal (DFS, BFS)

Good rule of thumb for DFS vs BFS - if the question asks about levels of a binary tree, use BFS (find the sum of nodes at each level, the rightmost node at each level, etc.)
Otherwise, use recursion + DFS.