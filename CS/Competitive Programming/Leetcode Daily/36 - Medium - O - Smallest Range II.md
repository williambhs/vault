
**Problem Number: 910
Relevant Tags:
<h1> Problem Description </h1>
You are given an integer array `nums` and an integer `k`.

For each index `i` where `0 <= i < nums.length`, change `nums[i]` to be either `nums[i] + k` or `nums[i] - k`.

The **score** of `nums` is the difference between the maximum and minimum elements in `nums`.

Return _the minimum **score** of_ `nums` _after changing the values at each index_.

**Example 1:**

**Input:** nums = [1], k = 0
**Output:** 0
**Explanation:** The score is max(nums) - min(nums) = 1 - 1 = 0.

**Example 2:**

**Input:** nums = [0,10], k = 2
**Output:** 6
**Explanation:** Change nums to be [2, 8]. The score is max(nums) - min(nums) = 8 - 2 = 6.

**Example 3:**

**Input:** nums = [1,3,6], k = 3
**Output:** 3
**Explanation:** Change nums to be [4, 6, 3]. The score is max(nums) - min(nums) = 6 - 3 = 3.

**Constraints:**

- `1 <= nums.length <= 104`
- `0 <= nums[i] <= 104`
- `0 <= k <= 104`

-----
Previously used an average but didn't work too well. Instead maybe iterate through the array, and keep a current min and current max. You want to add or subtract k based on the current min and max value - if it's closer to the current min you want to add k and if it's closer to the current max you want to subtract k because you don't want a new min/max. I am 99% sure this is wrong but I am going to implement it and when it doesn't work I will look at the solutions.

<h1> Solution </h1>
```cpp
class Solution {
public:
    int smallestRangeII(vector<int>& nums, int k) {
        if (nums.size() == 1) return 0;

        sort(nums.begin(), nums.end());
        int n = nums.size();

        int smallestRange = nums[n - 1] - nums[0];

        for (int i = 0; i < n - 1; ++i) {
            int high = max(nums[n - 1] - k, nums[i] + k);
            int low = min(nums[0] + k, nums[i + 1] - k);
            smallestRange = min(smallestRange, high - low);
        }

        return smallestRange;
    }
};
```so you guy