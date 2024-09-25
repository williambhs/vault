
----

Similarly to in Java, c++ has x++ vs --x.
Unlike in Java, in the majority of times, using one over the other has no real difference, but you should prefer to use the prefix (++x) vs the postfix (x++).
This is because occasionally using the postfix increment operator can produce errors - the prefix increment/decrement operations simply increment/decrement and then return x, whereas the postfix versions create a copy of x, increment/decrement the original, and then return the copy of x.
Because the postfix version creates a copy of x, if you try to initialize it to a variable, the output won't be what you expect: for example, if you look at this code -\

```cpp
int main()
{
    int x { 5 };
    int y { x++ }; 

    std::cout << x << ' ' << y << '\n';
    return 0;
}
```

Unlike in Java, the program will output 6 5 instead of 6 6.
This is because when you initialize variable y to x, what you end up doing is:

1 - copy x
2 - x is incremented
3 - y is assigned value of copy x, which is still 5 since the original x was incremented, and not the copy