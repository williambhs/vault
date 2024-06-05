
**Java Documentation:** https://docs.oracle.com/javase%2F8%2Fdocs%2Fapi%2F%2F/java/util/Stack.html

**Syntax for initialization:** Stack< Datatype > = new Stack<>();

**Example Initialization:** Stack< Integer > = new Stack<>();

**Relevant Tags:** [[01 - C - X - LIFO]]

-----

Note: Requires importing java.util.Stack

A stack is a data structure that follows the Last In First Out principle - the most recently added item is the first one to be removed.
Stacks only have five methods - listed below:
![[Stack Methods.png]]

Two types of stacks:
1 - fixed size stack - can't grow or shrink. If an element is added to a fixed size stack that will cause it to overflow, it will cause an error. Similarly, if the stack is empty and an attempt is made to remove an element, an underflow error will be thrown.
2 - dynamic size stack - can grow or shrink. When the stack is full, it will automatically increase in size to allow for the new element, and when empty, the size of the stack will decrease. Implemented using a linked list.

Stacks are useful when the computation has to go back in reverse order since they're a LIFO data structure, meaning the element inserted last is accessed first. For example, in reversing a string, a stack might be useful if you put all letters in a stack and pop them out - because the stack is in LIFO order, the letters will be returned in reverse.

Important to note that when the pop method is run, it will not only return a value but **also** pop the item off the stack. For example, int b = stack.pop() will not only return an int value but also pop the top value off the stack.