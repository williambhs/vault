
**Relevant Tags:** [[02 - DS - O - Stack]]

-----

Special data structure used in algorithmic problem solving that involves a stack that maintains elements in either increasing or decreasing order - commonly used to efficiently solve problems that involve finding the next greater or smaller element.

**Monotonically increasing stack** - stack where elements are placed in increasing order from bottom to top. For example: 1, 3, 10, 15, 17 would be a monotonically increasing stack with 17 on the top and 1 at the bottom. 

To achieve a monotonic increasing stack:
-initialize empty stack
-iterate through the elements, for each element 
-while stack isn't empty and top of stack > current element, keep popping elements off the stack
-push the current element onto the stack

**Monotonically decreasing stack** is the opposite - for example: 17, 15, 10, 3, 1 would be the opposite of the increasing stack, with 1 at the top and 17 at the bottom.

To achieve monotonic decreasing stack, you do the same but check if the top of the stack is less than the current element instead of greater

Important to note that monotonic stacks operate in linear/O(n) time