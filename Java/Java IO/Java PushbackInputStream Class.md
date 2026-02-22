The PushbackInputStream class in Java is used to read data from an input stream with the ability to push back bytes that have already been read.

In this chapter, we will understand what the PushbackInputStream class is, why it is used, its declaration, constructors, important methods, and how unread functionality works using an example.

## What is PushbackInputStream Class in Java?

The **PushbackInputStream class** extends FilterInputStream and provides additional functionality to another input stream. It allows a program to **unread one or more bytes** after they have been read.

This feature is useful when a program needs to inspect input data and then decide whether to process it or push it back for re-reading later. It is commonly used in parsing scenarios.

## PushbackInputStream Class Declaration

The following declaration shows how the PushbackInputStream class is defined:

[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)

1. public class PushbackInputStream extends FilterInputStream  

## Constructors of PushbackInputStream Class

The PushbackInputStream class provides constructors to create a pushback buffer.

### 1. PushbackInputStream(InputStream in)

This constructor creates a PushbackInputStream with a default pushback buffer size of one byte.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)

1. PushbackInputStream push = new PushbackInputStream(inputStream);  

### 2. PushbackInputStream(InputStream in, int size))

This constructor creates a PushbackInputStream with a specified pushback buffer size.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)

1. PushbackInputStream push = new PushbackInputStream(inputStream, 10);  

### Example of PushbackInputStream Class Constructors

The following example shows how the constructor of the PushbackInputStream class is used.

[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)

1. InputStream in = new FileInputStream("data.txt");  
2. PushbackInputStream push = new PushbackInputStream(in, 5);  

### Methods of PushbackInputStream Class

The PushbackInputStream class provides the following methods to read and unread bytes.

|Method|Description|
|---|---|
|int available()|It is used to return the number of bytes that can be read from the input stream.|
|int read()|It is used to read the next byte of data from the input stream.|
|boolean markSupported()||
|void mark(int readlimit)|It is used to mark the current position in the input stream.|
|long skip(long x)|It is used to skip over and discard x bytes of data.|
|void unread(int b)|It is used to pushes back the byte by copying it to the pushback buffer.|
|void unread(byte[] b)|It is used to pushes back the [array](https://www.tpointtech.com/array-in-java) of byte by copying it to the pushback buffer.|
|void reset()|It is used to reset the input stream.|
|void close()|It is used to close the input stream.|

## Examples of Java PushbackInputStream Class

Practice the following examples to understand the methods and usages of PushbackInputStream class.

### Example 1: Using PushbackInputStream to Replace Characters

The following example demonstrates how to unread bytes and replace specific characters using the PushbackInputStream class.

[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)

1. import java.io.*;  

2. public class PushbackExample1 {  
3.     public static void main(String[] args) throws Exception {  

4.         String str = "1##2#34###12";  
5.         byte[] ary = str.getBytes();  

6.         ByteArrayInputStream array = new ByteArrayInputStream(ary);  
7.         PushbackInputStream push = new PushbackInputStream(array);  

8.         int i;  
9.         while ((i = push.read()) != -1) {  
10.             if (i == '#') {  
11.                 int j = push.read();  
12.                 if (j == '#') {  
13.                     System.out.print("**");  
14.                 } else {  
15.                     push.unread(j);  
16.                     System.out.print((char) i);  
17.                 }  
18.             } else {  
19.                 System.out.print((char) i);  
20.             }  
21.         }  
22.         push.close();  
23.     }  
24. }  

**Output:**

****1**2#34**#12****

### ****Example 2: Unreading a Byte After Look-Ahead****

****The following example demonstrates how a byte can be read, checked, and then pushed back into the stream if required.****

****[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)[](https://www.tpointtech.com/java-pushbackinputstream-class#)

1. import java.io.*;  

2. public class PushbackExample2 {  
3.     public static void main(String[] args) throws Exception {  

4.         String data = "ABC";  
5.         byte[] bytes = data.getBytes();  

6.         ByteArrayInputStream bin = new ByteArrayInputStream(bytes);  
7.         PushbackInputStream push = new PushbackInputStream(bin);  

8.         int ch = push.read();  
9.         System.out.println("Read character: " + (char) ch);  

10.         // Push back the character  
11.         push.unread(ch);  

12.         int reread = push.read();  
13.         System.out.println("Re-read character: " + (char) reread);  

14.         push.close();  
15.     }  
16. }****  

******Output:******

********Read character: A
Re-read character: A********