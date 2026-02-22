Java StringWriter class is used to write character data into an internal string buffer, which can later be converted into a String.

In this chapter, we will understand what the StringWriter class is, why it is used, its declaration, constructors, methods, and examples to see how character data can be collected and processed in memory.

## What is StringWriter Class in Java?

The **StringWriter class** is a character stream that collects written output in an internal StringBuffer. This buffered content can later be converted into a String using the toString() method.

The StringWriter class extends the [Writer](https://www.tpointtech.com/java-writer-class) class and works entirely in memory. Since it does not use system resources such as files or network sockets, calling the close() method on a StringWriter object has no effect.

## Java StringWriter class declaration

The StringWriter class is a part of the java.io package and extends the Writer class.

[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)

1. public class StringWriter extends Writer  

## Constructors of StringWriter Class

The StringWriter class provides constructors to create a character output stream that writes data into an internal string buffer.

### 1. StringWriter()

This constructor creates a new StringWriter using a default initial buffer size.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)

1. StringWriter writer = new StringWriter();  

### 2. StringWriter(int initialSize)

This constructor creates a new StringWriter using the specified initial buffer size.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)

1. StringWriter writer = new StringWriter(100);  

### Example of StringWriter Class Constructors

The following example demonstrates how to create a StringWriter object using its constructors.

[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)

1. StringWriter writer1 = new StringWriter();  
2. StringWriter writer2 = new StringWriter(256);  

## Methods of StringWriter class

The StringWriter class provides several methods to write character data and retrieve it as a string.

|Method|Description|
|---|---|
|void write(int c)|It is used to write the single character.|
|void write(String str)|It is used to write the string.|
|void write(String str, int off, int len)|It is used to write the portion of a string.|
|void write(char[] cbuf, int off, int len)|It is used to write the portion of an [array](https://www.tpointtech.com/array-in-java) of characters.|
|String toString()|It is used to return the buffer current value as a string.|
|StringBuffer getBuffer()|It is used t return the string buffer.|
|StringWriter append(char c)|It is used to append the specified character to the writer.|
|StringWriter append(CharSequence csq)|It is used to append the specified character sequence to the writer.|
|StringWriter append(CharSequence csq, int start, int end)|It is used to append the subsequence of specified character sequence to the writer.|
|void flush()|It is used to flush the stream.|
|void close()|It is used to close the stream.|

## Examples of Java StringWriter Class

Practice the following examples to understand and usages of StringWriter class.

### Example 1: Reading File Data into StringWriter

The following example demonstrates how to use StringWriter to read file data into memory and convert it into a string.

[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)

1. import java.io.*;  

2. public class StringWriterExample {  
3.     public static void main(String[] args) throws IOException {  

4.         char[] ary = new char[512];  
5.         StringWriter writer = new StringWriter();  

6.         FileInputStream input = new FileInputStream("D://testout.txt");  
7.         BufferedReader buffer =  
8.             new BufferedReader(new InputStreamReader(input, "UTF-8"));  

9.         int x;  
10.         while ((x = buffer.read(ary)) != -1) {  
11.             writer.write(ary, 0, x);  
12.         }  

13.         System.out.println(writer.toString());  

14.         writer.close();  
15.         buffer.close();  
16.     }  
17. }  

Here, we are assuming that testout.txt contains the following data:

Javatpoint provides tutorial in Java, Spring, Hibernate, Android, PHP etc.

**Output:**

Javatpoint provides tutorial in Java, Spring, Hibernate, Android, PHP etc.

### Example 2: Writing Data Directly Using StringWriter

The following example demonstrates how to write data directly into a StringWriter and retrieve it as a String.

[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)[](https://www.tpointtech.com/java-stringwriter-class#)

1. import java.io.StringWriter;  

2. public class StringWriterExample2 {  
3.     public static void main(String[] args) {  

4.         StringWriter writer = new StringWriter();  
5.         writer.write("Welcome to ");  
6.         writer.write("Java StringWriter class.");  

7.         System.out.println(writer.toString());  
8.     }  
9. }  

**Output:**

Welcome to Java StringWriter class.