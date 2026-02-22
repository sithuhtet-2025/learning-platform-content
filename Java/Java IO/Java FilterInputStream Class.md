The FilterInputStream class in Java is used to wrap another input stream and provide additional functionality while reading data.

In this chapter, we will learn what the FilterInputStream class is, why it is used, its declaration, constructor, methods, and how it works with an example.

## What is FilterInputStream in Java?

The **FilterInputStream class** is an input stream that wraps another InputStream, and it is used to filter or modify the data while reading from the stream.

It acts as a base class for other input stream classes such as [BufferedInputStream](https://www.tpointtech.com/java-bufferedinputstream-class), [DataInputStream](https://www.tpointtech.com/java-datainputstream-class). Due to this reason, it is rarely used directly in applications and is mainly used as a superclass.

### FilterInputStream Class Declaration

The following declaration shows how the FilterInputStream class is defined in Java.

[](https://www.tpointtech.com/java-filterinputstream-class#)[](https://www.tpointtech.com/java-filterinputstream-class#)[](https://www.tpointtech.com/java-filterinputstream-class#)

1. public class FilterInputStream extends InputStream  

## Constructor of FilterInputStream Class

The FilterInputStream class provides a constructor to wrap an existing input stream.

### FilterInputStream(InputStream in)

This constructor creates a new FilterInputStream that reads data from the specified input stream.

**Syntax:**

Here is the syntax of the constructor:

[](https://www.tpointtech.com/java-filterinputstream-class#)[](https://www.tpointtech.com/java-filterinputstream-class#)[](https://www.tpointtech.com/java-filterinputstream-class#)

1. FilterInputStream(InputStream in)  

### Example

The following example demonstrates how to create a FilterInputStream object.

[](https://www.tpointtech.com/java-filterinputstream-class#)[](https://www.tpointtech.com/java-filterinputstream-class#)[](https://www.tpointtech.com/java-filterinputstream-class#)

1. FileInputStream file = new FileInputStream("D:\\testout.txt");  
2. FilterInputStream filter = new BufferedInputStream(file);  

### Methods of FilterInputStream Class

The FilterInputStream class provides methods to read and manage input data.

|Method|Description|
|---|---|
|int available()|It is used to return an estimate number of bytes that can be read from the input stream.|
|int read()|It is used to read the next byte of data from the input stream.|
|int read(byte[] b)|It is used to read up to byte.length bytes of data from the input stream.|
|long skip(long n)|It is used to skip over and discards n bytes of data from the input stream.|
|boolean markSupported()|It is used to test if the input stream support mark and reset method.|
|void mark(int readlimit)|It is used to mark the current position in the input stream.|
|void reset()|It is used to reset the input stream.|
|void close()|It is used to close the input stream.|

### Example of FilterInputStream Class

This example demonstrates how to read data from a file using the FilterInputStream class.

[](https://www.tpointtech.com/java-filterinputstream-class#)[](https://www.tpointtech.com/java-filterinputstream-class#)[](https://www.tpointtech.com/java-filterinputstream-class#)

1. import java.io.*;  
2. public class FilterExample {  
3.     public static void main(String[] args) throws IOException {  
4.         File data = new File("D:\\testout.txt");  
5.         FileInputStream  file = new FileInputStream(data);  
6.         FilterInputStream filter = new BufferedInputStream(file);  
7.         int k =0;  
8.         while((k=filter.read())!=-1){  
9.             System.out.print((char)k);  
10.         }  
11.         file.close();  
12.         filter.close();  
13.     }  
14. }  

Here, we are assuming that you have following data in **"testout.txt"** file:

Welcome to javatpoint

**Output:**

Welcome to javatpoint