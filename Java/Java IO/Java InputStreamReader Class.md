The InputStreamReader class in Java is used to convert byte streams into character streams using a specified character encoding.

In this chapter, we will understand what the InputStreamReader class is, why it is used, its declaration, constructors, important methods, and how to read character data from byte streams using examples.

## What is InputStreamReader Class in Java?

The **InputStreamReader class** acts as a bridge between byte streams and character streams. It reads raw bytes from an input stream and decodes them into characters using a specified charset.

The character encoding can be explicitly defined, provided through a decoder, or taken from the platform’s default charset. InputStreamReader is commonly used when reading text data from files, sockets, or other byte-based sources.

## InputStreamReader Class Declaration

The following declaration shows how the InputStreamReader class is defined:

[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)

1. public class InputStreamReader extends Reader  

## Constructors of InputStreamReader Class

The InputStreamReader class provides multiple constructors to handle different character encodings.

### 1. InputStreamReader(InputStream in)

This constructor creates an InputStreamReader that uses the platform’s default character encoding.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)

1. Reader reader = new InputStreamReader(new FileInputStream("file.txt"));  

### 2. InputStreamReader(InputStream in, Charset cs)

This constructor creates an InputStreamReader that uses the specified charset.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)

1. Reader reader = new InputStreamReader(  
2.         new FileInputStream("file.txt"),  
3.         StandardCharsets.UTF_8  
4. );  

### 3. InputStreamReader(InputStream in, CharsetDecoder dec)

This constructor creates an InputStreamReader that uses the given charset decoder.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)

1. Reader reader = new InputStreamReader(inputStream, charsetDecoder);  

### 4. InputStreamReader(InputStream in, String charsetName)

This constructor creates an InputStreamReader that uses the named charset.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)

1. Reader reader = new InputStreamReader(new FileInputStream("file.txt"), "UTF-8");  

### Example of InputStreamReader Class Constructors

The following code shows how different constructors of the InputStreamReader class can be used.

[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)

1. Reader r1 = new InputStreamReader(new FileInputStream("a.txt"));  
2. Reader r2 = new InputStreamReader(new FileInputStream("b.txt"), "UTF-8");  

## Methods of InputStreamReader Class

The InputStreamReader class provides the following methods to read decoded character data.

|Modifier and Type|Method|Description|
|---|---|---|
|void|close()|It closes the stream and releases any system resources associated with it.|
|String|getEncoding()|It returns the name of the character encoding being used by this stream.|
|int|read()|It reads a single character.|
|int|read(char[] cbuf, int offset, int length)|It reads characters into a portion of an [array](https://www.tpointtech.com/array-in-java).|
|boolean|ready()|It tells whether this stream is ready to be read.|

## Examples of Java InputStreamReader Class

The following examples demonstrate how to use the Java InputStreamReader class.

### Example 1: Reading Data from a File Using InputStreamReader

The following example demonstrates how to read character data from a file using the InputStreamReader class.

[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)

1. import java.io.*;  

2. public class InputStreamReaderExample {  
3.     public static void main(String[] args) {  
4.         try {  
5.             InputStream stream = new FileInputStream("file.txt");  
6.             Reader reader = new InputStreamReader(stream);  

7.             int data = reader.read();  
8.             while (data != -1) {  
9.                 System.out.print((char) data);  
10.                 data = reader.read();  
11.             }  
12.             reader.close();  
13.         } catch (Exception e) {  
14.             e.printStackTrace();  
15.         }  
16.     }  
17. }  

**Output:**

I love my country

### Example 2: Reading File Data Using UTF-8 Encoding

The following example demonstrates how to read text using a specific character encoding with the InputStreamReader class.

[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)[](https://www.tpointtech.com/java-inputstreamreader-class#)

1. import java.io.*;  
2. import java.nio.charset.StandardCharsets;  

3. public class InputStreamReaderUTF8Example {  
4.     public static void main(String[] args) throws Exception {  
5.         Reader reader = new InputStreamReader(  
6.                 new FileInputStream("file.txt"),  
7.                 StandardCharsets.UTF_8  
8.         );  

9.         int ch;  
10.         while ((ch = reader.read()) != -1) {  
11.             System.out.print((char) ch);  
12.         }  
13.         reader.close();  
14.     }  
15. }  

**Output:**

I love my country