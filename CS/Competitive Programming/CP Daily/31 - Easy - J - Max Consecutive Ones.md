
**Problem Number: 485
Relevant Tags:
<h1> Problem Description </h1>
Given a binary array `nums`, return _the maximum number of consecutive_ `1`_'s in the array_.

**Example 1:**

**Input:** nums = [1,1,0,1,1,1]
**Output:** 3
**Explanation:** The first two digits or the last three digits are consecutive 1s. The maximum number of consecutive 1s is 3.

**Example 2:**

**Input:** nums = [1,0,1,1,0,1]
**Output:** 2

**Constraints:**

- `1 <= nums.length <= 105`
- `nums[i]` is either `0` or `1`.

-----
Warmup problem - use math.max and iterate through the array, reset when you see a 0
(This took me 94 seconds to solve)
<h1> Solution </h1>
class Solution {

    public int findMaxConsecutiveOnes(int[] nums) {

        int ans = 0;

        int curr = 0;

        for (int i = 0; i < nums.length; i++) {

            if (nums[i] == 1) {

                curr++;

                ans = Math.max(ans, curr);

            }

            else {

                curr = 0;

            }

        }

        return ans;

    }

}