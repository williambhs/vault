
**Relevant Tags:** [[Map]]

----

Useful way to combine two values that are different data types.
Syntax is:

pair < dt1, dt2 > pairName

to get the value, use .first and .second. 
.first gets the first value, .second gets the second - for example

pair < char, int > p1;
p1.first = 'c';
p2.second = 12;

if you were to cout p1.first you would get c, and if you were to cout p2.second you would get 12.

to initialize the pair in one line, for the same pair you would do:

pair < char, int > p1 ('c', 12);

in versions of c++ 17 or later, you don't actually need to specify char, int - you can just do:

pair p1('c', 12);
or
pair p1 = {'c', 12};

and it will compile because the compiler deduces p1 should be of type < char, int >.
a very similar method to achieve the same function is provided in the pair class - 

p1 = make_pair('c', 12);

you can also initialize a pair with another pair to create a copy - for example

pair p2(p1);

pair also contains a swap method - syntax is:
pair1.swap(pair2);
(swaps pair1.first with pair2.first, pair1.second with pair2.second)

operators like "= =" can be used with pair as well. using < and > values will first compare the first elements, then the second if and only if the first elements are equal. that means it will prioritize the .first of both pairs before moving to the second value.

