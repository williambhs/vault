
**Java Documentation:** https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#:~:text=The%20String%20class%20represents%20character,changed%20after%20they%20are%20created.

**Syntax for initialization:** 
*For String Literals:*
String stringName = "stringText";
*Using new keyword*:
String stringName = new String("stringText");

**Example Initialization:** 
*For String Literals:*
String str = "bruh";
*Using new keyword*:
String str = new String("bruh");

**Relevant Tags:** 

-----

Strings are sequences of characters. In Java, string objects are immutable which means they are constant and thus cannot be changed after creation. It is important to note that strings are non-primitive data types and refer to an object.

As seen above - two ways to create a string, using string literals and using the new keyword. When you use a string literal, Java automatically creates a string object with that value - the value is automatically interned which means if more than one string literal with the same value is used, they will reference the same string object in memory. 

This means if you use == on string literals it will return true, but not if you use the new keyword. If using the new keyword use .equals to compare strings.

**Useful/Relevant Methods:** 

.toCharArray() - converts a string into an array of characters

.charAt() - substring but better

.contains(CharSequence s) - returns true if the string contains s

.endsWith(String suffix) 
.equals(Object anObject)
.indexOf() - all self explanatory
.lastIndexOf()

.indexOf(String str, int index), .lastIndexOf(String str, int index- returns the index of the first occurrence of str in the string starting from the index specified, or in the case of lastIndexOf, will search backwards starting from the index

.length()
.substring() - ...csa means you know what this does.

.toUpperCase()
.toLowerCase()

**IMPORTANT!!**
Do NOT ever concatenate strings within loops - instead use stringbuilder. This is much more memory efficient as strings objects are immutable which means in loops a string object is created each time if you concatenate. Stringbuilder, however is mutable - that means instead of :

String result = "";
(in loop)
result += i;

you should do:

StringBuilder str = new StringBuilder();
(in loop)
str.append(i);
result = str.toString();


Stringbuilder also has a built in reverse method: documentation is here
[StringBuilder (Java Platform SE 8 ) (oracle.com)](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html)
