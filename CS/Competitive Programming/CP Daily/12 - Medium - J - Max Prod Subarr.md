
**Problem Number: 152
Relevant Tags: [[04 - A - O - Sliding Window]], [[04 - A - O - Kadane's Algorithm]], [[11 - Medium - J - Max SubArr]]
<h1> Problem Description </h1>
Given an integer array `nums`, find a 

subarray

 that has the largest product, and return _the product_.

The test cases are generated so that the answer will fit in a **32-bit** integer.

**Example 1:**

**Input:** nums = [2,3,-2,4]
**Output:** 6
**Explanation:** [2,3] has the largest product 6.

**Example 2:**

**Input:** nums = [-2,0,-1]
**Output:** 0
**Explanation:** The result cannot be 2, because [-2,-1] is not a subarray.

**Constraints:**

- `1 <= nums.length <= 2 * 104`
- `-10 <= nums[i] <= 10`
- The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.

-----
Sliding window approach using multiplication and division operators - the problem is if there are two negatives spaced far apart
Maybe possible to brute force - create temp variable, then shrink the array after? Ie. make a window that encompasses the entire array, and then shrink it to size 0... seems very inefficient

After coming back to this having solved [[11 - Medium - J - Max SubArr]], it seems very similar. Instead, however, the product can always be more if curr is negative and [i] is negative, then curr * i will always be greater.

Apparently the solution involves keeping track of both a maximum and minimum product - you multiply the value by both the maximum and index and set the current max to the greatest of both.
Keep track of the max - if the value is less than 0 then the minimum becomes the max.

<h1> Solution </h1>
class Solution {

    public int maxProduct(int[] nums) {

        int max = nums[0];

        int min = max;

        int ans = min;

  

        for (int i = 1; i < nums.length; i++)

        {

            int num = nums[i];

            if (num < 0)

            {

                int temp = min;

                min = max;

                max = temp;

            }

  

            max = Math.max(num, num * max);

            min = Math.min(num, num * min);

            ans = Math.max(ans, max);

        }

        return ans;

  
  

    }

}