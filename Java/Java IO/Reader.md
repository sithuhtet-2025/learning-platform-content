# Java Reader



The Reader class in Java is an abstract class used for reading character streams.

In this chapter, we will learn what the Reader class is, why it is used, its declaration, constructors, important methods, and how to read character data using examples.

## What is Reader Class in Java?

The **Reader class** is an abstract class for reading data in the form of characters, and it is used as the base class for all character input stream classes.

It provides common methods to read characters, character arrays, and strings. [Classes](https://www.tpointtech.com/object-class) such as [BufferedReader](https://www.tpointtech.com/java-bufferedreader-class), FileReader, [InputStreamReader](https://www.tpointtech.com/Input-from-keyboard-by-InputStreamReader), and [StringReader](https://www.tpointtech.com/java-stringreader-class) extend the Reader class to provide concrete implementations.

## Java Reader Class Declaration

The following declaration shows how the Reader class is defined in Java.

[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)

1. public abstract class Reader  

## Fields of Reader Class

The Reader class contains a field used for synchronization.

|Modifier and Type|Field|Description|
|---|---|---|
|protected Object|lock|The object used to synchronize operations on this stream.|

## Constructors of Reader Class

The Reader class provides protected constructors that are used by its subclasses.

### 1. Reader()

This constructor creates a new character stream reader whose critical sections synchronize on the reader itself.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)

1. protected Reader()  

### 2. Reader(Object lock)

This constructor creates a new character stream reader whose critical sections synchronize on the specified lock object.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)

1. protected Reader(Object lock)  

### Example of Reader Class Constructors

The following example shows how the constructors of the Reader class are used indirectly through its subclasses.

[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)

1. Reader r1 = new FileReader("file1.txt");  
2. Reader r2 = new BufferedReader(new FileReader("file2.txt"));  

## Methods of Reader Class

The Reader class provides methods to read character data from input streams.

|Modifier and Type|Method|Description|
|---|---|---|
|abstract void|close()|It closes the stream and releases any system resources associated with it.|
|void|mark(int readAheadLimit)|It marks the present position in the stream.|
|boolean|markSupported()|It tells whether this stream supports the mark() operation.|
|int|read()|It reads a single character.|
|int|read(char[] cbuf)|It reads characters into an [array](https://www.tpointtech.com/array-in-java).|
|abstract int|read(char[] cbuf, int off, int len)|It reads characters into a portion of an array.|
|int|read(CharBuffer target)|It attempts to read characters into the specified character buffer.|
|boolean|ready()|It tells whether this stream is ready to be read.|
|void|reset()|It resets the stream.|
|long|skip(long n)|It skips characters.|

## Examples of Java Reader Class

The following examples demonstrate how the Reader class is used through its subclasses.

### Example 1: Reading Characters from a File Using FileReader

This example demonstrates how to read characters from a file using the FileReader class.

[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)

1. import java.io.*;  
2. public class ReaderExample {  
3.     public static void main(String[] args) {  
4.         try {  
5.             Reader reader = new FileReader("file.txt");  
6.             int data = reader.read();  
7.             while (data != -1) {  
8.                 System.out.print((char) data);  
9.                 data = reader.read();  
10.             }  
11.             reader.close();  
12.         } catch (Exception ex) {  
13.             System.out.println(ex.getMessage());  
14.         }  
15.     }  
16. }  

**file.txt:**

I love my country

**Output:**

I love my country

### Example 2: Reading Data Using BufferedReader

This example demonstrates how to read text efficiently using the BufferedReader class.

[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)[](https://www.tpointtech.com/java-reader-class#)

1. import java.io.*;  

2. public class BufferedReaderExample {  
3.     public static void main(String[] args) {  
4.         try {  
5.             Reader r = new FileReader("file.txt");  
6.             BufferedReader br = new BufferedReader(r);  
7.             String line;  
8.             while ((line = br.readLine()) != null) {  
9.                 System.out.println(line);  
10.             }  
11.             br.close();  
12.         } catch (IOException e) {  
13.             System.out.println(e);  
14.         }  
15.     }  
16. }  

**Output:**

I love my country