**Relevant Tags:**

----

Ternary operator in Java is a shorthand way of performing an if else conditional statement.
The ternary operator is also known as the conditional operator.

The syntax of the ternary operator is as follows:

**var = condition ? val1: val2;**

Var - represents a variable
Condition - represents an expression that evaluates to true or false
val1 - the value that var will be set to if condition
val2 - the value that var will be set to if condition is false
another way to think about it would be: if condition is true, expression, else expression 2.

Basic example:

int a = 10; 
int b = 20; 
int max = (a > b) ? a : b; 
<!-- if a is greater than b, max will be a, otherwise max will be b. -->
System.out.println("The maximum value is " + max);

Useful for straightforward conditional logic. Can also be nested, but reduces readability and should be used with caution.