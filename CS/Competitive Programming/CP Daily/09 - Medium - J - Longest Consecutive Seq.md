
**Problem Number: 128
Relevant Tags: [[02 - DS - O - HashSet]]
<h1> Problem Description </h1>
Given an unsorted array of integers `nums`, return _the length of the longest consecutive elements sequence._

You must write an algorithm that runs in `O(n)` time.

**Example 1:**

**Input:** nums = [100,4,200,1,3,2]
**Output:** 4
**Explanation:** The longest consecutive elements sequence is `[1, 2, 3, 4]`. Therefore its length is 4.

**Example 2:**

**Input:** nums = [0,3,7,2,5,8,4,6,0,1]
**Output:** 9

**Constraints:**

- `0 <= nums.length <= 105`
- `-109 <= nums[i] <= 109`

-----
Thinking about adding every value to a hashset with a for loop, for each value in the hashset, for i < key + arr.length, if the set contains key + i increment a temp variable that tracks the length
Apparently this solution is too inefficient, but a while loop works which is odd. Need to look into time complexity of nested for loop vs while loop in a for loop.
<h1> Solution </h1>
class Solution {

public int longestConsecutive(int[] nums) {

if (nums.length == 0) return 0;

  

HashSet<Integer> set = new HashSet<>();

for (int i: nums)

{

set.add(i);

}

  

int len = 1;

for (int num: set)

{

if (!set.contains(num - 1))

{

int curr = num;

int temp = 1;

while (set.contains(curr + 1))

{

curr++;

temp++;

if (temp > len)

{

len = temp;

}

}

}

}

return len;

}

}