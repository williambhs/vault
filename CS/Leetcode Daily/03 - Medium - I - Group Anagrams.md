
**Problem Number: 49
Relevant Tags: [[03 - Easy - O - Valid Anagram]], [[02 - DS - O - Hashmap]]
<h1> Problem Description </h1>
Given an array of strings `strs`, group **the anagrams** together. You can return the answer in **any order**.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Example 1:**

**Input:** strs = ["eat","tea","tan","ate","nat","bat"]
**Output:** [["bat"],["nat","tan"],["ate","eat","tea"]]

**Example 2:**

**Input:** strs = [""]
**Output:** [[""]]

**Example 3:**

**Input:** strs = ["a"]
**Output:** [["a"]]

**Constraints:**

- `1 <= strs.length <= 104`
- `0 <= strs[i].length <= 100`
- `strs[i]` consists of lowercase English letters.

-----
trying to think of ways to solve this problem - 
could use double for loop. definitely inefficient but would work.
implementation would look like 
1 - initialize an empty hashmap
2 - convert the array to an arraylist so you can remove stuff
3 - iterate over every string:
a] add the string to the list of lists
b] add each character to the hashmap, then compare that to every other string in a nested for loop
4 - if it finds a match, add the other string, then remove it from the arraylist 
5 - clear the hashmap
6 - return 
7 - profit?!?!?!?

<h1> Solution </h1>
