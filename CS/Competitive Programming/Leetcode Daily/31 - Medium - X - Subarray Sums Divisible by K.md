
**Problem Number: 974
Relevant Tags: [[04 - A - O - Prefix Sum]], [[29 - Medium - J - Subarr Sum Equals K]]
<h1> Problem Description </h1>
Given an integer array `nums` and an integer `k`, return _the number of non-empty **subarrays** that have a sum divisible by_ `k`.

A **subarray** is a **contiguous** part of an array.

**Example 1:**

**Input:** nums = [4,5,0,-2,-3,1], k = 5
**Output:** 7
**Explanation:** There are 7 subarrays with a sum divisible by k = 5:
[4, 5, 0, -2, -3, 1], [5], [5, 0], [5, 0, -2, -3], [0], [0, -2, -3], [-2, -3]

**Example 2:**

**Input:** nums = [5], k = 9
**Output:** 0

**Constraints:**

- `1 <= nums.length <= 3 * 104`
- `-104 <= nums[i] <= 104`
- `2 <= k <= 104`

-----
Similar to other prefix sum problem - instead of making a prefix sum array maybe just make a hashset with all the sums? For each element in the hashset if it's divisible by k add one.
Nevermind this definitely doesn't work because [5] and [5, 0] would both work.
So yeah, I guess you just make a hashmap like in [[29 - Medium - J - Subarr Sum Equals K]] and then for each key in the hashmap if it's divisible by k you add the value.
Actually instead, what you could do is only put a value in the hashmap if the map contains a key in which if you subtract the key (prefix sum) from the current sum and % k == 0, because that means there's a prefix sum divisible by k in the array.
But that would need a loop, because you can't just check if a value is divisible by k without looping through each value...

<h1> Solution </h1>
