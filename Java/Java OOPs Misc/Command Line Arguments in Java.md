
Java Command-line arguments allow you to pass input values to a program at runtime that makes the program easy to test and run with different data without modifying the code.

## What are Command-line Arguments in Java?

**Command-line arguments** are inputs passed to a Java program at runtime through the console. They are received in the **main()** method as a **String array (String[] args)**.

**Example:** If you run:

[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)

1. java MyProgram 10 20 Hello  

Then inside main(String[] args),

[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)

1. args[0] = "10", args[1] = "20", args[2] = "Hello"  

This makes programs easy to test with different inputs.

## Why Use Command-Line Arguments?

Command-line arguments offer a flexible way to pass input values to Java programs without changing the source code. It is particularly useful in scenarios like automation, where scripts need to run with different inputs, or configuration management, where settings change between environments (for example, dev, test, prod).

They allow developers to test various input scenarios efficiently, making programs more dynamic and reusable. Rather than hardcoding values, users can supply them externally, which leads to cleaner code and easier maintenance.

## Example of Command Line Argument

In this example, we are receiving only one argument and printing it. To run this Java program, we must pass at least one argument from the command prompt.

[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)

1. class Main {    
2. public static void main(String args[]) {    
3. System.out.println("Your first argument is: "+args[0]);    
4. }    
5. }    

**Output:**

Your first argument is: Andrew

Execute the above program by using the following commands.

[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)

1. compile by > javac Main.java    
2. run by > java Main Andrew  

## How to Handle Missing Arguments?

Accessing arguments that were not passed will cause an ArrayIndexOutOfBoundsException. To avoid this, always check the length of the args[] array:

[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)

1. if (args.length > 0) {  
2.     System.out.println("First argument: " + args[0]);  
3. } else {  
4.     System.out.println("No arguments provided.");  
5. }  

The above code snippet avoids crashes and improves the reliability of your code.

## Converting Argument Types

All command-line arguments are passed as strings. If your logic needs integers, floats, or booleans, we must parse them:

[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)

1. int num = Integer.parseInt(args[0]);  
2. double value = Double.parseDouble(args[1]);  
3. boolean flag = Boolean.parseBoolean(args[2]);  

Always handle exceptions like NumberFormatException when converting input values.

## Example: Printing Multiple Values Using Command Line Arguments

In this example, we are printing all the arguments passed from the command line. For this purpose, we have traversed the array using a for loop.

[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)

1. class Main {    
2. public static void main(String args[]) {    
3. for(int i=0;i<args.length;i++)    
4. System.out.println(args[i]);    
5. }    
6. }    

**Output:**

Andrew
25
University
of
California

Execute the above program by using the following commands.

[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)[](https://www.tpointtech.com/command-line-arguments-in-java#)

1. compile by > javac Main.java    
2. run by > java Main Andrew 25 University of California   

## Important Points to Remember

1. While running a Java program in the command prompt, arguments are provided in the console.
2. Arguments are added to the String[] args array used by the main() method.
3. The first argument is in args[0], the second in args[1] and, so on.
4. Trying to use a non-existent index will cause an ArrayIndexOutOfBoundsException to be thrown.
5. The number of arguments sent can be checked with args.length.
6. We can take advantage of loops (for example, a for loop) to loop through and print out all the arguments.
7. Every command-line argument, regardless of being a number, is still regarded as a string.

## Conclusion

Command line arguments in Java provide a flexible and efficient means of passing input to a programme at runtime. By supplying arguments through the main(String[] args) method, developers can customise programme behaviour without altering the source code. It makes Java applications more dynamic, testable, and suitable for automation.