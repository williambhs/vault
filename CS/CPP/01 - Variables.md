
----
Similar to how they work in Java. To initialize, syntax is something like
int a;
or int a, b;
^ this initializes two ints, a and b but is generally seen as bad practice. Note you cannot do:
int a, int b;
or declare two different types such as:
int a, string b;

it's ok to initialize a variable if you know you will assign it a value before you use it.

**Different types of initialization:**

**1 - default initialization:**
int a;
std::string s;

**2 - copy initialization:**
int a = 5;
std::string s = "Hello";

copies the value on the right hand side into the variable on the left

**3 - direct initialization:**
int a(5);
std::string s("Hello);

**4 - list initialization:**
int a{42};
std::string s{Hello};
OR
int a = {42};
*Note that:* std::string s = {"Hello"};
is not valid because of the way constructors are defined for strings.

Two types of list initialization, direct and copy - direct (the first one) is usually preferred. Modern C++ commonly uses list initialization as the compiler will error if you try to narrow a conversion, whereas other forms of variable initialization will simply truncate. 

**5 - value initialization:**
int a{};

in most cases initializes a variable to some default value (usually 0 or empty) - use value initialization if the value is temporary and will be replaced. You should use this over default initialization.

----
Note that it is also possible to initialize multiple variables on the same line - just like you can do:
int a, b;
you can similarly do
int a = 5, b = 6;
and you can similarly NOT do 
int a, b = 5;
note that this will run, however it would be the equivalent of:
int a;
int b = 5;
as opposed to:
int a = 5;
int b = 5;

sometimes the compiler will error if a variable is not used - thus use the "[[maybe_unused]]" tag which tells the compiler we're ok with a variable not being used.



