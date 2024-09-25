
**Problem Number: 739
Relevant Tags: [[02 - DS - Monotonic Stack]]
<h1> Problem Description </h1>
Given an array of integers `temperatures` represents the daily temperatures, return _an array_ `answer` _such that_ `answer[i]` _is the number of days you have to wait after the_ `ith` _day to get a warmer temperature_. If there is no future day for which this is possible, keep `answer[i] == 0` instead.

**Example 1:**

**Input:** temperatures = [73,74,75,71,69,72,76,73]
**Output:** [1,1,4,2,1,1,0,0]

**Example 2:**

**Input:** temperatures = [30,40,50,60]
**Output:** [1,1,1,0]

**Example 3:**

**Input:** temperatures = [30,60,90]
**Output:** [1,1,0]

**Constraints:**

- `1 <= temperatures.length <= 105`
- `30 <= temperatures[i] <= 100`

-----
Monotonic stack again - too lazy to type out my thought process but just copied this basically.
[Daily Temperatures (LeetCode 739) | Full solution with animations and examples | Study Algorithms (youtube.com)](https://www.youtube.com/watch?v=ekFs9Nb2RNQ)

<h1> Solution </h1>
class Solution {

    public int[] dailyTemperatures(int[] temperatures) {

        Stack<Integer> stack = new Stack<>();

        int[] ans = new int[temperatures.length];

  

        for (int i = temperatures.length - 1; i >= 0; i--) {

  

            while (!stack.isEmpty() && temperatures[stack.peek()] <= temperatures[i]) {

                stack.pop();

            }

  
  

            if (!stack.isEmpty()) {

                ans[i] = stack.peek() - i;

            }

  

            stack.push(i);

        }

  

        return ans;

    }

}