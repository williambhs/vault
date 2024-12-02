[[02 - DS - X - Linked List]]

----
Arrays are stored in one block of memory which makes it easy to locate a single element in the array

Problem with array - difficult to insert values in or remove values from the middle w/ out shifting the other values, as well as being difficult to enlarge the size of the structure without constructing a new array with a larger capacity.

Where arrays are weak - linked lists are strong. Easy to insert/delete values in the middle of a linked list as well as changing its size.

Node - like a building block. A recursive data structure - defined in terms of itself.

to create a ListNode use new ListNode();
make sure you keep the reference to the front to be able to traverse the list.

can't just say "ListNode list" without creating a new object because you have created a variable list, however it doesn't point to a listnode yet.

