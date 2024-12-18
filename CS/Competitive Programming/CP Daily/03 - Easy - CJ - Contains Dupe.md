
**Problem Number: 217**
**Relevant Tags:** [[02 - DS - O - HashSet]]
<h1> Problem Description </h1>
Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

**Example 1:**

**Input:** nums = [1,2,3,1]
**Output:** true

**Example 2:**

**Input:** nums = [1,2,3,4]
**Output:** false

**Example 3:**

**Input:** nums = [1,1,1,3,3,4,3,2,4,2]
**Output:** true

**Constraints:**

- `1 <= nums.length <= 105`
- `-109 <= nums[i] <= 109`

-----
seems really easy, on neetcode 150 so might as well do it.
want to get practice with hashmaps so going to solve with a hashmap. 
containsKey makes this very trivial. just create a map of < Integer, Integer >, the key is arr[i] and the value is i, if it containsKeythen return true otherwise continue looping and return false at the end.

Apparently there is a more efficient way to solve with hashset over hashmap - will look into that later
** update: solved with hashset
<h1> Solution </h1>
class Solution {

public boolean containsDuplicate(int[] nums) {

HashMap<Integer, Integer> map = new HashMap<>();

for (int i = 0; i < nums.length; i++)

{

int num = nums[i];

if (map.containsKey(num)) return true;

else

{

map.put(num, i);

}

}

return false;

}

}

----
Hashset solution: 
class Solution {

public boolean containsDuplicate(int[] nums) {

ArrayList<Integer> temp = new ArrayList<Integer>();

for (int num: nums)

{

temp.add(num);

}

HashSet<Integer > set = new HashSet<>(temp);

if (set.size() == nums.length) return false;

return true;

}

}

C++ Solution

```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        set<int> s;
        for (int i: nums) {
            s.insert(i);
        }
        return !(s.size() == nums.size());
    }
};
```