
**Relevant Tags:** [[04 - A - O - Two Pointers]]

----

Method used to efficiently solve problems that involve defining a range in the input and then moving the window across to perform some operation - common use cases include finding subarrays with a specific sum, finding the longest substring with unique characters, etc.

Two types of sliding window:

1] Fixed Size - 
-Find the size of the window required
-Compute the result for the window (for example, sum all the values of a window of size 3)
-Use a loop to move the window

2] Changing Size -
-Increase right pointer until condition is true
-Shrink the size of window by changing left pointer when the condition does not match
-Continue increasing right pointer until end of array reached

Identifying sliding window problems - generally require finding a maximum/minimum subarray or substrings that satisfy some specific condition. Many times the size of the subarray is given in the problem.
