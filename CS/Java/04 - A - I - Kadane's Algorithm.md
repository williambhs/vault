
**Relevant Tags:** [[04 - A - O - Two Pointers]], [[04 - A - O - Sliding Window]]

----

Useful algorithm used to find some maximum sum in a subarray. The time complexity of Kadane's is O(n) time, which is far more efficient than brute force, which is typically quadratic, or O(n^2) time. 
The way Kadane's works is applying a similar approach where you calculate the current sum of all the elements in the array so far and the max sum. Then, you check the next element of the array to see if you start a new sum or if you append the element to the current sum.

Useful video explaining the algorithm in Java: https://www.youtube.com/watch?v=jnoVtCKECmQ&t=342s

For example, if the input array is:
[ -2, 2, 5, -11, 6]
At arr[0], your max sum and current sum are both -2.
Then, at arr[1], your current sum becomes 2, as the value of arr[1] > arr[0] + arr[1]. Then, you compare the current sum value to the current max sum value - because 2 > -2, your max sum also becomes 2. 
To clarify - the current sum is not actually the sum of all the numbers leading up to arr[i] but rather the largest possible sum up to the current value.
Walking through the rest of the array - at arr[2], you simply add 5, because adding 5 to the current sum, which is 2, makes 7, which is greater than starting a new subarray with element 5.
Thus, current sum becomes 7, and max sum becomes 7 as well.

At arr[3], we want to add -11 to the current sum, which is -4, as 7 - 11 > -11. However, the max sum is not updated, as current sum is now no longer greater than the max sum.
Finally, we add 6 to the current sum at arr[4]. The new current sum becomes -4 + 6 = 2, which is not greater than the maximum sum, and the loop terminates at max sum = 7.
