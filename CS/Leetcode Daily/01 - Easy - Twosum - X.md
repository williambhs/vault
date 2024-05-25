**Problem Number: 1
Difficulty: Easy
Relevant Tags: [[02 - DS - Hashmap - O]]**
<h1> Problem Description </h1>
Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

-----

solved w/ brute force method -- revisit in the future and solve with faster time complexity

** revisiting the next day
hashmap solution with o time complexity - 
start by looping thru the array and adding to hashmap with the value + index
then check to see if (target - value) in array is equal to any key in the hashmap, if yes then populate the array with the value mapped to the key and the current index of the loop

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
