**Problem Number: 724
Relevant Tags: [[04 - A - O - Prefix Sum]]
<h1> Problem Description </h1>
Given an array of integers `nums`, calculate the **pivot index** of this array.

The **pivot index** is the index where the sum of all the numbers **strictly** to the left of the index is equal to the sum of all the numbers **strictly** to the index's right.

If the index is on the left edge of the array, then the left sum is `0` because there are no elements to the left. This also applies to the right edge of the array.

Return _the **leftmost pivot index**_. If no such index exists, return `-1`.

**Example 1:**

**Input:** nums = [1,7,3,6,5,6]
**Output:** 3
**Explanation:**
The pivot index is 3.
Left sum = nums[0] + nums[1] + nums[2] = 1 + 7 + 3 = 11
Right sum = nums[4] + nums[5] = 5 + 6 = 11

**Example 2:**

**Input:** nums = [1,2,3]
**Output:** -1
**Explanation:**
There is no index that satisfies the conditions in the problem statement.

**Example 3:**

**Input:** nums = [2,1,-1]
**Output:** 0
**Explanation:**
The pivot index is 0.
Left sum = 0 (no elements to the left of index 0)
Right sum = nums[1] + nums[2] = 1 + -1 = 0

**Constraints:**

- `1 <= nums.length <= 104`
- `-1000 <= nums[i] <= 1000`

-----

Use prefix sums - create a hashmap where you put all the prefix sums, then return the value mapped to the greatest prefix sums key/2.
Oh, apparently the the sum can't contain the index itself.
Instead create an array of prefix sums that starts with 0 at index 0 in case the answer is the first value - then iterate through the array and if sum - prefixSum[i] == prefixSum[i+1] then you return i.

<h1> Solution </h1>
```java
class Solution {
    public int pivotIndex(int[] nums) {

        int[] pfs = new int[nums.length + 1];
        pfs[0] = 0;
        pfs[1] = nums[0];

        for (int i = 2; i < nums.length + 1; i++) {
            pfs[i] = pfs[i - 1] + nums[i - 1];
        }

        for (int i = 0; i < pfs.length - 1; i ++) {
            if (pfs[pfs.length - 1] - pfs[i] == pfs[i+1]) {
                return i;
            }
        }
        
        return -1;
        
    }
}
```