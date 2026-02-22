The BufferedOutputStream class in Java is used to write data to an output stream efficiently by using an internal buffer.

In this chapter, we will learn what the BufferedOutputStream class is, why it is used, its declaration, constructors, methods, and how to write data to a file using an example.

## What is the BufferedOutputStream in Java?

The BufferedOutputStream class adds a buffering mechanism to an output stream. Instead of writing data directly to the destination, it first stores the data in a buffer and then writes it in larger chunks.

This buffering improves performance by reducing the number of write operations. It is commonly used with FileOutputStream.

## Adding Buffer to an OutputStream

The following syntax shows how to add buffering to an output stream:

[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)

1. OutputStream os= new BufferedOutputStream(new FileOutputStream("D:\\IO Package\\testout.txt"));  

## BufferedOutputStream Class Declaration

The following declaration shows how the BufferedOutputStream class is defined:

[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)

1. public class BufferedOutputStream extends FilterOutputStream  

## Constructors of BufferedOutputStream Class

The BufferedOutputStream class provides constructors to create a buffered output stream.

### 1. BufferedOutputStream(OutputStream out)

This constructor creates a buffered output stream using the specified output stream and a default buffer size.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)

1. BufferedOutputStream(OutputStream out)  

### 2. BufferedOutputStream(OutputStream out, int size)

This constructor creates a buffered output stream using the specified output stream with a custom buffer size.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)

1. BufferedOutputStream(OutputStream out, int size)  

### Example of BufferedOutputStream Constructors

This example creates a BufferedOutputStream using a FileOutputStream with the default buffer size.

[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)

1. import java.io.*;  

2. public class BufferedOutputStreamConstructorExample1 {  
3.     public static void main(String args[]) {  
4.         try {  
5.             FileOutputStream fout = new FileOutputStream("D:\\testout.txt");  
6.             BufferedOutputStream bout = new BufferedOutputStream(fout);  

7.             String data = "Default buffer example";  
8.             bout.write(data.getBytes());  

9.             bout.flush();  
10.             bout.close();  
11.             fout.close();  

12.             System.out.println("Data written successfully");  
13.         } catch (Exception e) {  
14.             System.out.println(e);  
15.         }  
16.     }  
17. }  

**Output:**

Data written successfully

**File Content (testout.txt):**

Default buffer example

## Methods of BufferedOutputStream Class

The BufferedOutputStream class provides methods to write data.

|Method|Description|
|---|---|
|void write(int b)|It writes the specified byte to the buffered output stream.|
|void write(byte[] b, int off, int len)|It write the bytes from the specified byte-input stream into a specified byte [array](https://www.tpointtech.com/array-in-java), starting with the given offset|
|void flush()|It flushes the buffered output stream.|

## Example of BufferedOutputStream Class

In this example, text data is written to a file using BufferedOutputStream. The flush() method sends buffered data to the file.

[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)[](https://www.tpointtech.com/java-bufferedoutputstream-class#)

1. package com.javatpoint;  
2. import java.io.*;  
3. public class BufferedOutputStreamExample{    
4. public static void main(String args[])throws Exception{    
5.      FileOutputStream fout=new FileOutputStream("D:\\testout.txt");    
6.      BufferedOutputStream bout=new BufferedOutputStream(fout);    
7.      String s="Welcome to javaTpoint.";    
8.      byte b[]=s.getBytes();    
9.      bout.write(b);    
10.      bout.flush();    
11.      bout.close();    
12.      fout.close();    
13.      System.out.println("success");    
14. }    
15. }  

**Output:**

Success

**testout.txt**

Welcome to javaTpoint.