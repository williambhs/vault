
**Problem Number: 409
Relevant Tags: [[02 - DS - O - Hashmap]]
<h1> Problem Description </h1>
Given a string `s` which consists of lowercase or uppercase letters, return the length of the **longest** 

**palindrome**

 that can be built with those letters.

Letters are **case sensitive**, for example, `"Aa"` is not considered a palindrome.

**Example 1:**

**Input:** s = "abccccdd"
**Output:** 7
**Explanation:** One longest palindrome that can be built is "dccaccd", whose length is 7.

**Example 2:**

**Input:** s = "a"
**Output:** 1
**Explanation:** The longest palindrome that can be built is "a", whose length is 1.

**Constraints:**

- `1 <= s.length <= 2000`
- `s` consists of lowercase **and/or** uppercase English letters only.
-----
Saw some guy sitting next to me trying to solve this problem so decided to try and solve it myself.
Thinking about using a hashmap - adding everything with getordefault(0)
then for each key - if the value is divisible y 2 add the key value/2 times to a string.
finally reverse the string, add it to itself, and return the result as the answer.

Ok nevermind this is way easier than I thought you only have to return the length of the palindrome.
<h1> Solution </h1>
class Solution {

    public int longestPalindrome(String s) {

  

        if (s.length() == 1) return 1;

  

        HashMap<Character, Integer> map = new HashMap<>();

        int ans = 0;

  
  

        for (int i = 0; i < s.length(); i++) {

            map.put(s.charAt(i), map.getOrDefault(s.charAt(i), 0) + 1);

        }

  

        int size = map.size();

        if (map.size() == 1) {

            for (Character c : map.keySet()){

                return map.get(c);

            }

        }

  

        boolean hasOdd = false;

        for (Character c : map.keySet()) {

            ans = (map.get(c) % 2 == 0) ? ans + map.get(c) : ans + map.get(c) - 1;

            if (map.get(c) % 2 != 0) hasOdd = true;      

        }

  

        if (hasOdd) ans++;

        return ans;

    }

}