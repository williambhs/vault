
**Problem Number: 3
Relevant Tags: [[02 - DS - O - HashSet]]
<h1> Problem Description </h1>

Given a string `s`, find the length of the **longest** 

**substring**

 without repeating characters.

**Example 1:**

**Input:** s = "abcabcbb"
**Output:** 3
**Explanation:** The answer is "abc", with the length of 3.

**Example 2:**

**Input:** s = "bbbbb"
**Output:** 1
**Explanation:** The answer is "b", with the length of 1.

**Example 3:**

**Input:** s = "pwwkew"
**Output:** 3
**Explanation:** The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.

**Constraints:**

- `0 <= s.length <= 5 * 104`
- `s` consists of English letters, digits, symbols and spaces.
-----
Possible solution is to convert the string into a character array - then create a hashmap of char and integer

But alternatively - sliding window approach
Loop goes to the arr - 1, window starts at arr[i], arr[j] with j being i + 1. if 

After revisiting this problem, the solution doesn't seem so bad - just create a hashset, and then two pointers for the sliding window, a left and a right pointer - while the right pointer is not less than the length of the string - 1 keep increasing the size of the array and adding the next element into the hashset. If the set contains the element you increase the left pointer and subtract one from some temp variable, then continue to increment the right pointer. A temp and len variable should be initialized to zero, temp is the size of the window at any point in time and len is the largest size of the sliding window. At the end, the value for len is the largest the window has been and thus the longest substring without repeating characters.


<h1> Solution </h1>
class Solution {

public int lengthOfLongestSubstring(String s) {

  

if (s.length() == 0) return 0;

  

char[] arr = s.toCharArray();

HashSet<Character> set = new HashSet<>();

set.add(arr[0]);

  

// initializing pointers, current length, max length

int left = 0;

int right = 1;

int temp = 1;

int len = 1;

  

// loop

while (right < arr.length)

{

char curr = arr[right];

if (!set.contains(curr))

{

set.add(curr);

temp++;

if (temp > len)

{

len = temp;

}

right++;

}

else

{

while (set.contains(curr))

{

set.remove(arr[left]);

left++;

  

temp--;

}

}

}

  

return len;

}

}