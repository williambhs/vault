
**Relevant Tags:**

----

<h1> Overview </h1>
Using two references/variables to keep track of distinct indexes. Useful as it saves both time and space.

**What is a pointer?**
Pointer = reference to an object - in many cases this is just a variable that points to something. 

**When to use two pointers?**
Commonly used when you need to iterate through a data structure 1+ times - having two pointers lets you keep track of each level of the loop, allowing you to process two elements of the loop instead of just one
Common patterns:
1 - two pointers, one moving from the end to the beginning
2 - two pointers, one fast and one slow

These two variants are known as **opposite directional** and **equi-directional**.