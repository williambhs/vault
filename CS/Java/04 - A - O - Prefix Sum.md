
**Relevant Tags:**

----


Also referred to as cumulative sum - technique used to calculate the sum of all elements in an array up to a certain index.

The basic idea is to precompute the sum of all element sup to each index and then use precomputed sums to quickly calculate the sum of subarrays.

To create a prefix sum array:
1 - create a new array with the same length as the original array
2 - initialize element 0 to the element 0 of the original array, as the first element will be the same
3 - iterate over the new array starting from the first element, setting it equal to the element in the old array + the element in the prefix sum array - 1: that way every next element is equal to the sum of all previous elements + the element in the original array

To find the sum of a sub array, we use the formula Sum(i, j) = prefixSum[j] - prefixSum[i - 1].
For example, if we have array [1, 2, 3, 4, 5] and we want the sum of everything from index 1 (assuming the array is zero indexed, so starting from 2) to 4 (ending at 5), here is a visualization of the initial array vs the prefix sum array:

original: [1, 2, 3, 4, 5, 6]
prefix sum: [1, 3, 6, 10, 15, 21]

The sum of each value from index 1-> 4 would be 2 + 3 + 4 + 5 = 14. 
To calculate this using the prefix sum, we take the value at index j in the prefix sum array, which is 15. Then we subtract prefixSum[i-1] - since i in this case is 1, we subtract prefixSum[0] which is 1. 15 - 1 = 14.


Here's a quick dry-run of what implementation looks like in Java.
public class Main {
    public static void main(String[] args) {
        int[] nums = new int[] { 1, 2, 3, 4, 5 };
        int[] pSum = new int[nums.length];
        pSum[0] = nums[0];
        for (int i = 1; i < nums.length; i++) {
            pSum[i] = nums[i] + pSum[i - 1];
        }
        for (int num : pSum) {
            System.out.println(num);
        }
    }
}

**USE CASES:**
Range Sum queries
Finding subarrays with given sum
Number of subarrays with sum <= k
Max subarray sum
Binary array subarray sums
Equal frequency subarrays
Prefix sum in 2d arrays
Some sliding window problems