
---

Map - a collection that associates keys with values

[[02 - DS - O - Hashmap]]
key/value pair - key can map to one value but multiple keys can map to the same value

two primary classes - hashmap, treemap

hashmap more general purpose whereas treemap stores comparable keys in sorted order

similar declaration as arraylist - 
Map<String, Double> doubleMap = new HashMap<>();

call get method which accepts key as a parameter, returns the value mapped to that key
contains key can check for a key but you can also check if the .get method returns null

map doesn't have iterator - thus you have to use map.keySet, but you ca still use for each loop: for example

for (String str: map.keySet()) 
or
for (int i: map.values())

the first one iterates over every key in a random order (if a hashmap) and the second one iterates every value

treemap vs hashmap:
hashmap faster, but keys aren't stored in any order
treemap slower, can only store comparable data, but keeps keys in sorted order

treemap sorts keys in numeric order - hashmap usually preferred due to performance, as well as its ability to work on data that doesn't have a natural ordering
