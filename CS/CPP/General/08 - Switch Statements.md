
----
Different way to write long if else chains - syntax is:
switch(variable)
{
case x:
	statement 0;
case y:
	statement 1;
	statement 2;
default:
	statement;
}

Note that there are no curly braces between statements.
If the variable equals x, statement 0 is executed - if equal to y, statements 1 and 2 are executed. The default case is optional, but if included will be executed if the variable inside switch is not equal to any other case.

Conventionally, cases are not indented and the default case is placed last in the block. A break statement is usually used after cases to break out of the block but not the function. If you don't break, execution overflows into other statements. This is referred to as fallthrough. If you want intentional fallthrough, you can use '[ [ fallthrough ] ]'. 