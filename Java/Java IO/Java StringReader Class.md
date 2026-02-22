Java StringReader class is used to read character data from a string as a character stream.

In this chapter, we will learn what the StringReader class is, why it is used, its declaration, constructors, methods, and examples to understand how strings can be processed as character streams.

## What is StringReader Class in Java?

The **StringReader class** is a character stream that takes a String as its source and converts it into a readable character stream. It extends the [Reader class](https://www.tpointtech.com/java-reader-class) and allows programs to read characters from a string just like reading from a file or other input stream.

The StringReader class works completely in memory. It does not use system resources such as files or network sockets, so calling the close() method on a StringReader object has no effect.

## StringReader Class Declaration

The StringReader class is a part of the java.io package and extends the Reader class.

[](https://www.tpointtech.com/java-stringreader-class#)[](https://www.tpointtech.com/java-stringreader-class#)[](https://www.tpointtech.com/java-stringreader-class#)

1. public class StringReader extends Reader  

## Constructors of StringReader Class

The StringReader class provides a constructor to create a character input stream using a string.

### StringReader(String s)

This constructor creates a new StringReader using the specified string as the source of characters.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/java-stringreader-class#)[](https://www.tpointtech.com/java-stringreader-class#)[](https://www.tpointtech.com/java-stringreader-class#)

1. StringReader reader = new StringReader("Welcome to Java");  

### Example of StringReader Class Constructor

The following example demonstrates how to create a StringReader object using a string.

[](https://www.tpointtech.com/java-stringreader-class#)[](https://www.tpointtech.com/java-stringreader-class#)[](https://www.tpointtech.com/java-stringreader-class#)

1. String text = "Java StringReader Example";  
2. StringReader reader = new StringReader(text);  

## Methods of StringReader class

The StringReader class provides methods to read characters, skip characters, and manage the reader.

|Method|Description|
|---|---|
|int read()|It is used to read a single character.|
|int read(char[] cbuf, int off, int len)|It is used to read a character into a portion of an [array](https://www.tpointtech.com/array-in-java).|
|boolean ready()|It is used to tell whether the stream is ready to be read.|
|boolean markSupported()|It is used to tell whether the stream support mark() operation.|
|long skip(long ns)|It is used to skip the specified number of character in a stream|
|void mark(int readAheadLimit)|It is used to mark the mark the present position in a stream.|
|void reset()|It is used to reset the stream.|
|void close()|It is used to close the stream.|

## Examples of Java StringReader Class

Practice the following examples to understand the concept and usages of StringReader class.

### Example 1: Reading Characters from a String

The following example demonstrates how to read characters from a string using the StringReader class.

[](https://www.tpointtech.com/java-stringreader-class#)[](https://www.tpointtech.com/java-stringreader-class#)[](https://www.tpointtech.com/java-stringreader-class#)

1. import java.io.StringReader;  

2. public class StringReaderExample {  
3.     public static void main(String[] args) throws Exception {  

4.         String srg = "Hello Java!! \nWelcome to TpointTech.";  
5.         StringReader reader = new StringReader(srg);  

6.         int k = 0;  
7.         while ((k = reader.read()) != -1) {  
8.             System.out.print((char) k);  
9.         }  
10.         reader.close();  
11.     }  
12. }  

**Output:**

Hello Java!!
Welcome to TpointTech.

### Example 2: Reading String Data into a Character Array

The following example demonstrates how to read string data into a character array using StringReader.

[](https://www.tpointtech.com/java-stringreader-class#)[](https://www.tpointtech.com/java-stringreader-class#)[](https://www.tpointtech.com/java-stringreader-class#)

1. import java.io.StringReader;  

2. public class StringReaderExample2 {  
3.     public static void main(String[] args) throws Exception {  

4.         String data = "Java I/O StringReader";  
5.         StringReader reader = new StringReader(data);  

6.         char[] buffer = new char[8];  
7.         int length;  

8.         while ((length = reader.read(buffer, 0, buffer.length)) != -1) {  
9.             System.out.print(new String(buffer, 0, length));  
10.         }  
11.         reader.close();  
12.     }  
13. }  

**Output:**

Java I/O StringReader