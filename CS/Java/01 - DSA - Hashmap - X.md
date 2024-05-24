
**Java Documentation:** [HashMap (Java Platform SE 8 ) (oracle.com)](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html)
**Syntax for initialization:** HashMap<key, value> HashMapName = new HashMap<>(); 
K - type of keys maintained
V - type of mapped values
**Example Initialization:** HashMap<String, Integer> dogTable = new HashMap<>();
**Relevant Tags:** 

-----

A map - set of key value pairs 
Requires importing java.util.HashMap

Use .put to add values to the hashmap - ie. map.put("Dog1", 3);
When printing the hashmap, values are printed in a random order - the map is used to map keys to values and thus doesn't care about how those values are organized.
If a key already exists in a hashmap and you attempt to use the put method to insert the same key, the old value is replaced with the new one.

Similarly - use .get to get values mapped to a certain key - for example, after running the previous command, printing the result of map.get("Dog1") would print 3, the value mapped to the key Dog1.

