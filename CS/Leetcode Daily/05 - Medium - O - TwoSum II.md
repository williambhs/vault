
**Problem Number: 167
Relevant Tags: [[01 - Easy - I - Twosum]], [[04 - A - O - Two Pointers]]
<h1> Problem Description </h1>
Given a 1-indexed array of integers `numbers` that is already **_sorted in non-decreasing order_**, find two numbers such that they add up to a specific `target` number. Let these two numbers be `numbers[index1]` and `numbers[index2]` where `1 <= index1 < index2 <= numbers.length`.

Return _the indices of the two numbers,_ `index1` _and_ `index2`_, **added by one** as an integer array_ `[index1, index2]` _of length 2._

The tests are generated such that there is **exactly one solution**. You **may not** use the same element twice.

Your solution must use only constant extra space.

**Example 1:**

**Input:** numbers = [2,7,11,15], target = 9
**Output:** [1,2]
**Explanation:** The sum of 2 and 7 is 9. Therefore, index1 = 1, index2 = 2. We return [1, 2].

**Example 2:**

**Input:** numbers = [2,3,4], target = 6
**Output:** [1,3]
**Explanation:** The sum of 2 and 4 is 6. Therefore index1 = 1, index2 = 3. We return [1, 3].

**Example 3:**

**Input:** numbers = [-1,0], target = -1
**Output:** [1,2]
**Explanation:** The sum of -1 and 0 is -1. Therefore index1 = 1, index2 = 2. We return [1, 2].

**Constraints:**

- `2 <= numbers.length <= 3 * 104`
- `-1000 <= numbers[i] <= 1000`
- `numbers` is sorted in **non-decreasing order**.
- `-1000 <= target <= 1000`
- The tests are generated such that there is **exactly one solution**.

-----
Input array is already sorted - means you should have two pointers, i and j
if i + j is more than the target that means you need to decrement - since it's sorted that means you take j (the pointer on the right hand side) and subtract one from the index
if it's less than the target you need to add more which means you add one to i 
problem specifies that there is exactly one solution, which means you shouldn't even need a while loop since i will never be equal to j
<h1> Solution </h1>
class Solution {

public int[] twoSum(int[] numbers, int target) {

int[] arr = new int[2];

int i = 0;

int j = numbers.length - 1;

while (i != j)

{

if (numbers[i] + numbers[j] == target)

{

arr[0] = i+1;

arr[1] = j+1;

return arr;

}

  

else if (numbers[i] + numbers[j] < target)

{

i++;

}

  

else if (numbers[i] + numbers[j] > target)

{

j--;

}

  

}

return arr;

}

}