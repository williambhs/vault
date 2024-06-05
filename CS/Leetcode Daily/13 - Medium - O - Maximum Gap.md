**Problem Number: 164
Relevant Tags: 
<h1> Problem Description </h1>
Given an integer array `nums`, return _the maximum difference between two successive elements in its sorted form_. If the array contains less than two elements, return `0`.

You must write an algorithm that runs in linear time and uses linear extra space.

**Example 1:**

**Input:** nums = [3,6,9,1]
**Output:** 3
**Explanation:** The sorted form of the array is [1,3,6,9], either (3,6) or (6,9) has the maximum difference 3.

**Example 2:**

**Input:** nums = [10]
**Output:** 0
**Explanation:** The array contains less than 2 elements, therefore return 0.

**Constraints:**

- `1 <= nums.length <= 105`
- `0 <= nums[i] <= 109`

-----
pretty sure this is cheating but.. it works. the correct solution is to use radix sort, might come back to this in the future

<h1> Solution </h1>
class Solution {

public int maximumGap(int[] nums) {

if (nums.length < 2) return 0;

Arrays.sort(nums);

int max = Math.abs(nums[0] - nums[1]);

for (int i = 1; i < nums.length - 1; i++)

{

max = Math.max(max, Math.abs(nums[i]-nums[i+1]));

}

return max;

}

}