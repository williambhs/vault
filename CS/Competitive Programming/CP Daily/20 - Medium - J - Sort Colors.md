
**Problem Number: 75
Relevant Tags: [[04 - A - O - Two Pointers]]
<h1> Problem Description </h1>
Given an array `nums` with `n` objects colored red, white, or blue, sort them **[in-place](https://en.wikipedia.org/wiki/In-place_algorithm)** so that objects of the same color are adjacent, with the colors in the order red, white, and blue.

We will use the integers `0`, `1`, and `2` to represent the color red, white, and blue, respectively.

You must solve this problem without using the library's sort function.

**Example 1:**

**Input:** nums = [2,0,2,1,1,0]
**Output:** [0,0,1,1,2,2]

**Example 2:**

**Input:** nums = [2,0,1]
**Output:** [0,1,2]

**Constraints:**

- `n == nums.length`
- `1 <= n <= 300`
- `nums[i]` is either `0`, `1`, or `2`.

**Follow up:** Could you come up with a one-pass algorithm using only constant extra space?

-----
Throw a hashmap at it!


<h1> Solution </h1>
class Solution {

    public void sortColors(int[] nums) {

        HashMap<Integer, Integer> map = new HashMap<>();

        map.put(0, 0);

        map.put(1, 0);

        map.put(2, 0);

  

        for (int num: nums) {

            map.put(num, map.get(num) + 1);

        }

  

        for (int i = 0; i < nums.length; i++) {

  

            if (i < map.get(0)) {

                nums[i] = 0;

            }

  

            else if (i >= map.get(0) && i < map.get(0) + map.get(1)) {

                nums[i] = 1;

            }

  

            else {

                nums[i] = 2;

            }

        }

  
  

    }

}