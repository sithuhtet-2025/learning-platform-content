Java **FilterWriter** class is an abstract class that is used to write filtered character streams.

In this chapter, we will learn what the FilterWriter class is, why it is used, its declaration, fields, constructors, methods, and examples to understand how it works in Java I/O.

## What is FilterWriter Class in Java?

The **FilterWriter class** is an abstract character output stream that wraps another Writer object to provide filtered or modified output.

It is mainly used as a base class for creating custom writer classes. Subclasses of FilterWriter override one or more writing methods to modify the data before writing it to the underlying writer. Classes like BufferedWriter internally use this concept to add extra functionality.

## FilterWriter Class Declaration

The FilterWriter class is a part of the java.io package and extends the Writer class.

[](https://www.tpointtech.com/java-filterwriter-class#)[](https://www.tpointtech.com/java-filterwriter-class#)[](https://www.tpointtech.com/java-filterwriter-class#)

1. public abstract class FilterWriter extends Writer  

## Fields of FilterWriter Class

- **out** – The underlying character-output stream on which filtered output is written.

## Constructors of FilterWriter Class

The FilterWriter class provides a protected constructor that is used by its subclasses.

### FilterWriter(Writer out)

This constructor creates a FilterWriter object that wraps the specified Writer.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-filterwriter-class#)[](https://www.tpointtech.com/java-filterwriter-class#)[](https://www.tpointtech.com/java-filterwriter-class#)

1. FilterWriter fw = new FilterWriter(writer);  

> **Note:**Since FilterWriter is an abstract class, it cannot be instantiated directly. This constructor is used inside subclasses.

### Example of FilterWriter Class Constructor

The following example demonstrates how a custom class extends FilterWriter and uses its constructor.

[](https://www.tpointtech.com/java-filterwriter-class#)[](https://www.tpointtech.com/java-filterwriter-class#)[](https://www.tpointtech.com/java-filterwriter-class#)

1. class CustomFilterWriter extends FilterWriter {  
2.     CustomFilterWriter(Writer out) {  
3.         super(out);  
4.     }  
5. }  

## Methods of FilterWriter Class

The FilterWriter class provides the following commonly used methods:

|Modifier and Type|Method|Description|
|---|---|---|
|void|close()|It closes the stream, flushing it first.|
|void|flush()|It flushes the stream.|
|void|write(char[] cbuf, int off, int len)|It writes a portion of an [array](https://www.tpointtech.com/array-in-java) of characters.|
|void|write(int c)|It writes a single character.|
|void|write(String str, int off, int len)|It writes a portion of a [string](https://www.tpointtech.com/java-string).|

## Examples of Java FilterWriter Class

Practice the following examples to understand the concept and usage of the FilterWriter class.

### Example 1: Writing Filtered Data Using Custom FilterWriter

The following example demonstrates how to create a custom FilterWriter that converts text to lowercase before writing it to a file.

[](https://www.tpointtech.com/java-filterwriter-class#)[](https://www.tpointtech.com/java-filterwriter-class#)[](https://www.tpointtech.com/java-filterwriter-class#)

1. import java.io.*;  

2. class CustomFilterWriter extends FilterWriter {  
3.     CustomFilterWriter(Writer out) {  
4.         super(out);  
5.     }  

6.     public void write(String str) throws IOException {  
7.         super.write(str.toLowerCase());  
8.     }  
9. }  

10. public class FilterWriterExample {  
11.     public static void main(String[] args) {  
12.         try {  
13.             FileWriter fw = new FileWriter("Record.txt");  
14.             CustomFilterWriter filterWriter = new CustomFilterWriter(fw);  

15.             filterWriter.write("I LOVE MY COUNTRY");  
16.             filterWriter.close();  

17.             FileReader fr = new FileReader("Record.txt");  
18.             BufferedReader br = new BufferedReader(fr);  

19.             int k;  
20.             while ((k = br.read()) != -1) {  
21.                 System.out.print((char) k);  
22.             }  
23.             br.close();  

24.         } catch (IOException e) {  
25.             e.printStackTrace();  
26.         }  
27.     }  
28. }  

**Output:**

i love my country

While running the current program if the current working directory does not contain the file, a new file is created and CustomFileWriter will write the text "I LOVE MY COUNTRY" in lowercase to the file.

### Example 2: Using FilterWriter to Modify Text Before Writing to File

The following example demonstrates how a custom FilterWriter modifies data before writing it to a file.

Here, the custom writer converts all characters to lowercase before storing them in the file.

[](https://www.tpointtech.com/java-filterwriter-class#)[](https://www.tpointtech.com/java-filterwriter-class#)[](https://www.tpointtech.com/java-filterwriter-class#)

1. import java.io.*;  

2. class CustomFilterWriter extends FilterWriter {  

3.     CustomFilterWriter(Writer out) {  
4.         super(out);  
5.     }  

6.     // Override write method to filter data  
7.     public void write(String str) throws IOException {  
8.         super.write(str.toLowerCase());  
9.     }  
10. }  

11. public class FilterWriterExample2 {  
12.     public static void main(String[] args) {  
13.         try {  
14.             // Create FileWriter  
15.             FileWriter fw = new FileWriter("output.txt");  

16.             // Wrap FileWriter with CustomFilterWriter  
17.             CustomFilterWriter filterWriter = new CustomFilterWriter(fw);  

18.             // Write data  
19.             filterWriter.write("JAVA FILTERWRITER SECOND EXAMPLE");  

20.             // Close writer  
21.             filterWriter.close();  

22.             // Read and display file content  
23.             FileReader fr = new FileReader("output.txt");  
24.             BufferedReader br = new BufferedReader(fr);  

25.             int ch;  
26.             while ((ch = br.read()) != -1) {  
27.                 System.out.print((char) ch);  
28.             }  

29.             br.close();  

30.         } catch (IOException e) {  
31.             e.printStackTrace();  
32.         }  
33.     }  
34. }  

**Output:**

java filterwriter second example