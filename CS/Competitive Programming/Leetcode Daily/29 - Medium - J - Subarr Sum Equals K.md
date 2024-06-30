
**Problem Number: 560
Relevant Tags:
<h1> Problem Description </h1>
Given an array of integers `nums` and an integer `k`, return _the total number of subarrays whose sum equals to_ `k`.

A subarray is a contiguous **non-empty** sequence of elements within an array.

**Example 1:**

**Input:** nums = [1,1,1], k = 2
**Output:** 2

**Example 2:**

**Input:** nums = [1,2,3], k = 3
**Output:** 2

**Constraints:**

- `1 <= nums.length <= 2 * 104`
- `-1000 <= nums[i] <= 1000`
- `-107 <= k <= 107`

-----

So I memorized the code but I'm still trying to wrap my head around the solution
You want to create a hashmap that stores:
1 - key mapped to the sum of curr subarrays
2 - the number of times that sum has been made to account for negative numbers

Then as you iterate through the array you check if there has been a prefix sum that is equal to sum - k in the map. 
If you want the sum of a subarray from i to j, you use prefix sums and subtract prefixSum[i-1] from prefixSum[j], since that basically "chops off" the part of the array before prefixSum[i], and the value of prefixSum[j] is equal to all the values from 0 to j summed up.
![[terrible pfixsum diagram I made.png]]
The diagram is trying to illustrate how j is equal to everything from index 0 to j, meanwhile i-1 is just everything from 0 to i - 1, meaning if you subtract pfixsum[i] you are left with all the values summed from i to j.

Using this intuition, going back to the initial problem, the hashmap contains all the prefixSums and their counts. If we can subtract the target from the sum and get any of the prefix sums in the hashmap, that means there's a prefix sum in the hashmap where if you add target you get the current sum. This is because if we want to get a subarray that adds up to k, using the previous formula, we can say prefixSum[j] - prefixSum[i-1] = k. Basically, if the difference between the current sum and any other previous prefix sums is equal to k, then the values in between them have to sum to k.

<h1> Solution </h1>
