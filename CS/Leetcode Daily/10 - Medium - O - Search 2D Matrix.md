
**Problem Number: 74
Relevant Tags: [[04 - A - O - Binary Search]], [[01 - C - X - Time Complexity]]
<h1> Problem Description </h1>
You are given an `m x n` integer matrix `matrix` with the following two properties:

- Each row is sorted in non-decreasing order.
- The first integer of each row is greater than the last integer of the previous row.

Given an integer `target`, return `true` _if_ `target` _is in_ `matrix` _or_ `false` _otherwise_.

You must write a solution in `O(log(m * n))` time complexity.

**Example 1:**

![](https://assets.leetcode.com/uploads/2020/10/05/mat.jpg)

**Input:** matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3
**Output:** true

**Example 2:**

![](https://assets.leetcode.com/uploads/2020/10/05/mat2.jpg)

**Input:** matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13
**Output:** false

**Constraints:**

- `m == matrix.length`
- `n == matrix[i].length`
- `1 <= m, n <= 100`
- `-104 <= matrix[i][j], target <= 104`

-----
Binary search each row, then binary search each column
Going through every element results in m * n time complexity which is why binary search is required
Each row has length n - for each row in the matrix perform binary search then for each column perform binary search if not found return false

To binary search each column, you would first search matrix00, then matrix 0mid, etc, if not found you increment 0 by i until less than n if n = matrix0.length

Ok, nevermind, you can literally just perform a normal binary search without needing all the extra code for searching columns. 
<h1> Solution </h1>
class Solution {

public boolean searchMatrix(int[][] matrix, int target) {

int m = matrix.length;

int n = matrix[0].length;

  

// binary searching rows

for (int[] row: matrix)

{

int left = 0;

// n = cols = length of a row

int right = n - 1;

  

while (left <= right)

{

// checking for the middle index of the row

int mid = left + (right-left) / 2;

  

if (row[mid] == target) return true;

if (row[mid] < target) left = mid + 1;

if (row[mid] > target) right = mid - 1;

}

}

  

return false;

}

}
