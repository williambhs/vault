
**Problem Number: 153
Relevant Tags: [[04 - A - O - Binary Search]]
<h1> Problem Description </h1>
Suppose an array of length `n` sorted in ascending order is **rotated** between `1` and `n` times. For example, the array `nums = [0,1,2,4,5,6,7]` might become:

- `[4,5,6,7,0,1,2]` if it was rotated `4` times.
- `[0,1,2,4,5,6,7]` if it was rotated `7` times.

Notice that **rotating** an array `[a[0], a[1], a[2], ..., a[n-1]]` 1 time results in the array `[a[n-1], a[0], a[1], a[2], ..., a[n-2]]`.

Given the sorted rotated array `nums` of **unique** elements, return _the minimum element of this array_.

You must write an algorithm that runs in `O(log n) time.`

**Example 1:**

**Input:** nums = [3,4,5,1,2]
**Output:** 1
**Explanation:** The original array was [1,2,3,4,5] rotated 3 times.

**Example 2:**

**Input:** nums = [4,5,6,7,0,1,2]
**Output:** 0
**Explanation:** The original array was [0,1,2,4,5,6,7] and it was rotated 4 times.

**Example 3:**

**Input:** nums = [11,13,15,17]
**Output:** 11
**Explanation:** The original array was [11,13,15,17] and it was rotated 4 times. 

**Constraints:**

- `n == nums.length`
- `1 <= n <= 5000`
- `-5000 <= nums[i] <= 5000`
- All the integers of `nums` are **unique**.
- `nums` is sorted and rotated between `1` and `n` times.

-----
Solution has something to do with binary search - but the array could be rotated
Means potentially the greatest value could be first
Unlike traditional binary search you should adjust where to move the mid index based on the value of the left and right pointers because it's sorted but rotated
Means instead you compare mid to nums[left] and nums[right]

If the middle is more than the right the point of rotation has to be on the right - that means the minimum value is on the right side
If it's less than or equal to right the pivot must be on the left side, or the minimum element itself

Example arrays to visualize:
5, 0, 1, 2, 3, 4 - where mid < left
3, 4, 5, 0, 1, 2 - where mid < right
<h1> Solution </h1>
class Solution {

public int findMin(int[] nums) {

int left = 0;

int right = nums.length - 1;

int mid = nums[0];

if (nums.length == 1) return mid;

while (left < right)

{

mid = left + (right - left) / 2;

if (nums[mid] > nums[right]) left = mid + 1;

if (nums[mid] <= nums[right]) right = mid;

}

return nums[left];

}

}