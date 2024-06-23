
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


<h1> Solution </h1>
