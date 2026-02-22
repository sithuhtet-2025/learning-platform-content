# Java PrintStream Class

Last Updated : 12 Feb 2026

The PrintStream class in Java is used to write formatted and unformatted data to another output stream.

In this chapter, we will learn what the PrintStream class is, why it is used, its declaration, constructors, important methods, and how to print data to files and the console using examples.

## What is PrintStream Class in Java?

The **PrintStream class** is an output stream that provides convenient methods to print data values such as primitives, strings, and objects in a readable form.

It automatically flushes the output, so there is no need to explicitly call the flush() method. Also, its printing methods do not throw IOException, which makes it easier to use. The System.out object is a well-known example of a PrintStream.

## PrintStream Class Declaration

The following declaration shows how the PrintStream class is defined:

[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)

1. public class PrintStream extends FilterOutputStream implements Closeable, Appendable   

## Constructors of PrintStream Class

The PrintStream class provides constructors to create a print stream connected to another output stream.

### 1. PrintStream(OutputStream out)

This constructor creates a new print stream using the specified output stream.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)

1. PrintStream ps = new PrintStream(new FileOutputStream("file.txt"));  

### 2. PrintStream(String fileName)

This constructor creates a new print stream using the specified file name.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)

1. PrintStream ps = new PrintStream("file.txt");  

### Example of PrintStream Class Constructors

The following code shows how the constructors of the PrintStream class are used.

[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)

1. PrintStream p1 = new PrintStream(System.out);  
2. PrintStream p2 = new PrintStream(new FileOutputStream("data.txt"));  

## Methods of PrintStream Class

The PrintStream class provides methods to print data in different formats.

|Method|Description|
|---|---|
|void print(boolean b)|It prints the specified boolean value.|
|void print(char c)|It prints the specified char value.|
|void print(char[] c)|It prints the specified character [array](https://www.tpointtech.com/array-in-java) values.|
|void print(int i)|It prints the specified int value.|
|void print(long l)|It prints the specified long value.|
|void print(float f)|It prints the specified float value.|
|void print(double d)|It prints the specified double value.|
|void print(String s)|It prints the specified [string](https://www.tpointtech.com/java-string) value.|
|void print(Object obj)|It prints the specified object value.|
|void println(boolean b)|It prints the specified boolean value and terminates the line.|
|void println(char c)|It prints the specified char value and terminates the line.|
|void println(char[] c)|It prints the specified character array values and terminates the line.|
|void println(int i)|It prints the specified int value and terminates the line.|
|void println(long l)|It prints the specified long value and terminates the line.|
|void println(float f)|It prints the specified float value and terminates the line.|
|void println(double d)|It prints the specified double value and terminates the line.|
|void println(String s)|It prints the specified string value and terminates the line.|
|void println(Object obj)|It prints the specified object value and terminates the line.|
|void println()|It terminates the line only.|
|void printf(Object format, Object... args)|It writes the formatted string to the current stream.|
|void printf(Locale l, Object format, Object... args)|It writes the formatted string to the current stream.|
|void format(Object format, Object... args)|It writes the formatted string to the current stream using specified format.|
|void format(Locale l, Object format, Object... args)|It writes the formatted string to the current stream using specified format.|

## Examples of Java PrintStream Class

The following examples demonstrate how to use the Java PrintStream class.

### Example 1: Writing Data to a File Using PrintStream

The following example demonstrates how to write integer and string data to a file using the PrintStream class.

[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)

1. import java.io.FileOutputStream;  
2. import java.io.PrintStream;  

3. public class PrintStreamTest {  
4.     public static void main(String args[]) throws Exception {  

5.         FileOutputStream fout = new FileOutputStream("D:\\testout.txt");  
6.         PrintStream pout = new PrintStream(fout);  

7.         pout.println(2016);  
8.         pout.println("Hello Java");  
9.         pout.println("Welcome to Java");  

10.         pout.close();  
11.         fout.close();  

12.         System.out.println("Success...");  
13.     }  
14. }    

**Output:**

Success...

**File Content (testout.txt):**

2016
Hello Java
Welcome to Java

## Example 2: Using printf() Method with PrintStream

The following example demonstrates how to print formatted output using the printf() method of the PrintStream class.

[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)[](https://www.tpointtech.com/java-printstream-class#)

1. public class PrintStreamPrintfExample {  
2.     public static void main(String args[]) {  
3.         int a = 19;  
4.         System.out.printf("%d", a); // out is an object of PrintStream  
5.     }  
6. }   

**Output:**

19