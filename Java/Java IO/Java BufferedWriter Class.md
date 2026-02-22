The BufferedWriter class in Java is used to write character data efficiently by providing buffering to a Writer.

In this chapter, we will learn what the BufferedWriter class is, why it is used, its declaration, constructors, important methods, and how to write data to files using examples.

## What is BufferedWriter Class in Java?

The **BufferedWriter class** is a character-based output stream that adds buffering capability to another Writer, and it is used to improve the performance of writing characters, arrays, and strings.

By storing data in a buffer before writing it to the file, BufferedWriter reduces the number of I/O operations and makes writing faster. It is a subclass of the Writer class.

## BufferedWriter Class Declaration

The following declaration shows how the BufferedWriter class is defined in Java.

[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)

1. public class BufferedWriter extends Writer  

## Constructors of BufferedWriter Class

The BufferedWriter class provides constructors to create a buffered character output stream.

### 1. BufferedWriter(Writer wrt)

This constructor creates a buffered writer that uses the default buffer size.

**Syntax:**

The syntax of this constructor is:

[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)

1. BufferedWriter bw = new BufferedWriter(new FileWriter("file.txt"));  

### 2. BufferedWriter(Writer wrt, int size)

This constructor creates a buffered writer with a specified buffer size.

**Syntax:**

The syntax of this constructor is:

[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)

1. BufferedWriter bw = new BufferedWriter(new FileWriter("file.txt"), 1024);  

### Example of BufferedWriter Class Constructors

The following example shows how the constructors of the BufferedWriter class are used.

[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)

1. BufferedWriter bw1 = new BufferedWriter(new FileWriter("file1.txt"));  
2. BufferedWriter bw2 = new BufferedWriter(new FileWriter("file2.txt"), 2048);  

## Methods of BufferedWriter Class

The BufferedWriter class provides methods to write buffered character data.

|Method|Description|
|---|---|
|void newLine()|It is used to add a new line by writing a line separator.|
|void write(int c)|It is used to write a single character.|
|void write(char[] cbuf, int off, int len)|It is used to write a portion of an array of characters.|
|void write(String s, int off, int len)|It is used to write a portion of a string.|
|void flush()|It is used to flushes the input stream.|
|void close()|It is used to closes the input stream|

## Examples of Java BufferedWriter Class

The following examples demonstrate how to write data to a file using the BufferedWriter class.

### Example 1: Writing Text to a File Using BufferedWriter

The following example demonstrates how to write a string to a file using the BufferedWriter class.

[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)

1. import java.io.*;  

2. public class BufferedWriterExample {  
3.     public static void main(String[] args) throws Exception {  
4.         FileWriter writer = new FileWriter("D:\\testout.txt");  
5.         BufferedWriter buffer = new BufferedWriter(writer);  
6.         buffer.write("Welcome to TpointTech.");  
7.         buffer.close();  
8.         System.out.println("Success");  
9.     }  
10. }  

**Output:**

success

**testout.txt:**

Welcome to TpointTech.

### Example 2: Writing Multiple Lines Using newLine()

The following example demonstrates how to write multiple lines to a file using the newLine() method of the BufferedWriter class.

[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)[](https://www.tpointtech.com/java-bufferedwriter-class#)

1. import java.io.*;  

2. public class BufferedWriterNewLineExample {  
3.     public static void main(String[] args) throws Exception {  
4.         BufferedWriter bw = new BufferedWriter(new FileWriter("D:\\testout2.txt"));  
5.         bw.write("Java I/O");  
6.         bw.newLine();  
7.         bw.write("BufferedWriter Example");  
8.         bw.close();  
9.         System.out.println("Data written successfully");  
10.     }  
11. }  

**Output:**

Data written successfully

**File Content (testout2.txt):**

Java I/O
BufferedWriter Example