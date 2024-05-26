
**Java Documentation:** https://docs.oracle.com/javase/8/docs/api/java/util/HashSet.html

**Syntax for initialization:** HashSet < Type > HashSetName = new HashSet<>();

**Example Initialization:** HashSet < Integer > set = new HashSet<>()

**Relevant Tags:** 

----

Note: Requires importing java.util.HashSet

Not to be confused with a HashMap - implements the set interface and is used to create a collection containing no duplicate elements. 

Hashsets are commonly used when you need a collection that doesn't have duplicates as well as when you don't need to maintain the order of elements.

A quick way to remove all the duplicates from a list or array is using the addAll method to a hashset, or, alternatively, passing the list into the hashset constructor - for example if your array was called list, you could initialize a hashset using HashSet< String > set = new HashSet<>(list), which would create a new hashset called set with all the elements of list, just without duplicates. However, it is important to note the order of elements will not be preserved if you convert the set back into a list.
Also - this does not work with arrays. You would first need to convert the array into a list since you need to pass a member of the Java Collections Framework into the constructor for it to be valid - lists implement the Java collection framework but arrays do not.

There are only a few methods for hashset so I'll just paste the screenshot from the oracle documentation.
![[HashSet method summary.png]]