Java PipedWriter class is used to write character data into a pipe, which can be read by a connected PipedReader.

In this chapter, we will learn what the PipedWriter class is, why it is used, its declaration, constructors, methods, and examples to understand inter-thread communication using character streams.

## What is PipedWriter Class in Java?

The **PipedWriter class** is a character stream used to write data into a pipe. This data can be read from the pipe using a connected PipedReader.

PipedWriter is generally used for **communication between two threads**, where one thread writes character data using PipedWriter and another thread reads that data using PipedReader.

## PipedWriter Class Declaration

The PipedWriter class is a part of the java.io package and extends the Writer class.

[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)

1. public class PipedWriter extends Writer  

## Constructors of PipedWriter Class

The PipedWriter class provides constructors to create a piped writer that may or may not be connected to a piped reader.

### 1. PipedWriter()

This constructor creates a PipedWriter that is not yet connected to any PipedReader.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)

1. PipedWriter writer = new PipedWriter();  

### 2. PipedWriter(PipedReader snk)

This constructor creates a PipedWriter that is already connected to the specified PipedReader.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)

1. PipedWriter writer = new PipedWriter(reader);  

### Example of PipedWriter Class Constructors

The following example demonstrates how to create and connect a PipedWriter with a PipedReader.

[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)

1. PipedReader reader = new PipedReader();  
2. PipedWriter writer = new PipedWriter(reader);  

## Methods of PipedWriter Class

The PipedWriter class provides methods to write characters and manage the pipe connection.

|Modifier and Type|Method|Method|
|---|---|---|
|void|close()|It closes this piped output stream and releases any system resources associated with this stream.|
|void|connect(PipedReader snk)|It connects this piped writer to a receiver.|
|void|flush()|It flushes this output stream and forces any buffered output characters to be written out.|
|void|write(char[] cbuf, int off, int len)|It writes len characters from the specified character [array](https://www.tpointtech.com/array-in-java) starting at offset off to this piped output stream.|
|void|write(int c)|It writes the specified char to the piped output stream.|

## Examples of Java PipedWriter Class

Practice the following examples to understand the concept and usages of PipedWriter class.

### Example 1: Communication Between Two Threads Using PipedWriter

The following example demonstrates how PipedWriter and PipedReader are used for communication between two different threads.

[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)

1. import java.io.PipedReader;  
2. import java.io.PipedWriter;  

3. public class PipedWriterExample {  
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

### Example 2: Connecting PipedWriter Later Using connect() Method

The following example demonstrates how a PipedWriter can be created first and connected to a PipedReader later using the connect() method.

[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)[](https://www.tpointtech.com/java-pipedwriter-class#)

1. import java.io.PipedReader;  
2. import java.io.PipedWriter;  

3. public class PipedWriterExample2 {  
4.     public static void main(String[] args) throws Exception {  

5.         PipedReader reader = new PipedReader();  
6.         PipedWriter writer = new PipedWriter();  

7.         writer.connect(reader);  

8.         writer.write("Java PipedWriter Example".toCharArray());  
9.         writer.close();  

10.         int ch;  
11.         while ((ch = reader.read()) != -1) {  
12.             System.out.print((char) ch);  
13.         }  
14.         reader.close();  
15.     }  
16. }  

**Output:**

Java PipedWriter Example