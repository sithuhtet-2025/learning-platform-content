The DataInputStream class in Java is used to read primitive data types from an input stream in a machine-independent format.

In this chapter, we will learn what the DataInputStream class is, why it is used, its declaration, constructor, important methods, and how to read primitive data from a file using an example.

## What is DataInputStream in Java?

The DataInputStream class allows a Java application to read primitive data types such as int, char, boolean, and String from an input stream in a portable way.

It is generally used with the DataOutputStream class, where data written using DataOutputStream can be read correctly using DataInputStream.

## DataInputStream Class Declaration

The following declaration shows how the DataInputStream class is defined:

[](https://www.tpointtech.com/java-datainputstream-class#)[](https://www.tpointtech.com/java-datainputstream-class#)[](https://www.tpointtech.com/java-datainputstream-class#)

1. public class DataInputStream extends FilterInputStream implements DataInput  

## Constructor of DataInputStream Class

The DataInputStream class provides a constructor to create a data input stream.

The DataInputStream(InputStream in) constructor creates a new DataInputStream that reads data from the specified input stream.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-datainputstream-class#)[](https://www.tpointtech.com/java-datainputstream-class#)[](https://www.tpointtech.com/java-datainputstream-class#)

1. DataInputStream(InputStream in)  

### Example of DataInputStream Class Constructor

The following example demonstrates how to create a DataInputStream using its constructor.

[](https://www.tpointtech.com/java-datainputstream-class#)[](https://www.tpointtech.com/java-datainputstream-class#)[](https://www.tpointtech.com/java-datainputstream-class#)

1. InputStream input = new FileInputStream("D:\\testout.txt");  
2. DataInputStream inst = new DataInputStream(input);  

## Methods of DataInputStream Class

The DataInputStream class provides methods to read primitive data types.

|Method|Description|
|---|---|
|int read(byte[] b)|It is used to read the number of bytes from the input stream.|
|int read(byte[] b, int off, int len)|It is used to read **len** bytes of data from the input stream.|
|int readInt()|It is used to read input bytes and return an int value.|
|byte readByte()|It is used to read and return the one input byte.|
|char readChar()|It is used to read two input bytes and returns a char value.|
|double readDouble()|It is used to read eight input bytes and returns a double value.|
|boolean readBoolean()|It is used to read one input byte and return true if byte is non zero, false if byte is zero.|
|int skipBytes(int x)|It is used to skip over x bytes of data from the input stream.|
|String readUTF()|It is used to read a [string](https://www.tpointtech.com/java-string) that has been encoded using the UTF-8 format.|
|void readFully(byte[] b)|It is used to read bytes from the input stream and store them into the buffer [array](https://www.tpointtech.com/array-in-java).|
|void readFully(byte[] b, int off, int len)|It is used to read **len** bytes from the input stream.|

## Example of DataInputStream Class

This example demonstrates how to read data from a file using the DataInputStream class.

[](https://www.tpointtech.com/java-datainputstream-class#)[](https://www.tpointtech.com/java-datainputstream-class#)[](https://www.tpointtech.com/java-datainputstream-class#)

1. package com.javatpoint;  
2. import java.io.*;    
3. public class DataStreamExample {  
4.   public static void main(String[] args) throws IOException {  
5.     InputStream input = new FileInputStream("D:\\testout.txt");  
6.     DataInputStream inst = new DataInputStream(input);  
7.     int count = input.available();  
8.     byte[] ary = new byte[count];  
9.     inst.read(ary);  
10.     for (byte bt : ary) {  
11.       char k = (char) bt;  
12.       System.out.print(k+"-");  
13.     }  
14.   }  
15. }  

Here, we are assuming that you have following data in **"testout.txt"** file:

JAVA

**Output:**

**J-A-V-A**