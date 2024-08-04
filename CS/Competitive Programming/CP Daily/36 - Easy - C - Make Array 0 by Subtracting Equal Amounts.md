
**Problem Number: 2357
Relevant Tags:
<h1> Problem Description </h1>
You are given a non-negative integer array `nums`. In one operation, you must:

- Choose a positive integer `x` such that `x` is less than or equal to the **smallest non-zero** element in `nums`.
- Subtract `x` from every **positive** element in `nums`.

Return _the **minimum** number of operations to make every element in_ `nums` _equal to_ `0`.

**Example 1:**

**Input:** nums = [1,5,0,3,5]
**Output:** 3
**Explanation:**
In the first operation, choose x = 1. Now, nums = [0,4,0,2,4].
In the second operation, choose x = 2. Now, nums = [0,2,0,0,2].
In the third operation, choose x = 2. Now, nums = [0,0,0,0,0].

**Example 2:**

**Input:** nums = [0]
**Output:** 0
**Explanation:** Each element in nums is already 0 so no operations are needed.

**Constraints:**

- `1 <= nums.length <= 100`
- `0 <= nums[i] <= 100`

-----
idk how I came up with this, but it works, so...
switching to c++.

<h1> Solution </h1>
```cpp
class Solution {
public:
    int minimumOperations(vector<int>& nums) {
        unordered_set<int> uniquePositiveNums;
        
        for (int num : nums) {
            if (num > 0) {
                uniquePositiveNums.insert(num);
            }
        }
        
        return uniquePositiveNums.size();
    }
};
```