
**Problem Number: 1248
Relevant Tags:
<h1> Problem Description </h1>
Given an array of integers `nums` and an integer `k`. A continuous subarray is called **nice** if there are `k` odd numbers on it.

Return _the number of **nice** sub-arrays_.

**Example 1:**

**Input:** nums = [1,1,2,1,1], k = 3
**Output:** 2
**Explanation:** The only sub-arrays with 3 odd numbers are [1,1,2,1] and [1,2,1,1].

**Example 2:**

**Input:** nums = [2,4,6], k = 1
**Output:** 0
**Explanation:** There are no odd numbers in the array.

**Example 3:**

**Input:** nums = [2,2,2,1,2,2,1,2,2,2], k = 2
**Output:** 16

**Constraints:**

- `1 <= nums.length <= 50000`
- `1 <= nums[i] <= 10^5`
- `1 <= k <= nums.length`

-----
Sliding window - start at nums[0], then you keep incrementing the right pointer until there are k odd numbers. Once there are k odd numbers you increment ans by 1, and shift the left pointer to the right pointer + 1, and the right pointer to the new left pointer + 1.
Apparently the solution is some very confusing prefix sum stuff, so I'm going to do some more prefix sum questions tomorrow to try and figure it out.

<h1> Solution </h1>
```java
class Solution {
    public int numberOfSubarrays(int[] nums, int k) {
        // Result to store the count of subarrays
        int result = 0;
        // Count of odd numbers seen so far
        int oddCount = 0;
        // Array to store the frequency of prefix sums (odd counts)
        int[] prefixCounts = new int[nums.length + 1];
        // There is one way to have a prefix sum of 0 (no odd numbers initially)
        prefixCounts[0] = 1;

        for (int num : nums) {
            // Increment oddCount if the current number is odd
            if (num % 2 != 0) {
                oddCount++;
            }

            // If the current oddCount is greater than or equal to k
            // we check how many times (oddCount - k) has been seen
            if (oddCount >= k) {
                result += prefixCounts[oddCount - k];
            }

            // Increment the count of the current prefix sum
            prefixCounts[oddCount]++;
        }

        return result;
    }
}
```