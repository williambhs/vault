
**Problem Number: 13
Relevant Tags: [[02 - DS - O - HashMap]], [[Map]]
<h1> Problem Description </h1>
Roman numerals are represented by seven different symbols: `I`, `V`, `X`, `L`, `C`, `D` and `M`.

**Symbol**       **Value**
I             1
V             5
X             10
L             50
C             100
D             500
M             1000

For example, `2` is written as `II` in Roman numeral, just two ones added together. `12` is written as `XII`, which is simply `X + II`. The number `27` is written as `XXVII`, which is `XX + V + II`.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not `IIII`. Instead, the number four is written as `IV`. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as `IX`. There are six instances where subtraction is used:

- `I` can be placed before `V` (5) and `X` (10) to make 4 and 9. 
- `X` can be placed before `L` (50) and `C` (100) to make 40 and 90. 
- `C` can be placed before `D` (500) and `M` (1000) to make 400 and 900.

Given a roman numeral, convert it to an integer.

-----
Seems relatively simple - first map each string I-M to its corresponding value on a hashmap, then use substring to pull stuff out of the string -> use map

After creating the code - seems to be working except for the edge cases - trying to think of how to handle them
One way could be to check if the letter is V, L, or D - if it is then check if the letter before is one of the other corresponding letters, if yes, you subtract that number and then add whatever the exception is, for example if the letter is a V and the letter before is an I, you would subtract I

<h1> Solution </h1>
class Solution {

    public int romanToInt(String s) {

        int num = 0;

  

        // mapping numerals to vals

        HashMap<String, Integer> map = new HashMap<>();

        map.put("I", 1);

        map.put("V", 5);

        map.put("X", 10);

        map.put("L", 50);

        map.put("C", 100);

        map.put("D", 500);

        map.put("M", 1000);

  

        // making the loop

        for (int i = 0; i < s.length(); i++)

        {

            String key = s.substring(i, i + 1);

            // manually handling every edgecase pepega

            if (i != 0)

            {

                if (key.equals("V") || key.equals("X"))

                {

                    if (s.substring(i-1, i).equals("I"))

                    {

                        num -= (map.get(s.substring(i-1, i))) * 2;

                    }

                }

                if (key.equals("L") || key.equals("C"))

                {

                    if (s.substring(i-1, i).equals("X"))

                    {

                        num -= (map.get(s.substring(i-1, i))) * 2;

                    }

                }

                if (key.equals("D") || key.equals("M"))

                {

                    if (s.substring(i-1, i).equals("C"))

                    {

                        num -= (map.get(s.substring(i-1, i))) * 2;

                    }

                }

            }

  

            num += map.get(key);

        }

        return num;

    }

}

----
C++ Solution

```cpp
class Solution {
public:
    int romanToInt(string s) {
        map<char, int> mp;
        mp['I'] = 1;
        mp['V'] = 5;
        mp['X'] = 10;
        mp['L'] = 50;
        mp['C'] = 100;
        mp['D'] = 500;
        mp['M'] = 1000;
        
        int ans = mp[s[0]];

        for (int i = 1; i < s.length(); ++i) {
            char c = s[i];
            if (mp[c] > mp[s[i-1]]) ans -= 2 * mp[s[i-1]];
            ans += mp[c];
        }
        return ans;
    }
};
```