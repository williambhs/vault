**Problem Number: 219
Relevant Tags: [[04 - A - O - Sliding Window]], [[02 - DS - O - HashSet]]
<h1> Problem Description </h1>
Given an integer array `nums` and an integer `k`, return `true` _if there are two **distinct indices**_ `i` _and_ `j` _in the array such that_ `nums[i] == nums[j]` _and_ `abs(i - j) <= k`.

**Example 1:**

**Input:** nums = [1,2,3,1], k = 3
**Output:** true

**Example 2:**

**Input:** nums = [1,0,1,1], k = 1
**Output:** true

**Example 3:**

**Input:** nums = [1,2,3,1,2,3], k = 2
**Output:** false

**Constraints:**

- `1 <= nums.length <= 105`
- `-109 <= nums[i] <= 109`
- `0 <= k <= 105`

-----

Solve in o(n) time using sliding window approach - actually an interesting problem where k is the max size the sliding window can be.
Create left and right pointers - if the distance between them (right - left) is more than k, increment left, otherwise increment right
Apparently though this doesn't work and instead you just use a hashset... whatever, passing 52/58 test cases is not bad I guess.
<h1> Solution </h1>
class Solution {

public boolean containsNearbyDuplicate(int[] nums, int k) {

  

if (k == 0) return false;

HashSet<Integer> set= new HashSet<>();

  

for (int i = 0; i < nums.length; i++)

{

if (set.contains(nums[i])) return true;

set.add(nums[i]);

if (set.size() > k) set.remove(nums[i - k]);

}

return false;

}

}