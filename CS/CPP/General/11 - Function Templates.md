
----

C++ allows you to make function templates for one or more overloaded functions. Useful as it allows you to make functions that work with different data types.

To create a function template, the syntax is:

template < typename T >
T templateName(T parameter, T parameter 2)

An example of a function template used to return the max of two values would be:

template < typename T >
T max(T x, T y)
{
	return ( x < y ) ? y : x;
}

To use this function in a program, the syntax would be max< int >(arg1, arg2).
The data type in between the angled brackets will replace all instances of T in the template.
Alternatively, because it's rare that you have both a matching non-template function and a function template, you can actually just call it like a normal function - for example max(1, 2) and the program will compile.