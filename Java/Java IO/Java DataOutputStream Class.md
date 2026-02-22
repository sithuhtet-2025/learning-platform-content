The DataOutputStream class in Java is used to write primitive data types to an output stream in a machine-independent format.

In this chapter, we will learn what the DataOutputStream class is, why it is used, its declaration, constructors, important methods, and how to write primitive data to a file using an example.

## What is DataOutputStream in Java?

The DataOutputStream class allows a Java application to write primitive data types such as int, char, boolean, and String to an output stream in a portable way.

The data written using DataOutputStream can later be read correctly using a DataInputStream. This makes it useful when data needs to be shared between different systems or programs.

## DataOutputStream Class Declaration

The following declaration shows how the DataOutputStream class is defined:

[](https://www.tpointtech.com/java-dataoutputstream-class#)[](https://www.tpointtech.com/java-dataoutputstream-class#)[](https://www.tpointtech.com/java-dataoutputstream-class#)

1. public class DataOutputStream extends FilterOutputStream implements DataOutput  

## Constructors of DataOutputStream Class

The DataOutputStream class provides a constructor to create a data output stream.

### 1. DataOutputStream(OutputStream out)

This constructor creates a new DataOutputStream that writes data to the specified output stream.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-dataoutputstream-class#)[](https://www.tpointtech.com/java-dataoutputstream-class#)[](https://www.tpointtech.com/java-dataoutputstream-class#)

1. DataOutputStream(OutputStream out)  

### Example of DataOutputStream Class Constructor

The following example demonstrates how to create a DataOutputStream using its constructor.

[](https://www.tpointtech.com/java-dataoutputstream-class#)[](https://www.tpointtech.com/java-dataoutputstream-class#)[](https://www.tpointtech.com/java-dataoutputstream-class#)

1. FileOutputStream fout = new FileOutputStream("D:\\testout.txt");  
2. DataOutputStream data = new DataOutputStream(fout);  

## Methods of DataOutputStream Class

The DataOutputStream class provides methods to write primitive data types.

|Method|Description|
|---|---|
|int size()|It is used to return the number of bytes written to the data output stream.|
|void write(int b)|It is used to write the specified byte to the underlying output stream.|
|void write(byte[] b, int off, int len)|It is used to write len bytes of data to the output stream.|
|void writeBoolean(boolean v)|It is used to write Boolean to the output stream as a 1-byte value.|
|void writeChar(int v)|It is used to write char to the output stream as a 2-byte value.|
|void writeChars(String s)|It is used to write [string](https://www.tpointtech.com/java-string) to the output stream as a sequence of characters.|
|void writeByte(int v)|It is used to write a byte to the output stream as a 1-byte value.|
|void writeBytes(String s)|It is used to write string to the output stream as a sequence of bytes.|
|void writeInt(int v)|It is used to write an int to the output stream|
|void writeShort(int v)|It is used to write a short to the output stream.|
|void writeShort(int v)|It is used to write a short to the output stream.|
|void writeLong(long v)|It is used to write a long to the output stream.|
|void writeUTF(String str)|It is used to write a string to the output stream using UTF-8 encoding in portable manner.|
|void flush()|It is used to flushes the data output stream.|

### Example of Java DataOutputStream Class

This example demonstrates how to write primitive data to a file using the DataOutputStream class.

[](https://www.tpointtech.com/java-dataoutputstream-class#)[](https://www.tpointtech.com/java-dataoutputstream-class#)[](https://www.tpointtech.com/java-dataoutputstream-class#)

1. package com.javatpoint;  

2. import java.io.*;  
3. public class OutputExample {  
4.     public static void main(String[] args) throws IOException {  
5.         FileOutputStream file = new FileOutputStream(D:\\testout.txt);  
6.         DataOutputStream data = new DataOutputStream(file);  
7.         data.writeInt(65);  
8.         data.flush();  
9.         data.close();  
10.         System.out.println("Succcess...");  
11.     }  
12. }  

**Output:**

Succcess...

**testout.txt:**

A