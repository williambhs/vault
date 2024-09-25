
**Relevant Tags:**
**Documentation:** https://docs.oracle.com/javase/8/docs/api/java/math/BigInteger.html

----
Biginteger is a **class** used for math ops with large int calculations outside the limit for primitive data types - thus helpful in CP

Example initialization:
int a = 54;
BigInteger num = BigInteger.valueOf(a);

for strings:
String str = "54"
BigInteger num = new BigInteger(str);

Performing mathematical operations on BigIntegers can be done with methods as opposed to normal integer addition/subtraction - for example, if you have two bigintegers A and B, to add them you would do
A.add(B);

All these functions take BigInteger as an argument and thus you must convert strings, ints, etc. to BigIntegers if you want to perform arithmetic operations on them.

To turn bigints into ints/strings use .intValue() and toString() respectively.

int x = num.intValue();
String str = num.toString();

for equality, similar to strings, use .equals() as opposed to two equals signs.
To compare, use compareTo - compare to returns a value of -1 (less than), 0 (equal), or 1 (greater than) - thus to replicate an expression like:

if (a < b)
-->
if (A.compareTo(B) < 0)

similarly, 

if (a > b)
becomes
if (A.compareTo(B) > 0)



