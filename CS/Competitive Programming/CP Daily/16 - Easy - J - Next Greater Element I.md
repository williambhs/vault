
**Problem Number: 496
Relevant Tags: [[02 - DS - O - Stack]], [[02 - DS - Monotonic Stack]]
<h1> Problem Description </h1>
The **next greater element** of some element `x` in an array is the **first greater** element that is **to the right** of `x` in the same array.

You are given two **distinct 0-indexed** integer arrays `nums1` and `nums2`, where `nums1` is a subset of `nums2`.

For each `0 <= i < nums1.length`, find the index `j` such that `nums1[i] == nums2[j]` and determine the **next greater element** of `nums2[j]` in `nums2`. If there is no next greater element, then the answer for this query is `-1`.

Return _an array_ `ans` _of length_ `nums1.length` _such that_ `ans[i]` _is the **next greater element** as described above._

**Example 1:**

**Input:** nums1 = [4,1,2], nums2 = [1,3,4,2]
**Output:** [-1,3,-1]
**Explanation:** The next greater element for each value of nums1 is as follows:
- 4 is underlined in nums2 = [1,3,4,2]. There is no next greater element, so the answer is -1.
- 1 is underlined in nums2 = [1,3,4,2]. The next greater element is 3.
- 2 is underlined in nums2 = [1,3,4,2]. There is no next greater element, so the answer is -1.

**Example 2:**

**Input:** nums1 = [2,4], nums2 = [1,2,3,4]
**Output:** [3,-1]
**Explanation:** The next greater element for each value of nums1 is as follows:
- 2 is underlined in nums2 = [1,2,3,4]. The next greater element is 3.
- 4 is underlined in nums2 = [1,2,3,4]. There is no next greater element, so the answer is -1.

**Constraints:**

- `1 <= nums1.length <= nums2.length <= 1000`
- `0 <= nums1[i], nums2[i] <= 104`
- All integers in `nums1` and `nums2` are **unique**.
- All the integers of `nums1` also appear in `nums2`.

**Follow up:** Could you find an `O(nums1.length + nums2.length)` solution?

-----
Obviously solvable using nested loops - iterate through each number in nums2 and check if it's greater than nums[i].
Finding a solution in O(nums1.length + nums2.length) is the hard part - need to come back to this later.

Coming back to this problem now - the fast solution uses a monotonic stack to process elements (see: [[02 - DS - Monotonic Stack]]) 
The solution is to use a monotonic stack combined with a hashmap. You iterate through nums2 and create a monotonic stack - whenever a greater element is found, you keep popping items off the stack that are less than it because that item is now the greatest element on the right in that position. Then, for each item you pop off, you add it to the map to store the relationship.
The elements remaining in the stack have no greater element to the right, and at the end of the loop the map will be filled with elements from nums2 as well as the next greater element in nums2.

Finally, since all elements in nums1 are in nums2, you use the hashmap and add the value to a new array.
<h1> Solution </h1>

class Solution {

    public int[] nextGreaterElement(int[] nums1, int[] nums2) {

        int[] ans = new int[nums1.length];

        for (int i = 0; i < nums1.length; i++)

        {

            int curr = nums1[i];

            int index = -1;

            for (int j = 0; j < nums2.length; j++) {

                if (nums2[j] == curr) index = j;

            }

  

            for (int k = index; k < nums2.length; k++)

            {

                if (nums2[k] > curr) {

                ans[i] = nums2[k];

                break;

                }

  

                else if (k == nums2.length - 1) {

                    ans[i] = -1;

                }

            }

        }

        return ans;

    }

}

**NEW Solution:**
public class Solution {

    public int[] nextGreaterElement(int[] nums1, int[] nums2) {

        HashMap<Integer, Integer> map = new HashMap<>();

        Stack<Integer> stack = new Stack<>();

  

        for (int i = 0; i < nums2.length; i++) {

            while (!stack.isEmpty() && nums2[i] > stack.peek()) {

                map.put(stack.pop(), nums2[i]);

            }

            stack.push(nums2[i]);

        }

  

        while (!stack.isEmpty()) {

            map.put(stack.pop(), -1);

        }

  

        int[] result = new int[nums1.length];

        for (int i = 0; i < nums1.length; i++) {

            result[i] = map.get(nums1[i]);

        }

  

        return result;

    }

}
