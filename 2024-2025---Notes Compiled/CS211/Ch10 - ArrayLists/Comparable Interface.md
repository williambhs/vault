
----
Similar to Arrays.sort() used to sort arrays ([[02 - DS - O - Array]]) arraylists can be sorted using Collections.sort() - for example if you have ArrayList<Integer> arr, you can do:

Collections.sort(arr);

similarly, if run with an array of strings, they will become sorted alphabetically

ArrayLists have no natural ordering because you can't really compare two arraylists of the same length but different elements - thus Java has a comparable interface:

public interface Comparable<T> {
	public int compareTo(T other);
}

is the syntax, with T being short for "type".

When using compareTo in your own class, replace the T with the type - for example public class DateTracker implements Comparable<DateTracker> since you're comparing pairs of values from the DateTracker class

Then create a public int compareTo(DateTracker other) method and use if statements returning values - usually -1/0/1 based on how to compare your datatype. However - to simplify, sometimes you can subtract the first value from the second - while it won't return 1/0/-1, it will always return positive when the first value is greater than the parameter

implementing comparable very handy as it allows you to now sort your datatype and use other useful built-in utillities


convention of compareTo - can't return a boolean t/f because there are three possible results:
1 - less than: arbitrary negative number
2 - equal: 0
3 - more than: arbitrary positive number

