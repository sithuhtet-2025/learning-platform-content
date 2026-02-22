# Java FileWriter Class

Last Updated : 12 Feb 2026

The FileWriter class in Java is used to write character-oriented data directly into a file.

In this chapter, we will learn what the FileWriter class is, why it is used, its declaration, constructors, important methods, and how to write character data to files using examples.

## What is FileWriter Class in Java?

The **FileWriter class** is a character-based output stream that is used to write text data to a file, and it is commonly used for file handling in Java.

Unlike the [FileOutputStream class](https://www.tpointtech.com/java-fileoutputstream-class), FileWriter allows writing [strings](https://www.tpointtech.com/java-string) and characters directly without converting them into byte arrays, which makes it easier to use for character-oriented data.

## Java FileWriter Class Declaration

The following declaration shows how the FileWriter class is defined:

[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)

1. public class FileWriter extends OutputStreamWriter  

## Constructors of FileWriter Class

The FileWriter class provides constructors to create and write data to files.

### 1. FileWriter(String file)

This constructor creates a new file using the specified file name in string format.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)

1. FileWriter fw = new FileWriter("filename.txt");  

### 2. FileWriter(File file)

This constructor creates a new file using a File object.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)

1. FileWriter fw = new FileWriter(new File("filename.txt"));  

### Example of FileWriter Class Constructors

The following example demonstrates how the constructors of the FileWriter class are used.

[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)

1. FileWriter fw1 = new FileWriter("file1.txt");  
2. FileWriter fw2 = new FileWriter(new File("file2.txt"));  

## Methods of FileWriter Class

The FileWriter class provides methods to write character data into a file.

|Method|Description|
|---|---|
|void write(String text)|It is used to write the string into FileWriter.|
|void write(char c)|It is used to write the char into FileWriter.|
|void write(char[] c)|It is used to write char array into FileWriter.|
|void flush()|It is used to flushes the data of FileWriter.|
|void close()|It is used to close the FileWriter.|

## Examples of Java FileWriter Class

The following examples demonstrate how to write data to a file using the FileWriter class.

### Example 1: Writing a String to a File

This example demonstrates how to write a string directly into a file using the FileWriter class.

[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)

1. import java.io.FileWriter;  

2. public class FileWriterExample {  
3.     public static void main(String args[]) {  
4.         try {  
5.             FileWriter fw = new FileWriter("D:\\testout.txt");  
6.             fw.write("Welcome to TpointTech.");  
7.             fw.close();  
8.             System.out.println("Success...");  
9.         } catch (Exception e) {  
10.             System.out.println(e);  
11.         }  
12.     }  
13. }  

**Output:**

Success...

**File Content (testout.txt):**

Welcome to TpointTech.

### Example 2: Writing Character Array to a File

This example demonstrates how to write a character array into a file using the FileWriter class.

[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)[](https://www.tpointtech.com/java-filewriter-class#)

1. import java.io.FileWriter;  

2. public class FileWriterCharExample {  
3.     public static void main(String args[]) {  
4.         try {  
5.             FileWriter fw = new FileWriter("D:\\testout2.txt");  
6.             char[] data = {'J','a','v','a',' ','I','O'};  
7.             fw.write(data);  
8.             fw.close();  
9.             System.out.println("Characters written successfully");  
10.         } catch (Exception e) {  
11.             System.out.println(e);  
12.         }  
13.     }  
14. }  

**Output:**

Characters written successfully

**File Content (testout2.txt):**

Java IO