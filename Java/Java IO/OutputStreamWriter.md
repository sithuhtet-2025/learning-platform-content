# Java OutputStreamWriter Class

The OutputStreamWriter class in Java is used to convert a character stream into a byte stream using a specified character encoding.

In this chapter, we will learn what the OutputStreamWriter class is, why it is used, its declaration, constructors, important methods, and how to write character data to byte streams using examples.

## What is OutputStreamWriter Class in Java?

The **OutputStreamWriter class** acts as a bridge between character streams and byte streams, and it is used to encode characters into bytes using a specified charset.

When the write() method is called, characters are converted into bytes using an encoding converter and then written to the underlying output stream. To improve performance and avoid frequent encoding operations, OutputStreamWriter is commonly used with [BufferedWriter](https://www.tpointtech.com/java-bufferedwriter-class).

## Java OutputStreamWriter Class Declaration

The following declaration shows how the OutputStreamWriter class is defined:

[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)

1. public class OutputStreamWriter extends Writer  

## Constructors of OutputStreamWriter Class

The OutputStreamWriter class provides constructors to create a writer with different character encodings.

### 1. OutputStreamWriter(OutputStream out)

This constructor creates an OutputStreamWriter that uses the default character encoding.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)

1. Writer writer = new OutputStreamWriter(new FileOutputStream("file.txt"));  

### 2. OutputStreamWriter(OutputStream out, Charset cs)

This constructor creates an OutputStreamWriter that uses the specified charset.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)

1. Writer writer = new OutputStreamWriter(new FileOutputStream("file.txt"), StandardCharsets.UTF_8);  

### 3. OutputStreamWriter(OutputStream out, CharsetEncoder enc)

This constructor creates an OutputStreamWriter that uses the specified charset encoder.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)

1. Writer writer = new OutputStreamWriter(new FileOutputStream("file.txt"), charsetEncoder);  

### 4. OutputStreamWriter(OutputStream out, String charsetName)

This constructor creates an OutputStreamWriter that uses the named charset.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)

1. Writer writer = new OutputStreamWriter(new FileOutputStream("file.txt"), "UTF-8");  

### Example of OutputStreamWriter Class Constructors

The following code shows how the constructors of the OutputStreamWriter class are used.

[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)

1. Writer w1 = new OutputStreamWriter(new FileOutputStream("a.txt"));  
2. Writer w2 = new OutputStreamWriter(new FileOutputStream("b.txt"), "UTF-8");  

## Methods of OutputStreamWriter Class

The OutputStreamWriter class provides the following methods to write encoded character data.

|Modifier and Type|Method|Description|
|---|---|---|
|void|close()|It closes the stream, flushing it first.|
|void|flush()|It flushes the stream.|
|String|getEncoding()|It returns the name of the character encoding being used by this stream.|
|void|write(char[] cbuf, int off, int len)|It writes a portion of an [array](https://www.tpointtech.com/array-in-java) of characters.|
|void|write(int c)|It writes a single character.|
|void|write(String str, int off, int len)|It writes a portion of a [string](https://www.tpointtech.com/java-string).|

## Examples of Java OutputStreamWriter Class

The following examples demonstrate how to use the Java OutputStreamWriter class.

### Example 1: Writing Text to a File Using OutputStreamWriter

The following example demonstrates how to write character data to a file using the OutputStreamWriter class.

[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)

1. import java.io.*;  

2. public class OutputStreamWriterExample {  
3.     public static void main(String[] args) {  
4.         try {  
5.             OutputStream outputStream = new FileOutputStream("output.txt");  
6.             Writer writer = new OutputStreamWriter(outputStream);  

7.             writer.write("Hello World");  
8.             writer.close();  
9.         } catch (Exception e) {  
10.             System.out.println(e);  
11.         }  
12.     }  
13. }  

**Output:**

Hello World

### Example 2: Writing Data Using UTF-8 Encoding

The following example demonstrates how to write text using a specific character encoding with the OutputStreamWriter class.

[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)[](https://www.tpointtech.com/java-outputstreamwriter-class#)

1. import java.io.*;  
2. import java.nio.charset.StandardCharsets;  

3. public class OutputStreamWriterUTF8Example {  
4.     public static void main(String[] args) throws Exception {  
5.         Writer writer = new OutputStreamWriter(  
6.                 new FileOutputStream("utf8.txt"),  
7.                 StandardCharsets.UTF_8  
8.         );  

9.         writer.write("Java I/O – UTF-8 Example");  
10.         writer.close();  
11.     }  
12. }  

**Output:**

Java I/O – UTF-8 Example