
**Problem Number: 242
Relevant Tags:
<h1> Problem Description </h1>
Given two strings `s` and `t`, return `true` _if_ `t` _is an anagram of_ `s`_, and_ `false` _otherwise_.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Example 1:**

**Input:** s = "anagram", t = "nagaram"
**Output:** true

**Example 2:**

**Input:** s = "rat", t = "car"
**Output:** false

**Constraints:**

- `1 <= s.length, t.length <= 5 * 104`
- `s` and `t` consist of lowercase English letters.

-----

Remember doing this one last summer. Seems pretty easy, just use charat and compare two strings.
nevermind i thought this was palindrome, lmao. still doesnt seem too hard. just convert the string into a hashmap... similar to the ransomnote problem (see - [[03 - Easy - CJ - Ransom Note]])
<h1> Solution </h1>
class Solution {

public boolean isAnagram(String s, String t) {

HashMap<Character, Integer> string1 = new HashMap<>();

HashMap<Character, Integer> string2 = new HashMap<>();

  

// map 1

for (int i = 0; i < s.length(); i++)

{

char c = s.charAt(i);

if (string1.containsKey(c))

{

string1.put(c, string1.get(c) + 1);

}

else

{

string1.put(c, 1);

}

}

  

//map 2

for (int i = 0; i < t.length(); i++)

{

char c = t.charAt(i);

if (string2.containsKey(c))

{

string2.put(c, string2.get(c) + 1);

}

else

{

string2.put(c, 1);

}

}

return string1.equals(string2);

  

}

}