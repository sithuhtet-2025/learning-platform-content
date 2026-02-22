# Java Writer

The Writer class in Java is an abstract class used for writing character streams.

In this chapter, we will learn what the Writer class is, why it is used, its declaration, constructors, important methods, and how it works using examples.

## What is Writer Class in Java?

The **Writer class** is an [abstract class](https://www.tpointtech.com/abstract-class-in-java) that is used to write data in the form of characters, and it is used as the base class for all character output stream classes.

It provides common methods for writing characters, strings, and character arrays. Subclasses such as FileWriter, BufferedWriter, and PrintWriter implement this class to provide concrete functionality.

## Java Writer Class Declaration

The following declaration shows how the Writer class is defined in Java.

[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)

1. public abstract class Writer  

## Fields of Writer Class

The Writer class provides a field used for synchronization.

|Modifier and Type|Field|Description|
|---|---|---|
|protected Object|lock|The object used to synchronize operations on this stream.|

## Constructors of Writer Class

The Writer class provides protected constructors that are used by its subclasses.

### 1. Writer()

This constructor creates a new character stream writer whose critical sections synchronize on the writer itself.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)

1. protected Writer()  

### 2. Writer(Object lock)

This constructor creates a new character stream writer whose critical sections synchronize on the specified lock object.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)

1. protected Writer(Object lock)  

### Example of Writer Class Constructors

The following example shows how the constructors of the Writer class are used indirectly through subclasses.

[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)

1. Writer w1 = new FileWriter("file1.txt");  
2. Writer w2 = new FileWriter("file2.txt");  

## Methods of Writer Class

The Writer class provides methods to write characters and strings.

|Modifier and Type|Method|Description|
|---|---|---|
|Writer|append(char c)|It appends the specified character to this writer.|
|Writer|append(CharSequence csq)|It appends the specified character sequence to this writer|
|Writer|append(CharSequence csq, int start, int end)|It appends a subsequence of the specified character sequence to this writer.|
|abstract void|close()|It closes the stream, flushing it first.|
|abstract void|flush()|It flushes the stream.|
|void|write(char[] cbuf)|It writes an [array](https://www.tpointtech.com/array-in-java) of characters.|
|abstract void|write(char[] cbuf, int off, int len)|It writes a portion of an array of characters.|
|void|write(int c)|It writes a single character.|
|void|write(String str)|It writes a [string](https://www.tpointtech.com/java-string).|
|void|write(String str, int off, int len)|It writes a portion of a string.|

## Examples of Java Writer Class

The following examples demonstrate how the Writer class is used through its subclasses.

### Example 1: Writing Text to a File Using FileWriter

This example demonstrates how to write text to a file using the FileWriter class, which is a subclass of Writer.

[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)

1. import java.io.*;  
2. public class WriterExample {  
3.     public static void main(String[] args) {  
4.         try {  
5.             Writer w = new FileWriter("output.txt");  
6.             String content = "I love my country";  
7.             w.write(content);  
8.             w.close();  
9.             System.out.println("Done");  
10.         } catch (IOException e) {  
11.             e.printStackTrace();  
12.         }  
13.     }  
14. }  

**Output:**

Done

**output.txt:**

I love my country

### Example 2: Writing Characters Using write(char[]) Method

This example demonstrates how to write a character array to a file using the Writer class.

[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)[](https://www.tpointtech.com/java-writer-class#)

1. import java.io.*;  

2. public class WriterCharArrayExample {  
3.     public static void main(String[] args) {  
4.         try {  
5.             Writer w = new FileWriter("output2.txt");  
6.             char[] data = {'J','a','v','a',' ','I','O'};  
7.             w.write(data);  
8.             w.close();  
9.             System.out.println("Characters written");  
10.         } catch (IOException e) {  
11.             e.printStackTrace();  
12.         }  
13.     }  
14. }  

**Output:**

Characters written