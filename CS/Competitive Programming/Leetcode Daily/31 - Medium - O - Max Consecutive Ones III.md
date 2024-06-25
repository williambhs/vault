
**Problem Number: 1004
Relevant Tags: [[04 - A - O - Sliding Window]]
<h1> Problem Description </h1>
Given a binary array `nums` and an integer `k`, return _the maximum number of consecutive_ `1`_'s in the array if you can flip at most_ `k` `0`'s.

**Example 1:**

**Input:** nums = [1,1,1,0,0,0,1,1,1,1,0], k = 2
**Output:** 6
**Explanation:** [1,1,1,0,0,**1**,1,1,1,1,**1**]
Bolded numbers were flipped from 0 to 1. The longest subarray is underlined.

**Example 2:**

**Input:** nums = [0,0,1,1,0,0,1,1,1,0,1,1,0,0,0,1,1,1,1], k = 3
**Output:** 10
**Explanation:** [0,0,1,1,**1**,**1**,1,1,1,**1**,1,1,0,0,0,1,1,1,1]
Bolded numbers were flipped from 0 to 1. The longest subarray is underlined.

**Constraints:**

- `1 <= nums.length <= 105`
- `nums[i]` is either `0` or `1`.
- `0 <= k <= nums.length`

-----
One month of leetcode daily!
Use a sliding window - the problem statement basically means find the longest subarray of 1s that contains up to k 0's.
Basically just slide a window across the array with a variable that equals k - you subtract one every time you see a zero, and once the variable is less than 1 you increment the left pointer until it's 1.

<h1> Solution </h1>

```java
class Solution {
    public int longestOnes(int[] nums, int k) {
        int maxLen = 0;
        int currLen = 0;
        int flips = k;

        int left = 0;
        int right = left;

        while (right < nums.length) {
            
            if (nums[right] == 1) {
                currLen++;
            }

            else {
                currLen++;
                flips--;
                if (flips < 0) {
                    while (nums[left] != 0) {
                        currLen--;
                        left++;
                    }
                    left++;
                    currLen--;
                    flips++;
                }
            }
            maxLen = Math.max(maxLen, currLen);
            right++;

        }

        return maxLen;
        
    }
}
```