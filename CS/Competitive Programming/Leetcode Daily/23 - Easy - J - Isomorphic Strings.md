
**Problem Number: 205
Relevant Tags: [[02 - DS - O - Hashmap]]
<h1> Problem Description </h1>


-----
Use a hashmap and convert s and t into two char arrays. 

Then iterate through s and t at the same time and map the character to s to the character at t.

If the character at s already has a value mapped to it, or in other words if map.containsKey(s[i]), check if t[i] = map.get(s[i]) - if not then return false.

Otherwise, return true.
Ok I couldn't get this to work so just made two hashmaps. But hey it worked so not much to complain about.
<h1> Solution </h1>

class Solution {

public boolean isIsomorphic(String s, String t) {

  

char[] str1 = s.toCharArray();

char[] str2 = t.toCharArray();

HashMap<Character, Character> map1 = new HashMap<>();

HashMap<Character, Character> map2 = new HashMap<>();

  

for (int i = 0; i < str1.length; i++) {

  

if (map1.containsKey(str1[i])) {

if (str2[i] != map1.get(str1[i])) return false;

}

  

if (map2.containsKey(str2[i])) {

if (str1[i] != map2.get(str2[i])) return false;

}

map1.put(str1[i],str2[i]);

map2.put(str2[i],str1[i]);

}

  

return true;

}

}