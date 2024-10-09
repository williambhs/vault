**Relevant Tags: [[01 - C - I - IO (Input Output)]]

----

CPP requires importing libraries similar to python to be able to access many functions - this is called a preprocessor directive which tells the compiler what library you want to use.
An example is 
'#include < iostream >'
The name inside the angle brackets (iostream) is the header, and '#include' is the directive.
Generally include directives appear outside of functions and are typically at the beginning of a file.

In C++ expressions are composed of operands + operators - for example, << is the output operator and >> is the input operator.
Take the statement:
std::cout << "Enter a number: " << std:endl;
for example. 

In C++ every expression produces a result which is usually the value generated by applying an operator to its operands - the result is the value of the left-hand operand, or the value returned by an output operation is the output stream itself, allowing you to chain together output requests.

Returning to the earlier example, it can be stated that it is equivalent to:

(std::cout << "Enter a number: " << std:endl;) << std:endl

->

std::cout << "Enter a number:";
std:: cout << std::endl;

endl is a manipulator - when written to an output stream it creates a newline and flushes the buffer.

The prefix std:: means the names cout and cin come from the standard library namespace - helps programmers avoid collisions as some libraries use the same names, so specifying the namespace helps the program differentiate.

:: is the scope operator - it means we want to use the name cout defined in namespace std.

The input operator is similar to the output operator, taking an istream (inputstream) operand and storing the value in its right hand operand.