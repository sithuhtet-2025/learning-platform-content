# Java CharArrayWriter Class

Last Updated : 12 Feb 2026

The CharArrayWriter class in Java is used to write character data into an in-memory buffer that can be reused to write data to multiple output streams.

In this chapter, we will learn what the CharArrayWriter class is, why it is used, its declaration, constructors, important methods, and how to write common data to multiple files using examples.

## What is CharArrayWriter Class in Java?

The CharArrayWriter class is a character-based output stream that writes data into an internal character buffer instead of writing directly to a file.

It extends the [Writer class](https://www.tpointtech.com/java-writer-class) and is mainly used when the same character data needs to be written to multiple destinations. The internal buffer grows automatically as data is written, and calling the close() method has no effect on the stream.

## CharArrayWriter Class Declaration

The following declaration shows how the CharArrayWriter class is defined:

[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)

1. public class CharArrayWriter extends Writer  

## Constructors of CharArrayWriter Class

The CharArrayWriter class provides constructors to create an in-memory character output stream.

### 1. CharArrayWriter()

This constructor creates a new character array writer with an initial default buffer size.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)

1. CharArrayWriter writer = new CharArrayWriter();  

### 2. CharArrayWriter(int size)

This constructor creates a new character array writer with a specified initial buffer size.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)

1. CharArrayWriter writer = new CharArrayWriter(1024);  

### Example of CharArrayWriter Class Constructors

The following code shows how the constructors of the CharArrayWriter class are used.

[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)

1. CharArrayWriter w1 = new CharArrayWriter();  
2. CharArrayWriter w2 = new CharArrayWriter(2048);  

## Methods of CharArrayWriter Class

The CharArrayWriter class provides methods to write and manage character data in memory. The following table lists important methods of CharArrayWriter class.

|Method|Description|
|---|---|
|int size()|It is used to return the current size of the buffer.|
|char[] toCharArray()|It is used to return the copy of an input data.|
|String toString()|It is used for converting an input data to a [string](https://www.tpointtech.com/java-string).|
|CharArrayWriter append(char c)|It is used to append the specified character to the writer.|
|CharArrayWriter append(CharSequence csq)|It is used to append the specified character sequence to the writer.|
|CharArrayWriter append(CharSequence csq, int start, int end)|It is used to append the subsequence of a specified character to the writer.|
|void write(int c)|It is used to write a character to the buffer.|
|void write(char[] c, int off, int len)|It is used to write a character to the buffer.|
|void write(String str, int off, int len)|It is used to write a portion of string to the buffer.|
|void writeTo(Writer out)|It is used to write the content of buffer to different character stream.|
|void flush()|It is used to flush the stream.|
|void reset()|It is used to reset the buffer.|
|void close()|It is used to close the stream.|

## Examples of Java CharArrayWriter Class

The following examples demonstrate how to use the Java CharArrayWriter class.

### Example 1: Writing Common Data to Multiple Files

The following example demonstrates how to write the same character data to multiple files using the CharArrayWriter class.

[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)

1. import java.io.CharArrayWriter;  
2. import java.io.FileWriter;  

3. public class CharArrayWriterExample {  
4.     public static void main(String args[]) throws Exception {  

5.         CharArrayWriter out = new CharArrayWriter();  
6.         out.write("Welcome to TpointTech");  

7.         FileWriter f1 = new FileWriter("D:\\a.txt");  
8.         FileWriter f2 = new FileWriter("D:\\b.txt");  
9.         FileWriter f3 = new FileWriter("D:\\c.txt");  
10.         FileWriter f4 = new FileWriter("D:\\d.txt");  

11.         out.writeTo(f1);  
12.         out.writeTo(f2);  
13.         out.writeTo(f3);  
14.         out.writeTo(f4);  

15.         f1.close();  
16.         f2.close();  
17.         f3.close();  
18.         f4.close();  

19.         System.out.println("Success...");  
20.     }  
21. }    

**Output:**

Success...

**File Content (a.txt, b.txt, c.txt, d.txt):**

Welcome to TpointTech

### Example 2: Converting CharArrayWriter Data to String

The following example demonstrates how to convert the buffer data of CharArrayWriter into a string.

[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)[](https://www.tpointtech.com/java-chararraywriter-class#)

1. import java.io.CharArrayWriter;  

2. public class CharArrayWriterToStringExample {  
3.     public static void main(String[] args) throws Exception {  

4.         CharArrayWriter writer = new CharArrayWriter();  
5.         writer.write("Java CharArrayWriter Example");  

6.         String result = writer.toString();  
7.         System.out.println(result);  
8.     }  
9. }  

**Output:**

Java CharArrayWriter Example