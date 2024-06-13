
**Problem Number: 383
Relevant Tags: [[02 - DS - O - HashMap]]
<h1> Problem Description </h1>

Given two strings `ransomNote` and `magazine`, return `true` _if_ `ransomNote` _can be constructed by using the letters from_ `magazine` _and_ `false` _otherwise_.

Each letter in `magazine` can only be used once in `ransomNote`.

**Example 1:**

**Input:** ransomNote = "a", magazine = "b"
**Output:** false

**Example 2:**

**Input:** ransomNote = "aa", magazine = "ab"
**Output:** false

**Example 3:**

**Input:** ransomNote = "aa", magazine = "aab"
**Output:** true

**Constraints:**

- `1 <= ransomNote.length, magazine.length <= 105`
- `ransomNote` and `magazine` consist of lowercase English letters.
-----
methodname is public boolean canConstruct(String ransomNote, String magazine) 
given two strings - one way to solve would be to create a hashmap with every letter in magazine, then for each character in ransomnote check if its in the map, if yes remove it and go to the next character
there can be multiple keys mapped to the same value, but there can't be the same key mapped to different values - that means when creating the hashmap the index should be the key and the character in magazine should be the value, and then you just use .get because the key itself shouldn't really matter
then i realized you can only .get keys and not values so thats not all that helpful...
you can have multiple keys mapped to the same value but you cant have multiple values mapped to the same key because each key is unique
after thinking about it for a long time i decided to just use an array...
original code if i want to revisit hashmap solution:

** after reading solutions and solving with array method - hashmap solution does something where you increment the count by one, so the index does matter. im gonna try to solve it with hashmap now - the idea being you map each character to the key - then the value represents how many times that appears, so for each character in the string you would check if the map containskey, then increment the value by 1 if it does. then you would pass through the map again for each character in ransomnote - if the value is more than 1 you decrement it by 1 and if the value is 1 you remove it.

-----
(old attempt at hashmap solution)
HashMap<Integer, String> map = new HashMap<>();

for (int i = 0; i < magazine.length(); i++)

{

String s = magazine.charAt(i);

map.put(i, s);

}

  

for (int i = 0; i < ransomNote.length(); i++)

{

String s = ransomNote.charAt(i);

}

----

<h1> Solution </h1>
class Solution {

public boolean canConstruct(String ransomNote, String magazine) {

ArrayList< Character> arr1 = new ArrayList<>();

char[] temp = magazine.toCharArray();

for (char c: temp)

{

arr1.add(c);

}

char[] arr2 = ransomNote.toCharArray();

for (char c: arr2)

{

if (arr1.contains(c))

{

arr1.remove(Character.valueOf(c));

}

else

{

return false;

}

}

return true;

  
  

}

}

** updated solution with hashmap:

class Solution {

public boolean canConstruct(String ransomNote, String magazine) {

HashMap<Character, Integer> map = new HashMap<>();

  

// creating the table

for (int i = 0; i < magazine.length(); i++)

{

char c = magazine.charAt(i);

if (map.containsKey(c))

{

map.put(c, map.get(c) + 1);

}

else

{

map.put(c, 1);

}

}

  

for (int i = 0; i < ransomNote.length(); i++)

{

char c = ransomNote.charAt(i);

if (map.containsKey(c))

{

if (map.get(c) > 1)

{

map.put(c, map.get(c) - 1);

}

else

{

map.remove(c);

}

}

else

{

return false;

}

}

return true;

}

}