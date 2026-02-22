Java PipedReader class is used to read character data from a pipe as a stream of characters.

In this chapter, we will learn what the PipedReader class is, why it is used, its declaration, constructors, methods, and examples to understand how it works with PipedWriter for inter-thread communication.

## What is PipedReader Class in Java?

The **PipedReader class** is a character input stream that reads data from a pipe. This data is written to the pipe using a connected PipedWriter.

PipedReader is mainly used for **communication between two threads**, where one thread writes character data using PipedWriter and another thread reads that data using PipedReader. Both streams must be connected to each other and usually run in different threads.

## PipedReader Class Declaration

The PipedReader class is a part of the java.io package and extends the Reader class.

[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)

1. public class PipedReader extends Reader  

## Constructors of PipedReader Class

The PipedReader class provides constructors to create a piped reader that may or may not be connected to a piped writer.

### 1. PipedReader()

This constructor creates a PipedReader that is not yet connected to any PipedWriter.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)

1. PipedReader reader = new PipedReader();  

### 2. PipedReader(PipedWriter src)

This constructor creates a PipedReader that is already connected to the specified PipedWriter.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)

1. PipedWriter writer = new PipedWriter();  
2. PipedReader reader = new PipedReader(writer);  

### 3. PipedReader(int pipeSize)

This constrictor creates a PipedReader that is not yet connected and uses the specified pipe size for the internal buffer.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)

1. PipedReader reader = new PipedReader(1024);  

### 4. PipedReader(PipedWriter src, int pipeSize)

This constructor creates a PipedReader that is connected to the specified PipedWriter and uses the given pipe size.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)

1. PipedWriter writer = new PipedWriter();  
2. PipedReader reader = new PipedReader(writer, 1024);  

### Example of PipedReader Class Constructors

The following example demonstrates how to create and connect a PipedReader using different constructors.

[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)

1. PipedWriter writer = new PipedWriter();  
2. PipedReader reader = new PipedReader();  
3. reader.connect(writer);  

## Methods of PipedReader Class

The PipedReader class provides the following methods to read characters and manage the pipe connection.

|Modifier and Type|Method|Method|
|---|---|---|
|void|close()|It closes this piped stream and releases any system resources associated with the stream.|
|void|connect(PipedWriter src)|It causes this piped reader to be connected to the piped writer src.|
|int|read()|It reads the next character of data from this piped stream.|
|int|read(char[] cbuf, int off, int len)|It reads up to len characters of data from this piped stream into an [array](https://www.tpointtech.com/array-in-java) of characters.|
|boolean|ready()|It tells whether this stream is ready to be read.|

## Examples of Java PipedReader Class

Practice the following examples to understand the concept and usages of PipedReader class.

### Example 1: Reading Data from a Pipe Using Two Threads

The following example demonstrates how PipedReader reads data written by a PipedWriter using two different threads.

[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)

1. import java.io.PipedReader;  
2. import java.io.PipedWriter;  

3. public class PipedReaderExample {  
4.     public static void main(String[] args) {  
5.         try {  

6.             final PipedReader read = new PipedReader();  
7.             final PipedWriter write = new PipedWriter(read);  

8.             Thread readerThread = new Thread(new Runnable() {  
9.                 public void run() {  
10.                     try {  
11.                         int data = read.read();  
12.                         while (data != -1) {  
13.                             System.out.print((char) data);  
14.                             data = read.read();  
15.                         }  
16.                     } catch (Exception e) {  
17.                         System.out.println(e);  
18.                     }  
19.                 }  
20.             });  

21.             Thread writerThread = new Thread(new Runnable() {  
22.                 public void run() {  
23.                     try {  
24.                         write.write("I love my country\n".toCharArray());  
25.                         write.close();  
26.                     } catch (Exception e) {  
27.                         System.out.println(e);  
28.                     }  
29.                 }  
30.             });  

31.             readerThread.start();  
32.             writerThread.start();  

33.         } catch (Exception e) {  
34.             System.out.println(e);  
35.         }  
36.     }  
37. }  

**Output:**

I love my country

### Example 2: Reading Data Using connect() Method

The following example demonstrates how a PipedReader can be connected to a PipedWriter using the connect() method.

[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)[](https://www.tpointtech.com/java-pipedreader-class#)

1. import java.io.PipedReader;  
2. import java.io.PipedWriter;  

3. public class PipedReaderExample2 {  
4.     public static void main(String[] args) throws Exception {  

5.         PipedReader reader = new PipedReader();  
6.         PipedWriter writer = new PipedWriter();  

7.         reader.connect(writer);  

8.         writer.write("Java PipedReader Example".toCharArray());  
9.         writer.close();  

10.         int ch;  
11.         while ((ch = reader.read()) != -1) {  
12.             System.out.print((char) ch);  
13.         }  
14.         reader.close();  
15.     }  
16. }  

**Output:**

Java PipedReader Example