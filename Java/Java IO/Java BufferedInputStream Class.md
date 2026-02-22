The BufferedInputStream class in Java is used to read data from an input stream efficiently by using an internal buffer.

In this chapter, we will learn what the BufferedInputStream class is, why it is used, its constructors, important methods, and how to read data from a file using an example.

## What is BufferedInputStream in Java?

The **BufferedInputStream** class is used to read data from an input stream with better performance. It uses an internal buffer to store data temporarily, which reduces the number of read operations from the underlying input stream.

When data is read or skipped, the buffer is automatically refilled with multiple bytes at once. This makes input operations faster compared to reading data byte by byte directly from the stream.

## Java BufferedInputStream class declaration

Let's see the declaration for Java.io.BufferedInputStream class:

[](https://www.tpointtech.com/java-bufferedinputstream-class#)[](https://www.tpointtech.com/java-bufferedinputstream-class#)[](https://www.tpointtech.com/java-bufferedinputstream-class#)

1. public class BufferedInputStream extends FilterInputStream  

## Constructors of BufferedInputStream Class

The BufferedInputStream class provides constructors to create a buffered input stream with or without a custom buffer size.

### 1. BufferedInputStream(InputStream in)

This constructor creates a BufferedInputStream using the specified input stream and a default buffer size.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-bufferedinputstream-class#)[](https://www.tpointtech.com/java-bufferedinputstream-class#)[](https://www.tpointtech.com/java-bufferedinputstream-class#)

1. BufferedInputStream(InputStream in)  

### 2. BufferedInputStream(InputStream in, int size)

This constructor creates a BufferedInputStream using the specified input stream and a custom buffer size.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-bufferedinputstream-class#)[](https://www.tpointtech.com/java-bufferedinputstream-class#)[](https://www.tpointtech.com/java-bufferedinputstream-class#)

1. BufferedInputStream(InputStream in, int size)  

### Example of BufferedInputStream Constructors

The following examples demonstrate how to create a BufferedInputStream using its constructors.

[](https://www.tpointtech.com/java-bufferedinputstream-class#)[](https://www.tpointtech.com/java-bufferedinputstream-class#)[](https://www.tpointtech.com/java-bufferedinputstream-class#)

1. import java.io.*;  

2. public class BufferedInputStreamConstructorExample1 {  
3.     public static void main(String args[]) {  
4.         try {  
5.             FileInputStream fin = new FileInputStream("D:\\testout.txt");  
6.             BufferedInputStream bin = new BufferedInputStream(fin);  

7.             int i;  
8.             while ((i = bin.read()) != -1) {  
9.                 System.out.print((char) i);  
10.             }  

11.             bin.close();  
12.             fin.close();  
13.         } catch (Exception e) {  
14.             System.out.println(e);  
15.         }  
16.     }  
17. }  

**Output:**

TpointTech

## Java BufferedInputStream class methods

The BufferedInputStream class provides several methods to read data.

|Method|Description|
|---|---|
|int available()|It returns an estimate number of bytes that can be read from the input stream without blocking by the next invocation method for the input stream.|
|int read()|It read the next byte of data from the input stream.|
|int read(byte[] b, int off, int ln)|It read the bytes from the specified byte-input stream into a specified byte array, starting with the given offset.|
|void close()|It closes the input stream and releases any of the system resources associated with the stream.|
|void reset()|It repositions the stream at a position the mark method was last called on this input stream.|
|void mark(int readlimit)|It sees the general contract of the mark method for the input stream.|
|long skip(long x)|It skips over and discards x bytes of data from the input stream.|
|boolean markSupported()|It tests for the input stream to support the mark and reset methods.|

## Example of BufferedInputStream Class

In this example, data is read from a file using BufferedInputStream, which improves performance by reading data through a buffer.

[](https://www.tpointtech.com/java-bufferedinputstream-class#)[](https://www.tpointtech.com/java-bufferedinputstream-class#)[](https://www.tpointtech.com/java-bufferedinputstream-class#)

1. package com.javatpoint;  

2. import java.io.*;  
3. public class BufferedInputStreamExample{    
4.  public static void main(String args[]){    
5.   try{    
6.     FileInputStream fin=new FileInputStream("D:\\testout.txt");    
7.     BufferedInputStream bin=new BufferedInputStream(fin);    
8.     int i;    
9.     while((i=bin.read())!=-1){    
10.      System.out.print((char)i);    
11.     }    
12.     bin.close();    
13.     fin.close();    
14.   }catch(Exception e){System.out.println(e);}    
15.  }    
16. }  

Here, we are assuming that you have following data in **"testout.txt"** file:

javaTpoint

**Output:**

javaTpoint