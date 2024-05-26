
**Java Documentation:** [ArrayList (Java Platform SE 8 ) (oracle.com)](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html)

**Syntax for initialization:** ArrayList< ArrayListType > ArrayListName = new ArrayList< ArrayListType >();

**Example Initialization:** ArrayList< Integer > arr = new ArrayList< Integer >();

**Relevant Tags:** [[02 - DS - O - Array]], [[02 - DS - X - Linked List]]

-----

ArrayList is a Java class implemented with the list interface - most of the advantages compared to arrays were explained in CSA but for a quick refresher:

ArrayLists are dynamic - thus you don't have to specify the size when creating it. The size automatically increases and decreases when adding/removing items.

Generally much more convenient than arrays - however arrays should still be used when you know the size of data beforehand as they're more memory efficient

**Useful Methods:**
just check the documentation lmao

.add()
.addAll() - example implementation would be arrayList1.addAll(arrayList2);
.remove()
.contains()
.clear()
.isEmpty()
.size()
.set()
.sort() - note this operation takes o log n time
.toArray() - returns an array containing all elements - works with objects like strings, but not primitives like ints (similarly to the asList() method for arrays - [[02 - DS - O - Array]])
Example implementation 
trimToSize() - this is kinda useless, but if for some reason since you can specify an initial capacity, you can trim the arraylist of all the empty values
