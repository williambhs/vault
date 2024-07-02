
**Problem Number: 155
Relevant Tags: [[14 - Medium - J - Min Stack]], [[01 - C - O - Ternary Operator]]
<h1> Problem Description </h1>
Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.

Implement the `MinStack` class:

- `MinStack()` initializes the stack object.
- `void push(int val)` pushes the element `val` onto the stack.
- `void pop()` removes the element on the top of the stack.
- `int top()` gets the top element of the stack.
- `int getMin()` retrieves the minimum element in the stack.

You must implement a solution with `O(1)` time complexity for each function.

**Example 1:**

**Input**
["MinStack","push","push","push","getMin","pop","top","getMin"]
[[],[-2],[0],[-3],[],[],[],[]]

**Output**
[null,null,null,null,-3,null,0,-2]

**Explanation**
MinStack minStack = new MinStack();
minStack.push(-2);
minStack.push(0);
minStack.push(-3);
minStack.getMin(); // return -3
minStack.pop();
minStack.top();    // return 0
minStack.getMin(); // return -2

**Constraints:**

- `-231 <= val <= 231 - 1`
- Methods `pop`, `top` and `getMin` operations will always be called on **non-empty** stacks.
- At most `3 * 104` calls will be made to `push`, `pop`, `top`, and `getMin`.

-----
Use an arraylist - to get min to run in O(1) time, just track the min whenever you add value, check if it's less than the min.

Nevermind - this will let you get the min in some cases, but can't account for popping items off the stack. Instead - create a list/array to track the current minimum as well.
The problem is trying to get a solution that can keep track of the minimum value in constant time instead of O(n) time where you need to loop through the array/list to get the minimum value.

There's a very simple solution just using two stacks - one that keeps track of the minimum value as well as one that performs normal operations.

When you push an element into the stack - check if it's the minimum - if it is push it to the top, if not push the current minimum element of the stack onto the top, since the depth of the stack has increased by one but the minimum remains lower in the stack.
<h1> Solution </h1>
class MinStack {

  

private Stack<Integer> stack;

private Stack<Integer> minStack;

  

public MinStack() {

stack = new Stack<>();

minStack = new Stack<>();

}

public void push(int val) {

stack.push(val);

int min = minStack.empty() ? val : Math.min(minStack.peek(), val);

minStack.push(min);

}

public void pop() {

stack.pop();

minStack.pop();

}

public int top() {

return stack.peek();

}

public int getMin() {

return minStack.peek();

}

}

  

/**

* Your MinStack object will be instantiated and called as such:

* MinStack obj = new MinStack();

* obj.push(val);

* obj.pop();

* int param_3 = obj.top();

* int param_4 = obj.getMin();

*/