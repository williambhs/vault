
**Problem Number: 232
Relevant Tags: [[02 - DS - O - Stack]]
<h1> Problem Description </h1>
Implement a first in first out (FIFO) queue using only two stacks. The implemented queue should support all the functions of a normal queue (`push`, `peek`, `pop`, and `empty`).

Implement the `MyQueue` class:

- `void push(int x)` Pushes element x to the back of the queue.
- `int pop()` Removes the element from the front of the queue and returns it.
- `int peek()` Returns the element at the front of the queue.
- `boolean empty()` Returns `true` if the queue is empty, `false` otherwise.

**Notes:**

- You must use **only** standard operations of a stack, which means only `push to top`, `peek/pop from top`, `size`, and `is empty` operations are valid.
- Depending on your language, the stack may not be supported natively. You may simulate a stack using a list or deque (double-ended queue) as long as you use only a stack's standard operations.

**Example 1:**

**Input**
["MyQueue", "push", "push", "peek", "pop", "empty"]
[[], [1], [2], [], [], []]
**Output**
[null, null, null, 1, 1, false]

**Explanation**
MyQueue myQueue = new MyQueue();
myQueue.push(1); // queue is: [1]
myQueue.push(2); // queue is: [1, 2] (leftmost is front of the queue)
myQueue.peek(); // return 1
myQueue.pop(); // return 1, queue is [2]
myQueue.empty(); // return false

**Constraints:**

- `1 <= x <= 9`
- At most `100` calls will be made to `push`, `pop`, `peek`, and `empty`.
- All the calls to `pop` and `peek` are valid.

**Follow-up:** Can you implement the queue such that each operation is **[amortized](https://en.wikipedia.org/wiki/Amortized_analysis)** `O(1)` time complexity? In other words, performing `n` operations will take overall `O(n)` time even if one of those operations may take longer.

-----


if empty push x into both stacks
if not empty - pop the elements out of stack 2 and push them into stack 1, then push x into stack 2, then pop the items back out of stack 1 and push them into stack 2




<h1> Solution </h1>
class MyQueue {

  

    private Stack<Integer> stack1;

    private Stack<Integer> stack2;

  

    public MyQueue() {

        stack1 = new Stack<>();

        stack2 = new Stack<>();

    }

    public void push(int x) {

        if (stack1.isEmpty()) {

            stack1.push(x);

            stack2.push(x);

        }

  

        else {

            int currSize = stack1.size();

            while (!stack2.isEmpty()) {

                stack1.push(stack2.pop());

            }

  

            stack2.push(x);

  

            while(stack1.size() > currSize) {

                stack2.push(stack1.pop());

            }

        }

  

    }

    public int pop() {

        return stack2.pop();

    }

    public int peek() {

        return stack2.peek();

    }

    public boolean empty() {

        return stack2.isEmpty();

    }

}

  

/**

 * Your MyQueue object will be instantiated and called as such:

 * MyQueue obj = new MyQueue();

 * obj.push(x);

 * int param_2 = obj.pop();

 * int param_3 = obj.peek();

 * boolean param_4 = obj.empty();

 */