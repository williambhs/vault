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


<h2> #2 BufferedReader + PrintWriter + StringTokenizer (diesofcringe) </h2>
requires importing java.util.BufferedReader, java.util.StringTokenizer

When initializing, have it throw an IOException - makes it so you don't need a new try/catch block to handle exceptions for things like readline, etc if there is an IO error
To use BufferedReader, you need to pass in a reader object - that means you also need an inputstreamreader to pass in

Syntax:
BufferedReader bf = new BufferedReader(new InputStreamReader(System.in));
In USACO - you use a filereader instead - 
BufferedReader bf = new BufferedReader(new FileReader("input.in"));

To properly read from the file, you need to use a combination of methods from the BufferedReader class in conjunction with sometimes a StringTokenizer when the input is separated with things like whitespace.
For an input that's just an int and some strings, you can use String str = br.readLine() to read the string and int i = Integer.parseInt(br.readLine()) to read the int. 
However, when the input is separated by things like whitespace, you need to use stringtokenizer and treat the whitespace as tokens. 

To do this - first create a new stringtokenizer (after importing stringtokenizer)
(Documentation: [StringTokenizer (Java SE 15 & JDK 15) (oracle.com)](https://docs.oracle.com/en/java/javase/15/docs/api/java.base/java/util/StringTokenizer.html))

StringTokenizer st = new StringTokenizer(br.readLine());



When finished, buffered reader has a close method - make sure to do bf.close(); for good practice as to not leak data/resources.


<h2> #3 IO Template </h2>
**FOR USACO:**





**FOR CFORCES:**

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


