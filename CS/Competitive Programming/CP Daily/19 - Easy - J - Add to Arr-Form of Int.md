
**Problem Number: 989
Relevant Tags: [[03 - DT - O - Character]]
<h1> Problem Description </h1>
The array-form** of an integer `num` is an array representing its digits in left to right order.

- For example, for `num = 1321`, the array form is `[1,3,2,1]`.

Given `num`, the **array-form** of an integer, and an integer `k`, return _the **array-form** of the integer_ `num + k`.

**Example 1:**

**Input:** num = [1,2,0,0], k = 34
**Output:** [1,2,3,4]
**Explanation:** 1200 + 34 = 1234

**Example 2:**

**Input:** num = [2,7,4], k = 181
**Output:** [4,5,5]
**Explanation:** 274 + 181 = 455

**Example 3:**

**Input:** num = [2,1,5], k = 806
**Output:** [1,0,2,1]
**Explanation:** 215 + 806 = 1021

**Constraints:**

- `1 <= num.length <= 104`
- `0 <= num[i] <= 9`
- `num` does not contain any leading zeros except for the zero itself.
- `1 <= k <= 104`

-----
First create an int k that's an int that represents the value of the k + num.
Then create a string with toString() and make another loop - while i < the length of the string, or the number of digits, you add to the arraylist the value % 10 ^ (nums.length - i)

Apparently this solution doesn't work due to integer overflow. Instead, you have to just perform the operation manually due to integer overflow for numbers that are too large.

<h1> Solution </h1>
class Solution {

    public List<Integer> addToArrayForm(int[] num, int k) {

        ArrayList<Integer> list = new ArrayList<>();

        int carry = k;

  

        for (int i = num.length - 1; i >= 0; i--) {

            list.add((num[i] + carry) % 10);

            carry = ((carry + num[i]) / 10);

        }

        while (carry != 0) {

            list.add(carry % 10);

            carry /= 10;

        }

  

        Collections.reverse(list);

        return list;

  

    }

}