
**Problem Number: 125
Relevant Tags: [[03 - DT - O - Character]]
<h1> Problem Description </h1>
A phrase is a **palindrome** if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string `s`, return `true` _if it is a **palindrome**, or_ `false` _otherwise_.

**Example 1:**

**Input:** s = "A man, a plan, a canal: Panama"
**Output:** true
**Explanation:** "amanaplanacanalpanama" is a palindrome.

**Example 2:**

**Input:** s = "race a car"
**Output:** false
**Explanation:** "raceacar" is not a palindrome.

**Example 3:**

**Input:** s = " "
**Output:** true
**Explanation:** s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.

**Constraints:**

- `1 <= s.length <= 2 * 105`
- `s` consists only of printable ASCII characters.

-----
I need a break after being humbled by medium problems...
actually harder than I originally thought
first part of the problem seems the hardest, which is just removing everything that isn't an alpha numerical character - gonna just remove everything that's not within a certain ascii value
alright nevermind there's a method that just does it for you...
** note - come back and solve with two pointer later

<h1> Solution </h1>
```
class Solution {

    public boolean isPalindrome(String s) {

  

        ArrayList<Character> temp = new ArrayList<Character>();

        char[] arr = s.toCharArray();

  

        for (char c: arr)

        {

            if (Character.isLetterOrDigit(c)) temp.add(c);

        }

        String s1 = "";

        for (char c: temp) {

            s1 += c;

        }

        s1 = s1.toLowerCase();

        String s2 = "";

        for (int i = s1.length() - 1; i >= 0; i--)

        {

            s2 += s1.charAt(i);

        }

        if (s1.equals(s2)) return true;

        return false;

    }

}
```