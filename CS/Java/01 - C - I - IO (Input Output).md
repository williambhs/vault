**Relevant Tags:**

----

**Useful Reference - https://usaco.guide/general/input-output

Three types - Scanner, BufferedReader + PW, and IO Template
IO Template preferred for CP as you can just copy paste using snippets.

<h2> #1 Scanner (slowest) </h2>
Documentation: https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html

requires importing java.util.Scanner;
Syntax:
Scanner sc = new Scanner(System.in);

Useful methods (view documentation):
hasNext(); - returns true if the scanner has another token
hasNextInt/hasNextLong/hasNextShort - returns true if the next token is an int/long/short
nextLine() - skips the current line and returns the input that was skipped



**Info for FastReader class used in the template:**
Custom implementation of reader class for java that uses bufferedreader + stringtokenizer - reads from input.txt and writes to output.txt, otherwise defaults to standard input and output (System.in and System.out)

Methods include:
next()
nextInt()
nextLong()
nextDouble()
nextLine()

use like scanner class after making a new fastreader - ex. 
int a = reader.nextInt()