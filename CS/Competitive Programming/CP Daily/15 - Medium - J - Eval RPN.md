
**Problem Number: 150
Relevant Tags: [[02 - DS - O - Stack]]
<h1> Problem Description </h1>

You are given an array of strings `tokens` that represents an arithmetic expression in a [Reverse Polish Notation](http://en.wikipedia.org/wiki/Reverse_Polish_notation).

Evaluate the expression. Return _an integer that represents the value of the expression_.

**Note** that:

- The valid operators are `'+'`, `'-'`, `'*'`, and `'/'`.
- Each operand may be an integer or another expression.
- The division between two integers always **truncates toward zero**.
- There will not be any division by zero.
- The input represents a valid arithmetic expression in a reverse polish notation.
- The answer and all the intermediate calculations can be represented in a **32-bit** integer.

**Example 1:**

**Input:** tokens = ["2","1","+","3","*"]
**Output:** 9
**Explanation:** ((2 + 1) * 3) = 9

**Example 2:**

**Input:** tokens = ["4","13","5","/","+"]
**Output:** 6
**Explanation:** (4 + (13 / 5)) = 6

**Example 3:**

**Input:** tokens = ["10","6","9","3","+","-11","*","/","*","17","+","5","+"]
**Output:** 22
**Explanation:** ((10 * (6 / ((9 + 3) * -11))) + 17) + 5
= ((10 * (6 / (12 * -11))) + 17) + 5
= ((10 * (6 / -132)) + 17) + 5
= ((10 * 0) + 17) + 5
= (0 + 17) + 5
= 17 + 5
= 22

**Constraints:**

- `1 <= tokens.length <= 104`
- `tokens[i]` is either an operator: `"+"`, `"-"`, `"*"`, or `"/"`, or an integer in the range `[-200, 200]`.
-----
Very confusing problem - read up on https://en.wikipedia.org/wiki/Reverse_Polish_notation

1 - create stack of chars, then call tochararray on each string in tokens to check if they are a number
2 - if number - push, else val1 = pop, val2 = second pop, then val2 should run the expression on val1 with the result being pushed
3 - return stack.peek()

** nvm use integerparseint instead, way more convenient

I solved this in like 20 minutes - guess I am getting better at leetcode?
<h1> Solution </h1>
class Solution {

    public int evalRPN(String[] tokens) {

        Stack<Integer> stack = new Stack<Integer>();

        for (String s: tokens) {

            if (s.equals("-")) {

                int top = stack.pop();

                int bot = stack.pop();

                stack.push(bot - top);

            }

  

            else if (s.equals("+")) {

                int top = stack.pop();

                int bot = stack.pop();

                stack.push(bot + top);

            }

  

            else if (s.equals("*")) {

                int top = stack.pop();

                int bot = stack.pop();

                stack.push(bot * top);

            }

            else if (s.equals("/")) {

                int top = stack.pop();

                int bot = stack.pop();

                stack.push(bot / top);

            }  

  

            else {stack.push(Integer.parseInt(s));}

        }

        return stack.peek();

    }

}