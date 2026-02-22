The ByteArrayOutputStream class in Java is used to write data into a byte array, which can later be written to multiple output streams.

In this chapter, we will learn what the ByteArrayOutputStream class is, how it works, its declaration, [constructors](https://www.tpointtech.com/java-constructor), methods, and how to write the same data into multiple files using an example.

## What is ByteArrayOutputStream in Java?

The ByteArrayOutputStream class writes data into an internal byte array instead of directly writing it to a file or device. The stored data can later be written to multiple output streams.

This class maintains a copy of data in memory and forwards it to multiple streams when required. The internal buffer automatically grows as more data is written.

## ByteArrayOutputStream Class Declaration

The following declaration shows how the ByteArrayOutputStream class is defined:

[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)

1. public class ByteArrayOutputStream extends OutputStream  

## Constructors of ByteArrayOutputStream Class

The ByteArrayOutputStream class provides constructors to create a byte array output stream.

### 1. ByteArrayOutputStream()

This constructor creates a new byte array output stream with an initial buffer capacity of 32 bytes. The buffer size increases automatically if required.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)

1. ByteArrayOutputStream()  

### 2. ByteArrayOutputStream(int size)

This constructor creates a new byte array output stream with the specified initial buffer size.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)

1. ByteArrayOutputStream(int size)  

### Example of ByteArrayOutputStream Class Constructors

The following code statements demonstrates how the ByteArrayOutputStream constructors are used to store data in memory.

[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)

1. ByteArrayOutputStream bout1 = new ByteArrayOutputStream();  
2. ByteArrayOutputStream bout2 = new ByteArrayOutputStream(64);  

## Methods of ByteArrayOutputStream Class

The ByteArrayOutputStream class provides methods to write, convert, and transfer data.

|Method|Description|
|---|---|
|int size()|It is used to returns the current size of a buffer.|
|byte[] toByteArray()|It is used to create a newly allocated byte array.|
|String toString()|It is used for converting the content into a [string](https://www.tpointtech.com/java-string) decoding bytes using a platform default character set.|
|String toString(String charsetName)|It is used for converting the content into a string decoding bytes using a specified charsetName.|
|void write(int b)|It is used for writing the byte specified to the byte array output stream.|
|void write(byte[] b, int off, int len|It is used for writing **len** bytes from specified byte array starting from the offset **off** to the byte array output stream.|
|void writeTo(OutputStream out)|It is used for writing the complete content of a byte array output stream to the specified output stream.|
|void reset()|It is used to reset the count field of a byte array output stream to zero value.|
|void close()|It is used to close the ByteArrayOutputStream.|

## Example of ByteArrayOutputStream Class

This example demonstrates how to write the same data into two different files using the ByteArrayOutputStream class.

[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)[](https://www.tpointtech.com/java-bytearrayoutputstream-class#)

1. package com.javatpoint;  
2. import java.io.*;  
3. public class DataStreamExample {  
4. public static void main(String args[])throws Exception{    
5.       FileOutputStream fout1=new FileOutputStream("D:\\f1.txt");    
6.       FileOutputStream fout2=new FileOutputStream("D:\\f2.txt");    

7.       ByteArrayOutputStream bout=new ByteArrayOutputStream();    
8.       bout.write(65);    
9.       bout.writeTo(fout1);    
10.       bout.writeTo(fout2);    

11.       bout.flush();    
12.       bout.close();//has no effect    
13.       System.out.println("Success...");    
14.      }    
15.     }   

**Output:**

Success...

**f1.txt:**

A

**f2.txt:**

A

![Java Byte array output stream class 1](https://images.tpointtech.com/java/javaio/images/java-byte-array-output-stream-class1.png)