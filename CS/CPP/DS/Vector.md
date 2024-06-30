
**Relevant Tags:** [[02 - DS - O - ArrayList]]

----

Basically Java Arraylists - dynamic arrays that can resize themselves as part of the standard library.

Syntax is:
std::vector< dataType > vectorName

if using std, you can skip the first part:

vector< datatype > vectorName;

Three types of initialization:

1 - using list: pass a list of elements into the vector constructor
vector < int > v({v1, v2, v3});

2 - initialize every element with the same value (equivalent of arrays.fill in java)
vector < int > v(size, value);

for example - vector < int > v(10, 0) creates a vector with size 10 populated with 10 0's/

3 - initialization from another vector:
vector < int > name(v);

(assume v is the name of a different vector)