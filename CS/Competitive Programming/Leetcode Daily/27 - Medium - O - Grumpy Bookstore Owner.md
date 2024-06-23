
**Problem Number: 1052
Relevant Tags: [[04 - A - O - Sliding Window]]
<h1> Problem Description </h1>
There is a bookstore owner that has a store open for `n` minutes. Every minute, some number of customers enter the store. You are given an integer array `customers` of length `n` where `customers[i]` is the number of the customer that enters the store at the start of the `ith` minute and all those customers leave after the end of that minute.

On some minutes, the bookstore owner is grumpy. You are given a binary array grumpy where `grumpy[i]` is `1` if the bookstore owner is grumpy during the `ith` minute, and is `0` otherwise.

When the bookstore owner is grumpy, the customers of that minute are not satisfied, otherwise, they are satisfied.

The bookstore owner knows a secret technique to keep themselves not grumpy for `minutes` consecutive minutes, but can only use it once.

Return _the maximum number of customers that can be satisfied throughout the day_.

**Example 1:**

**Input:** customers = [1,0,1,2,1,1,7,5], grumpy = [0,1,0,1,0,1,0,1], minutes = 3
**Output:** 16
**Explanation:** The bookstore owner keeps themselves not grumpy for the last 3 minutes. 
The maximum number of customers that can be satisfied = 1 + 1 + 1 + 1 + 7 + 5 = 16.

**Example 2:**

**Input:** customers = [1], grumpy = [0], minutes = 1
**Output:** 1

**Constraints:**

- `n == customers.length == grumpy.length`
- `1 <= minutes <= n <= 2 * 104`
- `0 <= customers[i] <= 1000`
- `grumpy[i]` is either `0` or `1`.

-----
First calculate how much without the "secret tactic" and save it to a variable like ans.
Next create a sliding window that's minutes long - then create a max variable which is the maximum amount from making all the grumpy people happy, then add that to your initial score from all the un-grumpy people... yeah

<h1> Solution </h1>
class Solution {

public int maxSatisfied(int[] customers, int[] grumpy, int minutes) {

int n = customers.length;

// Calculate initial number of satisfied customers without using the technique.

int alreadySatisfied = 0;

for (int i = 0; i < n; i++) {

if (grumpy[i] == 0) {

alreadySatisfied += customers[i];

}

}

  

// Sliding window to calculate the maximum additional satisfied customers.

int maxAdditionalSatisfied = 0;

int currentAdditionalSatisfied = 0;

  

// Initialize the first window.

for (int i = 0; i < minutes; i++) {

if (grumpy[i] == 1) {

currentAdditionalSatisfied += customers[i];

}

}

maxAdditionalSatisfied = currentAdditionalSatisfied;

  

// Slide the window across the array.

for (int i = minutes; i < n; i++) {

if (grumpy[i - minutes] == 1) {

currentAdditionalSatisfied -= customers[i - minutes];

}

if (grumpy[i] == 1) {

currentAdditionalSatisfied += customers[i];

}

maxAdditionalSatisfied = Math.max(maxAdditionalSatisfied, currentAdditionalSatisfied);

}

  

// The final answer is the sum of already satisfied customers and the maximum additional satisfied.

return alreadySatisfied + maxAdditionalSatisfied;

}

}