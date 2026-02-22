# Java BufferedReader Class

Last Updated : 12 Feb 2026

The BufferedReader class in Java is used to read text efficiently from a character-based input stream.

In this chapter, we will learn what the BufferedReader class is, why it is used, its declaration, constructors, important methods, and how to read data from files and the console using examples.

## What is BufferedReader Class in Java?

The **BufferedReader class** is a character-based input stream that provides buffering for another Reader, making the reading process faster and more efficient.

It is commonly used to read text data line by line using the readLine() method. By reducing the number of direct I/O operations, it improves performance when reading large amounts of text. The BufferedReader class extends the Reader class.

### BufferedReader Class Declaration

The following declaration shows how the BufferedReader class is defined:

[](https://www.tpointtech.com/java-bufferedreader-class#)[](https://www.tpointtech.com/java-bufferedreader-class#)[](https://www.tpointtech.com/java-bufferedreader-class#)

1. public class BufferedReader extends Reader  

## Constructors of BufferedReader Class

The BufferedReader class provides constructors to create a buffered character input stream.

### 1. BufferedReader(Reader rd)

This constructor creates a buffered reader that uses the default buffer size.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-bufferedreader-class#)[](https://www.tpointtech.com/java-bufferedreader-class#)[](https://www.tpointtech.com/java-bufferedreader-class#)

1. BufferedReader br = new BufferedReader(new FileReader("file.txt"));</textrea></div>  

2. <h3 class="h3">2. BufferedReader(Reader rd, int size)</h3>  

3. <p>This constructor creates a buffered reader with a specified buffer size.</p>  

4. <p><strong>Syntax:</strong></p>  

5. <p>Here is the syntax:</p>  

6. <div class="codeblock"><textarea class="Java" name="code">BufferedReader br = new BufferedReader(new FileReader("file.txt"), 1024);</textrea></div>  

7. <h3 class="h3">Example of BufferedReader Class Constructors</h3>  

8. <p>The following code shows how the constructors of the BufferedReader class are used.</p>  

9. <div class="codeblock"><textarea class="Java" name="code">BufferedReader br1 = new BufferedReader(new FileReader("file1.txt"));  
10. BufferedReader br2 = new BufferedReader(new FileReader("file2.txt"), 2048);  

## Methods of BufferedReader Class

The BufferedReader class provides methods to read character data efficiently.

|Method|Description|
|---|---|
|int read()|It is used for reading a single character.|
|int read(char[] cbuf, int off, int len)|It is used for reading characters into a portion of an [array](https://www.tpointtech.com/array-in-java).|
|boolean markSupported()|It is used to test the input stream support for the mark and reset method.|
|String readLine()|It is used for reading a line of text.|
|boolean ready()|It is used to test whether the input stream is ready to be read.|
|long skip(long n)|It is used for skipping the characters.|
|void reset()|It repositions the [stream](https://www.tpointtech.com/java-8-stream) at a position the mark method was last called on this input stream.|
|void mark(int readAheadLimit)|It is used for marking the present position in a stream.|
|void close()|It closes the input stream and releases any of the system resources associated with the stream.|

## Examples of Java BufferedReader Class

The following examples demonstrate different ways to read data using the Java BufferedReader class.

### Example 1: Reading Data from a File Using BufferedReader

The following example demonstrates how to read text from a file using the BufferedReader class.

[](https://www.tpointtech.com/java-bufferedreader-class#)[](https://www.tpointtech.com/java-bufferedreader-class#)[](https://www.tpointtech.com/java-bufferedreader-class#)

1. import java.io.*;  

2. public class BufferedReaderExample {  
3.     public static void main(String args[]) throws Exception {  
4.         FileReader fr = new FileReader("D:\\testout.txt");  
5.         BufferedReader br = new BufferedReader(fr);  

6.         int i;  
7.         while ((i = br.read()) != -1) {  
8.             System.out.print((char) i);  
9.         }  

10.         br.close();  
11.         fr.close();  
12.     }  
13. }  

**File Content (testout.txt):**

Welcome to TpointTech.

**Output:**

Welcome to TpointTech.

### Example 2: Reading Data from Console Using BufferedReader

The following example demonstrates how to read input from the console using InputStreamReader and BufferedReader.

[](https://www.tpointtech.com/java-bufferedreader-class#)[](https://www.tpointtech.com/java-bufferedreader-class#)[](https://www.tpointtech.com/java-bufferedreader-class#)

1. import java.io.*;  

2. public class BufferedReaderConsoleExample {  
3.     public static void main(String args[]) throws Exception {  
4.         InputStreamReader r = new InputStreamReader(System.in);  
5.         BufferedReader br = new BufferedReader(r);  

6.         System.out.println("Enter your name:");  
7.         String name = br.readLine();  
8.         System.out.println("Welcome " + name);  

9.         br.close();  
10.         r.close();  
11.     }  
12. }  

**Output:**

Enter your name:
Nakul Jain
Welcome Nakul Jain