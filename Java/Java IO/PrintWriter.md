# Java PrintWriter Class

Last Updated : 12 Feb 2026

The PrintWriter class in Java is used to write formatted text representations of objects to a character output stream.

In this chapter, we will learn what the PrintWriter class is, why it is used, its declaration, constructors, important methods, and how to write formatted data to the console and files using examples.

## What is PrintWriter Class in Java?

The **PrintWriter class** is a character-based output stream that is used to print formatted representations of objects such as integers, doubles, strings, and other data types.

It simplifies writing text data by automatically handling line breaks and converting primitive data types into their textual form. The PrintWriter class also supports printf-style formatting and is often used with classes like FileWriter, BufferedWriter, or OutputStreamWriter to write data efficiently to files or other output destinations.

### PrintWriter Class Declaration

The following declaration shows how the PrintWriter class is defined:

[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)

1. public class PrintWriter extends Writer  

## Constructors of PrintWriter Class

The PrintWriter class provides multiple constructors to create a writer connected to different output destinations.

### 1. PrintWriter(Writer out)

This constructor creates a new PrintWriter that writes to the specified Writer.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)

1. PrintWriter pw = new PrintWriter(new FileWriter("file.txt"));  

### 2. PrintWriter(OutputStream out)

This constructor creates a new PrintWriter that writes to the specified output stream.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)

1. PrintWriter pw = new PrintWriter(System.out);  

### 3. PrintWriter(File file)

This constructor creates a new PrintWriter that writes to the specified file.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)

1. PrintWriter pw = new PrintWriter(new File("file.txt"));  

### 4. PrintWriter(String fileName)

This constructor creates a new PrintWriter that writes to the file specified by its name.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)

1. PrintWriter pw = new PrintWriter("file.txt");  

### Example of PrintWriter Class Constructors

The following code shows how the constructors of the PrintWriter class are used.

[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)

1. PrintWriter p1 = new PrintWriter(System.out);  
2. PrintWriter p2 = new PrintWriter(new File("data.txt"));  

## Methods of PrintWriter Class

The PrintWriter class provides methods to print and format text data.

|Method|Description|
|---|---|
|void println(boolean x)|It is used to print the boolean value.|
|void println(char[] x)|It is used to print an [array](https://www.tpointtech.com/array-in-java) of characters.|
|void println(int x)|It is used to print an integer.|
|PrintWriter append(char c)|It is used to append the specified character to the writer.|
|PrintWriter append(CharSequence ch)|It is used to append the specified character sequence to the writer.|
|PrintWriter append(CharSequence ch, int start, int end)|It is used to append a subsequence of specified character to the writer.|
|boolean checkError()|It is used to flushes the stream and check its error state.|
|protected void setError()|It is used to indicate that an error occurs.|
|protected void clearError()|It is used to clear the error state of a stream.|
|PrintWriter format(String format, Object... args)|It is used to write a formatted [string](https://www.tpointtech.com/java-string) to the writer using specified arguments and format string.|
|void print(Object obj)|It is used to print an object.|
|void flush()|It is used to flushes the stream.|
|void close()|It is used to close the stream.|
|**void println(double x)**|Prints a double value.|
|**void println(float x)**|Prints a float value.|
|**void println(long x)**|Prints a long value.|
|**void println(String x)**|Prints a string.|
|**void write(char[] buf)**|Writes an array of characters.|
|**void write(char[] buf, int off, int len)**|Writes a portion of an array of characters.|
|**void write(int c)**|Writes a single character.|
|**void write(String s)**|Writes a string.|
|**void write(String s, int off, int len)**|Writes a portion of a string.|
|**PrintWriter format(Locale l, String format, Object... args)**|Writes a formatted string to the writer using the specified locale, format string, and arguments.|
|**PrintWriter printf(String format, Object... args)**|Writes a formatted string to the writer using the specified format string and arguments.|

## Examples of Java PrintWriter Class

The following examples demonstrate how to use the Java PrintWriter class.

### Example 1: Writing Data to Console and File Using PrintWriter

The following example demonstrates how to write text to the console and a file using the PrintWriter class.

[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)

1. import java.io.File;  
2. import java.io.PrintWriter;  

3. public class PrintWriterExample {  
4.     public static void main(String[] args) throws Exception {  

5.         // Writing data to console  
6.         PrintWriter writer = new PrintWriter(System.out);  
7.         writer.write("TpointTech provides tutorials of all technology.");  
8.         writer.flush();  
9.         writer.close();  

10.         // Writing data to file  
11.         PrintWriter writer1 = new PrintWriter(new File("D:\\testout.txt"));  
12.         writer1.write("Like Java, Spring, Hibernate, Android, PHP etc.");  
13.         writer1.flush();  
14.         writer1.close();  
15.     }  
16. }  

**Output**

TpointTech provides tutorials of all technology.

**File Content (testout.txt):**

Like Java, Spring, Hibernate, Android, PHP etc.

**Explanation**

The PrintWriter class in Java is used by this code to write data to a file and the console. Text can be printed to the console by first constructing a PrintWriter object called writer, which is connected to the standard output stream.

To guarantee quick output, the println method publishes the given string to the console and then flushes it. Any system resources utilised by the PrintWriter are released using the shut function. Then, a new File object called "testout.txt" is attached to another PrintWriter, writer1, so that data can be written to that file in the current directory. Println, flush, and close methods are used to write the string to the file, guarantee that data is written instantly, and release resources in accordance with console output.

### Example 2: Using printf() Method with PrintWriter

The following example demonstrates how to print formatted output using the printf() method of the PrintWriter class.

[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)[](https://www.tpointtech.com/java-printwriter-class#)

1. import java.io.PrintWriter;  

2. public class PrintWriterPrintfExample {  
3.     public static void main(String[] args) {  

4.         PrintWriter pw = new PrintWriter(System.out);  
5.         int count = 10;  
6.         double price = 99.99;  

7.         pw.printf("Count: %d, Price: %.2f", count, price);  
8.         pw.flush();  
9.         pw.close();  
10.     }  
11. }  

**Output**

Count: 10, Price: 99.99