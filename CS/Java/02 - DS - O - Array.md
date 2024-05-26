
**Java Documentation:** https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html

**Syntax for initialization:** ArrayType[] ArrayName = new ArrayType[arraylength];

**Example Initialization:** int[] nums = new int[4];
*note that you can initialize an array with only the first half - for example "int[] arr;", this initializes a reference variable but does not actually create the array itself. However, attempting to use it before initializing the array itself will cause a null pointer exception.*

**Relevant Tags:** 

-----

Note: requires importing java.util.Arrays

I mean... it's an array. Everyone learned this for CSA.
An array stores a collection of elements in a contiguous memory. This means consecutive blocks of memory allocated to user processes. (what does that even mean? maybe I'll find out one day. see - https://stackoverflow.com/questions/4059363/what-is-a-contiguous-memory-block)
Each item in an array is indexed starting with 0. 
Some important things to note are that arrays are foundational to implement many other data structures, ie. queues and stacks. Arrays can also be used to build binary search trees and balanced binary trees.

In Java, arrays are often used to store data of the same type, implement matrices/tables, sorting/searching, and image processing. 

Some advantages of arrays are their ease of implementation, memory efficiency, fast data retrieval, and versatility.
On the other hand, arrays suffer from having a fixed size, large arrays might result in the system running out of memory, and inserting/deleting an element from an array can be potentially inefficient because all elements must be shifted to accommodate any changes. 

Some useful array methods include:

Arrays.sort() - sorts the array into ascending numerical order, or alphabetical order for strings

Arrays.fill(Object[] a, Object val) - pretty self explanatory. Fills the array with the value specified.

Arrays.equals(Object[] a, Object[] b) - also pretty self explanatory. Returns true if the given two arrays are equivalent.

Arrays.copyOf(Object[] a, int val) - creates a new array with contents of a and length val. If the copy has a greater length than the original, the 

Arrays.asList(Object[] a) - converts the array into a list. Note that this does not work with wrapper classes like Integers because they're primitives as opposed to objects. This means .asList will work on strings, but not ints. 
Here is an example how you would use asList:

public boolean containsDuplicate(String[] arr) 
{
     ArrayList< String > temp = new ArrayList<>(Arrays.asList(arr));
}