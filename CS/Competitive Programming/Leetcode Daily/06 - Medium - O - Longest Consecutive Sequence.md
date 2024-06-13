**Problem Number: 128
Relevant Tags: [[02 - DS - O - Array]]
<h1> Problem Description </h1>
Given an unsorted array of integers `nums`, return _the length of the longest consecutive elements sequence._

You must write an algorithm that runs in `O(n)` time.

**Example 1:**

**Input:** nums = [100,4,200,1,3,2]
**Output:** 4
**Explanation:** The longest consecutive elements sequence is `[1, 2, 3, 4]`. Therefore its length is 4.

**Example 2:**

**Input:** nums = [0,3,7,2,5,8,4,6,0,1]
**Output:** 9

**Constraints:**

- `0 <= nums.length <= 105`
- `-109 <= nums[i] <= 109`

-----

I think arrays.sort might be o log n time, so might potentially revisit this question - but solution seems to be just using arrays.sort and an if statement..?
<h1> Solution </h1>
class Solution {

    public int longestConsecutive(int[] nums) {

        if (nums.length == 0) return 0;

        Arrays.sort(nums);

        int seq = 1;

        int temp = 1;

        for (int i = 0; i < nums.length - 1; i++)

        {

            if (nums[i] + 1 == nums[i + 1])

            {

                temp++;

                if (temp > seq)

                {

                    seq = temp;

                }

            }

            else

            {

                if (nums[i] == nums[i + 1])

                {

                    continue;

                }

                temp = 1;

            }

        }

        return seq;

    }

}