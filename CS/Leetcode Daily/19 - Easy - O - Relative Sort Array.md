
**Problem Number: 1122
Relevant Tags: [[02 - DS - O - ArrayList]], [[02 - DS - O - Array]]
<h1> Problem Description </h1>

Given two arrays `arr1` and `arr2`, the elements of `arr2` are distinct, and all elements in `arr2` are also in `arr1`.

Sort the elements of `arr1` such that the relative ordering of items in `arr1` are the same as in `arr2`. Elements that do not appear in `arr2` should be placed at the end of `arr1` in **ascending** order.

**Example 1:**

**Input:** arr1 = [2,3,1,3,2,4,6,7,9,2,19], arr2 = [2,1,4,3,9,6]
**Output:** [2,2,2,1,4,3,3,9,6,7,19]

**Example 2:**

**Input:** arr1 = [28,6,22,8,44,17], arr2 = [22,28,8,6]
**Output:** [22,28,8,6,17,44]

**Constraints:**

- `1 <= arr1.length, arr2.length <= 1000`
- `0 <= arr1[i], arr2[i] <= 1000`
- All the elements of `arr2` are **distinct**.
- Each `arr2[i]` is in `arr1`.
-----
Create hashmap, arr called ans - first put all the elements of arr1 into the hashmap with getordefault. Then iterate through arr2 - if arr2[i] contains the value, or if the value mapped to the key is >= 1, subtract 1 and change ans[i] to the key.
If the value mapped to the key is 0 remove it from the map.
The values left in the map at the end will be the extra numbers - for each value add it to a new array using a loop (you add each key value times)
Finally:
1 - initialize a new counter variable that starts at 0
2 - start i at arr2.length and change ans[i] to the new arr[counter] and increment the counter variable by 1

Returning ans should return the correct answer
Needed to make some slight changes but that's the gist of it.
<h1> Solution </h1>
class Solution {

    public int[] relativeSortArray(int[] arr1, int[] arr2) {

        HashMap<Integer, Integer> map = new HashMap<>();

        ArrayList<Integer> temp = new ArrayList<Integer>();

        int[] ans = new int[arr1.length];

  

        // creating map

        for (int i = 0; i < arr1.length; i++) {

            map.put(arr1[i], map.getOrDefault(arr1[i], 0) + 1);

        }

  

        for (int i = 0; i < arr2.length; i++) {

            if (map.containsKey(arr2[i])) {

                for (int j = 0; j < map.get(arr2[i]); j++) {

                    temp.add(arr2[i]);

                }

                map.remove(arr2[i]);

            }

        }

  

        // populating answer

        for (int i = 0; i < temp.size(); i++) {

            ans[i] = temp.get(i);

        }

        int idx = temp.size();

        temp.clear();

  

        for (int key: map.keySet()) {

            for (int i = 0; i < map.get(key); i++) {

                temp.add(key);

            }

        }

        Collections.sort(temp);

  

        int counter = 0;

        for (int i = idx; i < temp.size() + idx; i++) {

            ans[i] = temp.get(counter);

            counter++;

        }

  

        return ans;

    }

}