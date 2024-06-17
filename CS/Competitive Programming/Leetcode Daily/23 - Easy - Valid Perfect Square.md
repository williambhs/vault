
**Problem Number: 367
Relevant Tags: [[04 - A - O - Binary Search]]
<h1> Problem Description </h1>
Given a positive integer num, return `true` _if_ `num` _is a perfect square or_ `false` _otherwise_.

A **perfect square** is an integer that is the square of an integer. In other words, it is the product of some integer with itself.

You must not use any built-in library function, such as `sqrt`.

**Example 1:**

**Input:** num = 16
**Output:** true
**Explanation:** We return true because 4 * 4 = 16 and 4 is an integer.

**Example 2:**

**Input:** num = 14
**Output:** false
**Explanation:** We return false because 3.742 * 3.742 = 14 and 3.742 is not an integer.

**Constraints:**

- `1 <= num <= 231 - 1`

-----
Initial thought process was to just square values and use binary search, but the number ends up being too big.
But - apparently using longs instead of ints fixes this issue.
<h1> Solution </h1>
class Solution {

    public boolean isPerfectSquare(int num) {

        long l = 0;

        long r = num;

  

        while (l <= r) {

            long mid = l + (r - l) / 2;

  

            if (mid * mid == num) return true;

  

            if (mid * mid < num) l = mid + 1;

  

            if (mid * mid > num) r = mid - 1;

        }

        return false;

    }

}