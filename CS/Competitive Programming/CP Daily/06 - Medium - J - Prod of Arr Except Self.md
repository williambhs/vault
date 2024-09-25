**Problem Number: 238
Relevant Tags:
<h1> Problem Description </h1>

Given an integer array `nums`, return _an array_ `answer` _such that_ `answer[i]` _is equal to the product of all the elements of_ `nums` _except_ `nums[i]`.

The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.

You must write an algorithm that runs in `O(n)` time and without using the division operation.

**Example 1:**

**Input:** nums = [1,2,3,4]
**Output:** [24,12,8,6]

**Example 2:**

**Input:** nums = [-1,1,0,-3,3]
**Output:** [0,0,9,0,0]

**Constraints:**

- `2 <= nums.length <= 105`
- `-30 <= nums[i] <= 30`
- The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.

**Follow up:** Can you solve the problem in `O(1)` extra space complexity? (The output array **does not** count as extra space for space complexity analysis.)

-----
First - set each element in an array to 1. Then, you multiply all the elems on the right and all the elems on the left.
The idea is that you multiply output[i] by right or left - the value for right or left gets stored and accumulated.
<h1> Solution </h1>
class Solution {

    public int[] productExceptSelf(int[] nums) {

        int[] output = new int[nums.length];

        Arrays.fill(output, 1);

  

        int right = 1;

        int left = 1;

  

        for (int i = nums.length - 1; i >= 0; i--)

        {

            output[i] *= right;

            right *= nums[i];

        }

  

        for (int i = 0; i < nums.length; i++)

        {

            output[i] *= left;

            left *= nums[i];

        }

  

        return output;

    }

}