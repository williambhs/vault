
**Problem Number: 15
Relevant Tags: [[01 - Easy - O - Twosum]], [[05 - Medium - O - TwoSum II]], [[04 - A - O - Two Pointers]]
<h1> Problem Description </h1>
Given an integer array nums, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.

Notice that the solution set must not contain duplicate triplets.

**Example 1:**

**Input:** nums = [-1,0,1,2,-1,-4]
**Output:** [[-1,-1,2],[-1,0,1]]
**Explanation:** 
nums[0] + nums[1] + nums[2] = (-1) + 0 + 1 = 0.
nums[1] + nums[2] + nums[4] = 0 + 1 + (-1) = 0.
nums[0] + nums[3] + nums[4] = (-1) + 2 + (-1) = 0.
The distinct triplets are [-1,0,1] and [-1,-1,2].
Notice that the order of the output and the order of the triplets does not matter.

**Example 2:**

**Input:** nums = [0,1,1]
**Output:** []
**Explanation:** The only possible triplet does not sum up to 0.

**Example 3:**

**Input:** nums = [0,0,0]
**Output:** [[0,0,0]]
**Explanation:** The only possible triplet sums up to 0.

**Constraints:**

- `3 <= nums.length <= 3000`
- `-105 <= nums[i] <= 105`

-----
The third twosum problem now - should be pretty simple, going to just sort the array and then check if i in the array + j (i+1) + k (array.length) is equal to target, if yes add i, j, and k to the array, if j = k stop looping.

came up with working solution that passes 311/313 test cases but exceeds time limit. the contains method is too expensive most likely.
Solved with hashset - just added everything to the set and then later to the list. Didn't need to use the contain method.

<h1> Solution </h1>

----
class Solution {

    public List<List<Integer>> threeSum(int[] nums) {

        Arrays.sort(nums);

        ArrayList<List<Integer>> list = new ArrayList<List<Integer>>();

        HashSet<List<Integer>> set = new HashSet<List<Integer>>();

  

        for (int i = 0; i < nums.length - 1; i++)

        {

            int j = i + 1;

            int k = nums.length - 1;

  

            while (j < k)

            {

                if (nums[i] + nums[j] + nums[k] == 0)

                {

                    ArrayList<Integer> temp = new ArrayList<Integer>();

                    temp.add(nums[i]);

                    temp.add(nums[j]);

                    temp.add(nums[k]);        

                    set.add(temp);  

                    j++;

                }

  

                else if (nums[i] + nums[j] + nums[k] < 0)

                {

                    j++;

                }

  

                else

                {

                    k--;

                }    

            }

  

        }

        for (List<Integer> l: set)

        {

            list.add(l);

        }

        return list;

    }

}