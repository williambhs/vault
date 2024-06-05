
**Problem Number: 20
Relevant Tags: [[02 - DS - O - Stack]]
<h1> Problem Description </h1>
Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
3. Every close bracket has a corresponding open bracket of the same type.

**Example 1:**

**Input:** s = "()"
**Output:** true

**Example 2:**

**Input:** s = "()[]{}"
**Output:** true

**Example 3:**

**Input:** s = "(]"
**Output:** false

**Constraints:**

- `1 <= s.length <= 104`
- `s` consists of parentheses only `'()[]{}'`.

-----
First stack problem - still trying to understand how stack works.
Solution should be to push the element onto the stack if its empty - peek the stack if its not empty, if the next character is not equal return false, else pop the stack and continue.
Also going to use a hashmap to make this a little more bearable.

Ok it seems it is actually not so simple, because you might have something like "({})" which is valid because the curly brackets are closed after the parenthesis. That means in the stack all you have to keep track of is if there are more opening brackets than closing brackets, and at the end return if the stack is empty or not. 

New solution:
1 - push element onto stack if empty
2 - if not empty, check if stack contains opening bracket 
<h1> Solution </h1>
