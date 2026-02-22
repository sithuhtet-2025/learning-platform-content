The FilterOutputStream class in Java is used to wrap another output stream and add additional functionality while writing data.

In this chapter, we will learn what the FilterOutputStream class is, why it is used, its declaration, constructor, methods, and how to write data using an example.

## What is FilterOutputStream in Java?

The **FilterOutputStream class** is a wrapper output stream that extends the OutputStream class, and it is used to filter or modify the data written to another output stream.

It acts as a base class for other output stream classes such as [BufferedOutputStream](https://www.tpointtech.com/java-bufferedoutputstream-class) and [DataOutputStream](https://www.tpointtech.com/java-dataoutputstream-class). Because of this, it is rarely used directly in applications.

## FilterOutputStream Class Declaration

The following declaration shows how the FilterOutputStream class is defined:

[](https://www.tpointtech.com/java-filteroutputstream-class#)[](https://www.tpointtech.com/java-filteroutputstream-class#)[](https://www.tpointtech.com/java-filteroutputstream-class#)

1. public class FilterOutputStream extends OutputStream  

## Constructor of FilterOutputStream Class

The FilterOutputStream class provides a constructor to wrap an existing output stream.

### FilterOutputStream(OutputStream out)

This constructor creates a new FilterOutputStream that writes data to the specified output stream.

**Syntax:**

Here is the syntax of the constructor:

[](https://www.tpointtech.com/java-filteroutputstream-class#)[](https://www.tpointtech.com/java-filteroutputstream-class#)[](https://www.tpointtech.com/java-filteroutputstream-class#)

1. FilterOutputStream(OutputStream out)  

### Example

The following example demonstrates how to create a FilterOutputStream object.

[](https://www.tpointtech.com/java-filteroutputstream-class#)[](https://www.tpointtech.com/java-filteroutputstream-class#)[](https://www.tpointtech.com/java-filteroutputstream-class#)

1. FileOutputStream file = new FileOutputStream("D:\\testout.txt");  
2. FilterOutputStream filter = new FilterOutputStream(file);  

## Methods of FilterOutputStream Class

The FilterOutputStream class provides methods to write and manage output data.

|Method|Description|
|---|---|
|void write(int b)|It is used to write the specified byte to the output stream.|
|void write(byte[] ary)|It is used to write ary.length byte to the output stream.|
|void write(byte[] b, int off, int len)|It is used to write len bytes from the offset off to the output stream.|
|void flush()|It is used to flushes the output stream.|
|void close()|It is used to close the output stream.|

## Example of FilterOutputStream Class

This example demonstrates how to write data to a file using the FilterOutputStream class.

[](https://www.tpointtech.com/java-filteroutputstream-class#)[](https://www.tpointtech.com/java-filteroutputstream-class#)[](https://www.tpointtech.com/java-filteroutputstream-class#)

1. import java.io.*;  
2. public class FilterExample {  
3.     public static void main(String[] args) throws IOException {  
4.         File data = new File("D:\\testout.txt");  
5.         FileOutputStream file = new FileOutputStream(data);  
6.         FilterOutputStream filter = new FilterOutputStream(file);  
7.         String s="Welcome to javaTpoint.";      
8.         byte b[]=s.getBytes();      
9.         filter.write(b);     
10.         filter.flush();  
11.         filter.close();  
12.         file.close();  
13.         System.out.println("Success...");  
14.     }  
15. }  

**Output:**

Success...

**testout.txt**

Welcome to javaTpoint.