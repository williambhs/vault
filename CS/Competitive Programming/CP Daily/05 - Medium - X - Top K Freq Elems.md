
**Problem Number: 347
Relevant Tags: [[02 - DS - O - HashMap]]
<h1> Problem Description </h1>
Given an integer array `nums` and an integer `k`, return _the_ `k` _most frequent elements_. You may return the answer in any order.

**Example 1:**

**Input:** nums = [1,1,1,2,2,3], k = 2
**Output:** [1,2]

**Example 2:**

**Input:** nums = [1], k = 1
**Output:** [1]

**Constraints:**

- `1 <= nums.length <= 105`
- `-104 <= nums[i] <= 104`
- `k` is in the range `[1, the number of unique elements in the array]`.
- It is **guaranteed** that the answer is **unique**.

**Follow up:** Your algorithm's time complexity must be better than `O(n log n)`, where n is the array's size.

-----
Another medium problem - had to read over it a couple times
Asks you to return an array of the k elements that appear the most
Thinking of a solution - create a hashmap frequency table with the key being the int and the value being how frequently it appears
The issue after that is how to find the largest k values and return the corresponding keys
Probably very inefficient but you could create an arraylist - while the arraylist is less than size k you keep iterating 

coming back to this problem the next day - instead of iterating through values you could iterate through the .get() function on each key and update two variables - one that tracks the key and one that tracks the largest value returned by .get called on that key, then at the end of the loop you add the key to the array and do that k times

came up with a working solution that passes 19/21 test cases but times out 

after looking at solutions - you're supposed to create an array of lists that stores elements based on their frequency - the index is the frequency and the list at each index contains every num in nums that has that frequency.

Then, for int i = the length of the array, you add values and decrement i until i is equal to the length of the array - k.

this shit is way too hard bro ill come back and do it some later time
<h1> Solution </h1>
