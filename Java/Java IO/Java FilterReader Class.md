
Java FilterReader class is an abstract class used to read filtered character streams.

In this chapter, we will learn what the FilterReader class is, why it is used, its declaration, constructors, methods, and examples to understand how filtering works on character input streams.

## What is FilterReader Class in Java?

The FilterReader class is a character input stream that wraps another Reader and filters the data read from it.

It provides default implementations that simply pass all read requests to the underlying reader. Subclasses of FilterReader override one or more methods to modify or filter the data before it is returned to the caller.

FilterReader is mainly used when we want to transform, validate, or modify character data while reading it from an input source such as a file or string.

## FilterReader Class Declaration

The FilterReader class is a part of the java.io package and extends the Reader class.

[](https://www.tpointtech.com/java-filterreader-class#)[](https://www.tpointtech.com/java-filterreader-class#)[](https://www.tpointtech.com/java-filterreader-class#)

1. public abstract class FilterReader extends Reader  

## Fields of FilterReader Class

The field of FilterReader class is as follows:

|Modifier|Type|Field|Description|
|---|---|---|---|
|protected|Reader|in|The underlying character-input stream.|

## Constructors of FilterReader Class

The FilterReader class provides a protected constructor that is used by its subclasses.

### FilterReader(Reader in)

This constructor creates a new filtered reader that wraps the specified reader.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-filterreader-class#)[](https://www.tpointtech.com/java-filterreader-class#)[](https://www.tpointtech.com/java-filterreader-class#)

1. FilterReader filterReader = new CustomFilterReader(reader);  

### Example of FilterReader Class Constructor

The following example demonstrates how a FilterReader subclass is created using the constructor.

[](https://www.tpointtech.com/java-filterreader-class#)[](https://www.tpointtech.com/java-filterreader-class#)[](https://www.tpointtech.com/java-filterreader-class#)

1. Reader reader = new FileReader("input.txt");  
2. FilterReader filterReader = new CustomFilterReader(reader);  

## Methods of FilterReader Class

The FilterReader class provides the following methods to read and manage character streams.

|Modifier and Type|Method|Description|
|---|---|---|
|void|close()|It closes the stream and releases any system resources associated with it.|
|void|mark(int readAheadLimit)|It marks the present position in the stream.|
|boolean|markSupported()|It tells whether this stream supports the mark() operation.|
|boolean|ready()|It tells whether this stream is ready to be read.|
|int|read()|It reads a single character.|
|int|read(char[] cbuf, int off, int len)|It reads characters into a portion of an [array](https://www.tpointtech.com/array-in-java).|
|void|reset()|It resets the stream.|
|long|skip(long n)|It skips characters.|

## Examples of Java FilterReader Class

Practice the following examples to understand how the FilterReader class works in real scenarios.

### Example 1: Replacing Spaces with Question Mark

The following example demonstrates how a custom FilterReader replaces spaces with a question mark (?) while reading data from a file.

[](https://www.tpointtech.com/java-filterreader-class#)[](https://www.tpointtech.com/java-filterreader-class#)[](https://www.tpointtech.com/java-filterreader-class#)

1. import java.io.*;  

2. class CustomFilterReader extends FilterReader {  

3.     CustomFilterReader(Reader in) {  
4.         super(in);  
5.     }  

6.     public int read() throws IOException {  
7.         int ch = super.read();  
8.         if (ch == ' ') {  
9.             return '?';  
10.         }  
11.         return ch;  
12.     }  
13. }  

14. public class FilterReaderExample1 {  
15.     public static void main(String[] args) {  
16.         try {  
17.             Reader reader = new FileReader("javaFile123.txt");  
18.             CustomFilterReader fr = new CustomFilterReader(reader);  

19.             int i;  
20.             while ((i = fr.read()) != -1) {  
21.                 System.out.print((char) i);  
22.             }  

23.             fr.close();  
24.             reader.close();  

25.         } catch (Exception e) {  
26.             System.out.println(e);  
27.         }  
28.     }  
29. }  

**File Content (javaFile123.txt):**

India is my country

**Output:**

India?is?my?country

### Example 2: Converting Characters to Uppercase While Reading

The following example demonstrates how a custom FilterReader converts all characters to uppercase while reading data from a file.

[](https://www.tpointtech.com/java-filterreader-class#)[](https://www.tpointtech.com/java-filterreader-class#)[](https://www.tpointtech.com/java-filterreader-class#)

1. import java.io.*;  

2. class UpperCaseFilterReader extends FilterReader {  

3.     UpperCaseFilterReader(Reader in) {  
4.         super(in);  
5.     }  

6.     public int read() throws IOException {  
7.         int ch = super.read();  
8.         if (ch == -1) {  
9.             return ch;  
10.         }  
11.         return Character.toUpperCase((char) ch);  
12.     }  
13. }  

14. public class FilterReaderExample2 {  
15.     public static void main(String[] args) {  
16.         try {  
17.             Reader reader = new FileReader("input.txt");  
18.             UpperCaseFilterReader fr = new UpperCaseFilterReader(reader);  

19.             int c;  
20.             while ((c = fr.read()) != -1) {  
21.                 System.out.print((char) c);  
22.             }  

23.             fr.close();  
24.             reader.close();  

25.         } catch (Exception e) {  
26.             System.out.println(e);  
27.         }  
28.     }  
29. }  

**File Content (input.txt):**

Java FilterReader Example

**Output:**

JAVA FILTERREADER EXAMPLE