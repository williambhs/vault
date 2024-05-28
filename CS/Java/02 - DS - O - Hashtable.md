
**Java Documentation:** https://docs.oracle.com/javase/8/docs/api/java/util/Hashtable.html

**Syntax for initialization:** Hashtable<key, value> 
HashtableName = new Hashtable<>(); 
K - type of keys maintained
V - type of mapped values

**Example Initialization:** Hashtable<String, Integer> dogTable = new Hashtable<>();

**Relevant Tags:** [[02 - DS - O - HashMap]], [[01 - C - X - Thread Safety]]

-----

Considered a Java legacy class - functionally identical to a Hashmap except a Hashmap is usually more efficient as threads ([[01 - C - X - Thread Safety]]) are not synchronized. The Hashtable class is still available if one needs a synchronized table - however HashMap also allows a null key and multiple null values, and ConcurrentHashMap from the java.util.concurrent package can be used as a thread-safe alternative to Hashtable.