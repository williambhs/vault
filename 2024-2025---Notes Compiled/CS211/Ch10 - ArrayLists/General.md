
----
see: [[02 - DS - O - ArrayList]]
arraylist - dynamic

must be imported

ArrayList<String> list = new ArrayList<String>();

easier to think about ArrayList<String> as one object - an arraylist of strings

Java introduced the diamond operator so you don't need String inside the second diamond operator ->
Arraylist<String> list = new ArrayList<>();

When traversing array - if you want to change the elements you should work backwards, especially if the constraints of the array change as you traverse it. This is to ensure the elements you processed won't affect the array traversal.

While arraylist doesn't support spamming stuff in {}, you can use list.of inside the parenthesis after the diamond to quickly initialize the arraylist ->
ArrayList<String> arr = new ArrayList<>(List.of("hello", "world"));

ArrayList<E> -> e stands for element - can take any objects but not primitives like ints, doubles, chars, etc

wrapper classes are reference types and allows you to get around this issue

Boxing - automatic conversion - you can add ints like 12 to Integer subclass because Java knows the relationship and will automatically convert. Java will also do this in reverse - known as unboxing