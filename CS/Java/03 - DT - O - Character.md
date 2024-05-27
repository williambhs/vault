
**Java Documentation:** [Character (Java Platform SE 8 ) (oracle.com)](https://docs.oracle.com/javase/8/docs/api/java/lang/Character.html)

**Syntax for initialization:** char name = 'character';

**Example Initialization:** char c = 'hello';

**Relevant Tags:** [[[02 - DT - X - Primitives]]]

-----

Character is the wrapper class for char, used to store a single character, which is the main distinction between chars and strings.

There isn't much information on the chars online but they're a must-know to be able to solve LC problems efficiently. 
When solving LC problems and working with chars, to convert character arrays to strings you can  create a new String using the String constructor - for example String str = new String(charArray) if you had an array of characters called charArray. Note that you **cannot** use string literals if you want to preserve the characters in the character array - doing this will instead concatenate the charArray with the toString method called on it which is distinct.

**Other Relevant Methods:**

.compare(char x, char y) - compares two values numerically - this method might not do what you expect it to. It's static and returns the value of the first char minus the second character. For example - Character.compare(3, 7) would return 3 - 7 = -4. It can also be used to compare things like letters to numbers, ie. Character.compare(a, 3) would produce 94 (97-3) as the unicode value of a is 97, and the unicode value of 3 is 3.

.compareTo(Character c) - the same except not static.

.toUpperCase()
.toLowerCase()

.equals()

.isLetterorDigit() - this method is static and can be used to check if a character is alphanumeric. Returns a boolean - example usage would be Character.isLetterorDigit('A') would return true.

A useful trick for getting the unicode value of a character is by casting it to an int - for example:
char c = 'A'
int val = (int) c;
val will be equivalent to the unicode value of 'A', which is 65.
![[Java Unicode Visual.png]]
Useful visual - dec represents the unicode value.