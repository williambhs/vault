**Relevant Tags:** [[02 - DS - Hashtable - O]], [[02 - DS - Hashmap - O]]

-----
<h1> Overview </h1>
Hashing is the process of making a fixed size output using formulas called hash functions. 
Three main components of hashing:
1 - Key: Anything which is fed as an input in the hash function.
2 - Hash Function: Receives the key and returns the index of an element in an array called a hash table. The index is called the hash index.
3 - Hash Table: a data structure that maps keys to values using a special function called a hash function. 

![[hash img.png]]

**Hash functions** are a fundamental concept in CS - they take an input and return a fixed size string of bytes. The output is called the hash code or hash value. Their purpose is to map data to values which are then used as indexes in hash tables.
Some examples of hash functions include division, multiplication, mid-square, folding, cryptographic, universal, perfect, etc.
All these do is essentially modify the key through some method to place in the hashtable - for example, the division hash function applies mod to the key and then puts it in the table.

However - a problem arises in that sometimes different keys can generate the same hash value. This is known as **collision**. There are two main methods to handle collision.

First - Separate Chaining.
Make each cell a linked list of records that have the same hash function value. Chaining is simple but requires additional memory outside the table.
**write linked list dsa and come back
[Introduction to Hashing - Data Structure and Algorithm Tutorials - GeeksforGeeks](https://www.geeksforgeeks.org/introduction-to-hashing-data-structure-and-algorithm-tutorials/)
