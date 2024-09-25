
**Relevant Tags:** [[02 - DS - O - Hashmap]], [[Pair]]

---
Basically just a Java hashmap - think of it as an arraylist or vector of pairs.
Syntax is
map< dt1, dt2> mapname;

Populating a map in c++ differs from Java. After creating a map, to add a value you use the syntax:

map[key] = value;

for example, if you wanted to add a value to a map of chars to ints called map, you would do:

map['c'] = 12;

this would map key c to value 12 in the map.

to populate the map during its initialization, the syntax is as follows:

map<char, int> = {
{'a' , 0},
{'b', 0},
{'c', 0}
};
note the semicolon after the second curly brace as well as commas after the pairs.

another way to put values in the map is directly using pairs - for example a pair of type char int initialized with
pair p1('c', 12);
could be inserted using the insert method:

map.insert(p1);

in a map, keys are default initialized to 0. this way an efficient way to create a map with characters mapped to the frequency of how many times they appear in a string is:

for (char c: str) {
	mp[c]++;
}

this will either default initialize mp[c] to 0 and then increment it to 1, or increment the value already at mp[c] to it's frequency + 1.

Some useful methods include:
.size()
.clear()
.insert() - explained above
.erase()

