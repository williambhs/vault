
**Relevant Tags:** [[02 - DS - O - HashSet]]

---

Similar to a HashSet in java with a few key differences - each element has to be unique.

Syntax is:
std::set < dt > setName;

or, if using namespace std:

set < dt > setName;

similar to an array or vector you can initialize a set with values:
set < int > mySet = {3, 2, 5, 1};

to put a value in, use .insert(). 
doesn't contain a .contains() method but you can use the .find() method to return an iterator instead - if the iterator points to setName.end() (so if (itr = = setName.end())) that's the equivalent of false - otherwise, the method will return some different value of the iterator not equal to the end meaning the element exists in the set.

to illustrate how this works, you would first create an iterator -
auto itr = mySet.find(target);

then check if it's equal to the end of your set -
if (itr = = mySet.end())

if the function returns true, then it means target isn't in the set, otherwise it is.

you use the .erase() method to remove values from the set.