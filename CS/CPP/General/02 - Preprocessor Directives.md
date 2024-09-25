
----

Preprocessor directives refer to lines of code that start with a # and end with a newline, not a semicolon.

You can use # define to create a macro. There are two ways to define object-like macros:

1 - # define NAME
2 - # define NAME text

these should follow the same naming conventions as previously discussed - however note that macro names are typically all upper case and separated by underscores.

for the second example - the preprocessor will simply replace all instances of NAME with text - for example:

std:: cout << "hello, " << NAME << ".";
->
std:: cout << "hello, " << text << ".";

On the other hand, without substitution text, the macro simply removes occurrences of NAME.

Conditional compilation preprocessor directives give conditions for when something will/won't compile.

some examples include, # ifdef (or # if defined), and # ifndef (or # if !defined)
For the alternative syntax, parenthesis are used - for example # ifdef HELLO becomes # if defined(HELLO) and # ifndef HELLO becomes # if !defined(HELLO)

make sure to wrap with an # endif statement.