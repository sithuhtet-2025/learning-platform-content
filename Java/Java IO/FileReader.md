# Java FileReader Class

Last Updated : 12 Feb 2026

The FileReader class in Java is used to read character-oriented data from a file.

In this chapter, we will learn what the FileReader class is, why it is used, its declaration, constructors, important methods, and how to read data from files using examples.

## What is FileReader Class in Java?

The **FileReader class** is a character-based input stream that is used to read data from a file, and it is commonly used for file handling in Java.

It reads data character by character and internally uses byte streams to decode characters. Unlike FileInputStream, FileReader is suitable for reading text data rather than raw binary data.

## Java FileReader Class Declaration

The following declaration shows how the FileReader class is defined in Java.

[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)

1. public class FileReader extends InputStreamReader  

## Constructors of FileReader Class

The FileReader class provides constructors to open files in read mode.

### 1. FileReader(String file)

This constructor opens the specified file using the file name provided as a string. If the file does not exist, it throws FileNotFoundException.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)

1. FileReader fr = new FileReader("filename.txt");  

### 2. FileReader(File file)

This constructor opens the specified file using a File object. If the file does not exist, it throws FileNotFoundException.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)

1. FileReader fr = new FileReader(new File("filename.txt"));  

### Example of FileReader Class Constructors

The following code shows how the constructors of the FileReader class are used.

[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)

1. FileReader fr1 = new FileReader("file1.txt");  
2. FileReader fr2 = new FileReader(new File("file2.txt"));  

## Methods of FileReader class

The FileReader class provides methods to read character data from a file.

|Method|Description|
|---|---|
|int read()|It is used to return a character in ASCII form. It returns -1 at the end of file.|
|void close()|It is used to close the FileReader class.|

## Examples of Java FileReader Class

The following examples demonstrate how to read data from a file using the FileReader class.

### Example 1: Reading File Character by Character

The following example demonstrates how to read a text file character by character using the FileReader class.

[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)

1. import java.io.FileReader;  

2. public class FileReaderExample {  
3.     public static void main(String args[]) throws Exception {  
4.         FileReader fr = new FileReader("D:\\testout.txt");  
5.         int i;  
6.         while ((i = fr.read()) != -1) {  
7.             System.out.print((char) i);  
8.         }  
9.         fr.close();  
10.     }  
11. }  

**File Content (testout.txt):**

Welcome to TpointTech.

**Output:**

Welcome to TpointTech.

### Example 2: Reading File Using File Object

The following example demonstrates how to read data from a file using a File object with the FileReader class.

[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)[](https://www.tpointtech.com/java-filereader-class#)

1. import java.io.File;  
2. import java.io.FileReader;  

3. public class FileReaderFileObjectExample {  
4.     public static void main(String args[]) throws Exception {  
5.         File file = new File("D:\\testout.txt");  
6.         FileReader fr = new FileReader(file);  
7.         int ch;  
8.         while ((ch = fr.read()) != -1) {  
9.             System.out.print((char) ch);  
10.         }  
11.         fr.close();  
12.     }  
13. }  

**Output:**

Welcome to TpointTech.