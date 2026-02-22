The ByteArrayInputStream class in Java is used to read data from a byte array as an input stream.

In this chapter, we will learn what the ByteArrayInputStream class is, how it works, its declaration, [constructors](https://www.tpointtech.com/java-constructor), methods, and how to read byte array data using an example.

## What is ByteArrayInputStream in Java?

The ByteArrayInputStream class allows a byte array to be used as an input stream. Instead of reading data from a file or device, it reads data directly from a byte array stored in memory.

This [class](https://www.tpointtech.com/java-classes-and-objects) internally uses a buffer to read byte data sequentially. It is useful when input data is already available in the form of a byte array.

## ByteArrayInputStream Class Declaration

The following declaration shows how the ByteArrayInputStream class is defined:

[](https://www.tpointtech.com/java-bytearrayinputstream-class#)[](https://www.tpointtech.com/java-bytearrayinputstream-class#)[](https://www.tpointtech.com/java-bytearrayinputstream-class#)

1. public class ByteArrayInputStream extends InputStream  

## Constructors of ByteArrayInputStream Class

The ByteArrayInputStream class provides constructors to create an input stream from a byte array.

### 1. ByteArrayInputStream(byte[] buf)

This constructor creates a new byte array input stream that uses the given byte array as its internal buffer.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-bytearrayinputstream-class#)[](https://www.tpointtech.com/java-bytearrayinputstream-class#)[](https://www.tpointtech.com/java-bytearrayinputstream-class#)

1. ByteArrayInputStream(byte[] buf)  

### 2. ByteArrayInputStream(byte[] buf, int offset, int length)

This constructor creates a new byte array input stream that reads data starting from the specified offset and up to the given length.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-bytearrayinputstream-class#)[](https://www.tpointtech.com/java-bytearrayinputstream-class#)[](https://www.tpointtech.com/java-bytearrayinputstream-class#)

1. ByteArrayInputStream(byte[] buf, int offset, int length)  

### Example of ByteArrayInputStream Class Constructors

The following code statements demonstrates how the constructors of the ByteArrayInputStream class are used.

[](https://www.tpointtech.com/java-bytearrayinputstream-class#)[](https://www.tpointtech.com/java-bytearrayinputstream-class#)[](https://www.tpointtech.com/java-bytearrayinputstream-class#)

1. byte[] data = {65, 66, 67, 68};  
2. ByteArrayInputStream in1 = new ByteArrayInputStream(data);  
3. ByteArrayInputStream in2 = new ByteArrayInputStream(data, 1, 2);  

## Methods of ByteArrayInputStream Class

The ByteArrayInputStream class provides several methods to read data from a byte array.

|Methods|Description|
|---|---|
|int available()|It is used to return the number of remaining bytes that can be read from the input stream.|
|int read()|It is used to read the next byte of data from the input stream.|
|int read(byte[] ary, int off, int len)|It is used to read up to len bytes of data from an array of bytes in the input stream.|
|boolean markSupported()|It is used to test the input stream for mark and reset method.|
|long skip(long x)|It is used to skip the x bytes of input from the input stream.|
|void mark(int readAheadLimit)|It is used to set the current marked position in the stream.|
|void reset()|It is used to reset the buffer of a byte array.|
|void close()|It is used for closing a ByteArrayInputStream.|

## Example of ByteArrayInputStream Class

This example demonstrates how to read data from a byte array using the ByteArrayInputStream class.

[](https://www.tpointtech.com/java-bytearrayinputstream-class#)[](https://www.tpointtech.com/java-bytearrayinputstream-class#)[](https://www.tpointtech.com/java-bytearrayinputstream-class#)

1. package com.javatpoint;  
2. import java.io.*;  
3. public class ReadExample {  
4.   public static void main(String[] args) throws IOException {  
5.     byte[] buf = { 35, 36, 37, 38 };  
6.     // Create the new byte array input stream  
7.     ByteArrayInputStream byt = new ByteArrayInputStream(buf);  
8.     int k = 0;  
9.     while ((k = byt.read()) != -1) {  
10.       //Conversion of a byte into character  
11.       char ch = (char) k;  
12.       System.out.println("ASCII value of Character is:" + k + "; Special character is: " + ch);  
13.     }  
14.   }  
15. }  

**Output:**

ASCII value of Character is:35; Special character is: #
ASCII value of Character is:36; Special character is: $
ASCII value of Character is:37; Special character is: %
ASCII value of Character is:38; Special character is: &