
**Problem Number: 151
Relevant Tags: [[03 - DT - O - Character]]
<h1> Problem Description </h1>
Given an input string `s`, reverse the order of the **words**.

A **word** is defined as a sequence of non-space characters. The **words** in `s` will be separated by at least one space.

Return _a string of the words in reverse order concatenated by a single space._

**Note** that `s` may contain leading or trailing spaces or multiple spaces between two words. The returned string should only have a single space separating the words. Do not include any extra spaces.

**Example 1:**

**Input:** s = "the sky is blue"
**Output:** "blue is sky the"

**Example 2:**

**Input:** s = "  hello world  "
**Output:** "world hello"
**Explanation:** Your reversed string should not contain leading or trailing spaces.

**Example 3:**

**Input:** s = "a good   example"
**Output:** "example good a"
**Explanation:** You need to reduce multiple spaces between two words to a single space in the reversed string.

**Constraints:**

- `1 <= s.length <= 104`
- `s` contains English letters (upper-case and lower-case), digits, and spaces `' '`.
- There is **at least one** word in `s`.

**Follow-up:** If the string data type is mutable in your language, can you solve it **in-place** with `O(1)` extra space?

-----
Not sure why this is a medium problem, going to create an arraylist - first turn the string s into a character array, then use the ascii table - if the character is a letter add it to a temp string, then if the character is not a letter add the temp string to the arraylist of strings. At the end add all the strings in the arraylist to a string with a space in between.

** Maybe come back to this problem and use stringbuilder as a more efficient approach to run in O(n) time - concatenation causes it to create a new string constantly.

<h1> Solution </h1>
class Solution {

public String reverseWords(String s) {

ArrayList<String> list = new ArrayList<String>();

char[] arr = s.toCharArray();

String temp = "";

String str = "";

for (char c: arr)

{

// check if it's a character

if (c != ' ') {

temp += c;

}

else

{

if (temp.length() >= 1) list.add(temp);

temp = "";

}

}

list.add(temp);

for (int i = list.size() - 1; i >= 0; i--)

{

if (!list.get(i).equals(""))

{

str += list.get(i);

if (i != 0) str += " ";

}

}

return str;

}

}