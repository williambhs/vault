See: [[01 - C - I - IO (Input Output)]]

Creating a file - File f = new File("name.txt");

Requires importing java.io.*

Can be read with a scanner - instead of passing System.in, you can pass a File object
Don't need to create a new file - instead:
Scanner input = new Scanner(new File("filename.txt"));

Checked exception - use the try catch statement - you can avoid problems as long as you indicate you are handling it