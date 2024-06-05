**Relevant Tags:**

---- 

<h1> Overview </h1>

To determine an algorithms run time - asymptotic notation
Also referred to as an algorithm's growth rate and describes what happens to the algorithms run time as the input size changes

**Big O Notation**
Measured in terms of O order - O(n) -> O(logn) -> O(n^2)
The most widely used notation for asymptotic analysis and specifies the upper bound of a function, or the worst-case/maximum runtime required by an algorithm

**Big Omega Notation**
The opposite of Big O - instead measures the best case or floor growth rate, giving a lower bound on the growth rate of an algorithms runtime

**Big Theta Notation**
The best of worst case, or average runtime of an algorithm

**Space Complexity**
The total amount of memory space used by an algorithm - not to be confused with auxiliary space, which is extra space
Auxiliary space + space use by input values = space complexity
Better algorithms should have a low level of space complexity - less space = faster execution time


<h2> Distinguishing between time complexities: </h2>
**Constant Time - O(1)**
An algorithm has constant time when the runtime is not dependent on the input size - thus, if for any array, the runtime is 1 unit of time, the function would be considered running in constant time.

**Linear Time - O(n)**
Algorithms run in linear time when the running time increases linearly with the input length - for example, if the length of the input doubles, if the number of operations doubles, the algorithm runs in linear time.

**Logarithmic Time - O(log n)**
Algorithms have a logarithmic time complexity when the size of the input data is reduced in each operation - in other words the number of operations are reduced as the input size increases. For example - in a binary search, the size of the input is halved with each additional operation. Thus, logarithmic time is faster than linear time.

**Quadratic Time - O(n^2)**
An algorithm runs in quadratic time when the runtime increases nonlinearly with input length - generally refers to loops within loops where each loop takes O(n) time, resulting in O(n) * O(n) = O(n^2) time.


