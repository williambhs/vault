**Problem Number: 1
Difficulty: Easy
Relevant Tags: [[01 - DSA - Hashmap - X]]**
<h1> Problem Description </h1>
Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

-----

solved w/ brute force method -- revisit in the future and solve with faster time complexity
see:

<h1> Solution </h1>
class Solution {

public int[] twoSum(int[] nums, int target) {

int[] arr = new int[2];

for (int i = 0; i < nums.length; i++)

{

for (int j = i + 1 ; j < nums.length; j++)

{

if (nums[i] + nums[j] == target)

{

arr[0] = i;

arr[1] = j;

return arr;

}

}

}

return arr;

}

}
