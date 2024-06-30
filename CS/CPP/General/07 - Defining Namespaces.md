**Relevant Tags:** [[02 - Header Files]]

----

User-defined namespaces allow you to create your own namespace using the namespace keyword - for example:

namespace MyNameSpace {
}

note that the name of the namespace is capitalized - C++20 standard documents use this style, as well as the C++ core guidelines.
ultimately, however, both capitalized and uncapitalized styles are acceptable.

then, simply put the function you want inside the namespace and call it with the name of the namespace. For example, if MyNameSpace had function foo that took an int parameter, you would call it using MyNameSpace:: foo(some number here);

note that now that you have defined a namespace, you can't call foo(some number) because foo is no longer in the global namespace, unless you happen to have another function called foo in the global namespace.

however - if an identifier is used in a namespace, the compiler will try to find a matching declaration in the same namespace first. That means if you define namespace foo with a print method, and then create a second method that calls print, the compiler will use the print defined in your foo namespace over the global print function even though you haven't used the scope operator. In these cases, you can use the scope operator without specifying a name space to refer to the global namespace - ::print(). 

for identifiers inside namespaces, forward declarations also have to be inside the namespace in header files (both in the .cpp file and the header file itself)

C++ has namespace aliases - using the = operator you can do namespace X = Y, and now every instance of Y refers to X. Useful when dealing with nested namespaces so you don't have to type the entire thing out.