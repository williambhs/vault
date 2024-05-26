
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
first medium problem yay
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



progress so far -

class Solution {

    public List<List<String>> groupAnagrams(String[] strs) {

        // initial stuff

        ArrayList<List<String>> arr = new ArrayList<List<String>>();

        HashMap<Character, Integer> map = new HashMap<>();

  

        // converting strs to an arraylist

        ArrayList<String> input = new ArrayList<String>();

        for (String str : strs) {

            input.add(str);

        }

        // ----------------------------------------------

  

        for (int i = 0; i < input.size(); i++) {

            map.clear();

            ArrayList<String> temp = new ArrayList<String>();

            String s = input.get(i);

            temp.add(s);

            input.remove(s);

  

            // making the hashmap

            for (int x = 0; x < s.length(); x++) {

                if (map.containsKey(s)) {

                    map.put(s, map.get(s) + 1);

                } else {

                    map.put(s, x);

                }

            }

  

            // comparing with the rest of the strings

            for (int j = 0; j < input.size(); k++) {

                String comp = input.get(j);

  

                // checking if it's an anagram

                for (int k = 0; k < comp.length(); k++) {

                    char c = comp.charAt(k);

                    if (map.containsKey(c)) {

                        if (map.get(c) > 1) {

                            map.put(c, map.get(c) - 1);

                        } else {

                            map.remove(c);

                        }

                    } else {

                        return;

                    }

                }

                temp.add(comp);

                input.remove(comp);

            }

            arr.add(temp);

  

        }

        return arr;

    }

}
<h1> Solution </h1>
