
**Problem Number: 1480
Relevant Tags: [[04 - A - O - Prefix Sum]]
<h1> Problem Description </h1>
Given an array `nums`. We define a running sum of an array as `runningSum[i] = sum(nums[0]…nums[i])`.

Return the running sum of `nums`.

**Example 1:**

**Input:** nums = [1,2,3,4]
**Output:** [1,3,6,10]
**Explanation:** Running sum is obtained as follows: [1, 1+2, 1+2+3, 1+2+3+4].

**Example 2:**

**Input:** nums = [1,1,1,1,1]
**Output:** [1,2,3,4,5]
**Explanation:** Running sum is obtained as follows: [1, 1+1, 1+1+1, 1+1+1+1, 1+1+1+1+1].

**Example 3:**

**Input:** nums = [3,1,2,10,1]
**Output:** [3,4,6,16,17]

**Constraints:**

- `1 <= nums.length <= 1000`
- `-10^6 <= nums[i] <= 10^6`


-----
Just doing some prefix sum practice. This problem literally just asks you to make a prefix sum array. 

<h1> Solution </h1>
```java
class Solution {
    public int[] runningSum(int[] nums) {

        int[] pfs = new int[nums.length];
        pfs[0] = nums[0];
        for (int i = 1; i < nums.length; i++) {
            pfs[i] = nums[i] + pfs[i - 1];
        }
        return pfs;
        
    }
}
```
----
C++ Solution
```cpp
class Solution {
public:
    vector<int> runningSum(vector<int>& nums) {
        vector<int> ans(nums.size(), 0);
        ans[0] = nums[0];
        for (int i = 1; i < nums.size(); i++) {
            ans[i] = ans[i-1] + nums[i];
        }
        return ans;
        
    }
};
```