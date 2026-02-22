Java I/O (Input and Output) is used to read data from input sources and write data to output destinations.

In this chapter, we will learn the basics of Java I/O, core concepts like streams and readers/writers, important I/O classes, and best practices for handling input and output operations.

## What is Java I/O?

Java I/O refers to the process of handling input and output operations in Java applications. It is mainly used to read data from sources such as the keyboard or files and write data to destinations like the console or files.

Java uses the concept of **streams** to make input and output operations efficient. All Java I/O-related classes are available in the java.io package.

Java I/O is also widely used for **file handling** in Java.

## Core Concepts of Java I/O

Java I/O is based on two main concepts:

### 1. Streams

A stream represents a continuous flow of data. In Java, streams are used to read or write data sequentially.

There are two types of streams:

- **Input Streams:** Used to read data from a source
- **Output Streams:** Used to write data to a destination

Streams are further classified into:

- **Byte Streams:** InputStream, OutputStream
- **Character Streams:** Reader, Writer

### 2. Readers/Writers

Readers and Writers are specially designed for handling **character-based data**.

- **Readers**: Readers are used to read character data
- **Writers**: Writers are used to write character data

They provide a convenient way to work with text data.

## What is a Stream in Java?

A stream is a sequence of data bytes. It is called a stream because data flows continuously, similar to a stream of water.

Java automatically creates three standard streams, which are connected to the console:

1. **System.out** – Standard output stream
2. **System.in** – Standard input stream
3. **System.err** – Standard error stream

Let's see the code to print **output and an error** message to the console.

[](https://www.tpointtech.com/java-io#)[](https://www.tpointtech.com/java-io#)[](https://www.tpointtech.com/java-io#)

1. System.out.println("simple message");  
2. System.err.println("error message");  

Let's see the code to get **input** from console.

[](https://www.tpointtech.com/java-io#)[](https://www.tpointtech.com/java-io#)[](https://www.tpointtech.com/java-io#)

1. int i=System.in.read();//returns ASCII code of 1st character  
2. System.out.println((char)i);//will print the character  

## OutputStream Class

OutputStream class is an abstract class. It is the superclass of all classes representing an output stream of bytes. An output stream accepts output bytes and sends them to some sink.

### Methods of OutputStream Class

The following table lists the useful methods of OutputStream class:

|Method|Description|
|---|---|
|public void write(int) throws IOException|It is used to write a byte to the current output stream.|
|public void write(byte[])throws IOException|It is used to write an array of byte to the current output stream.|
|public void flush() throws IOException|It flushes the current output stream.|
|public void close() throws IOException|It is used to close the current output stream.|

### OutputStream Hierarchy

The following image shows the class hierarchy of the OutputStream, illustrating its subclasses and their relationships used for writing byte data to different destinations.

![Java output stream hierarchy](https://d2jdgazzki9vjm.cloudfront.net/java/javaio/images/java-outputstream.png)

### Example of OutputStream Class

The following example demonstrates how a student writes exam answers to a file using the OutputStream class.

[](https://www.tpointtech.com/java-io#)[](https://www.tpointtech.com/java-io#)[](https://www.tpointtech.com/java-io#)

1. import java.io.FileOutputStream;  

2. public class OutputStreamExample {  
3.     public static void main(String[] args) throws Exception {  
4.         FileOutputStream fout = new FileOutputStream("answer.txt");  
5.         String content = "Student exam answers";  
6.         fout.write(content.getBytes());  
7.         fout.close();  
8.         System.out.println("Data written successfully");  
9.     }  
10. }  

**Output:**

Data written successfully

## InputStream Class

InputStream class is an abstract class. It is the superclass of all classes representing an input stream of bytes.

### Useful Methods of InputStream Class

The following table lists the useful methods of InputStream class:

|Method|Description|
|---|---|
|public abstract int read() throws IOException|It reads the next byte of data from the input stream. It returns -1 at the end of the file.|
|public int available() throws IOException|It returns an estimate of the number of bytes that can be read from the current input stream.|
|public void close() throws IOException|It is used to close the current input stream.|

### InputStream Hierarchy

The following image shows the class hierarchy of the InputStream in Java, illustrating its subclasses and their relationships used for reading byte data from different sources.

![Java input stream hierarchy](https://d2jdgazzki9vjm.cloudfront.net/java/javaio/images/java-inputstream.png)

### Example of InputStream Class

The following example demonstrates how a student reads notes from a file using the InputStream class.

[](https://www.tpointtech.com/java-io#)[](https://www.tpointtech.com/java-io#)[](https://www.tpointtech.com/java-io#)

1. import java.io.FileInputStream;  

2. public class InputStreamExample {  
3.     public static void main(String[] args) throws Exception {  
4.         FileInputStream fin = new FileInputStream("answer.txt");  
5.         int i;  
6.         while ((i = fin.read()) != -1) {  
7.             System.out.print((char) i);  
8.         }  
9.         fin.close();  
10.     }  
11. }  

**Output:**

Student exam answers

## OutputStream Vs. InputStream

The OutputStream and InputStream classes are used to write data to and read data from different sources and destinations.

An **OutputStream** is used by a Java application to write data to a destination. The destination can be a file, a byte array, a peripheral device, or a network socket. Whereas, an **InputStream** is used by a Java application to read data from a source. The source can be a file, a byte array, a peripheral device, or a network socket.

The following image shows the working and relationship of the OutputStream and InputStream classes.

![Java IO](https://d2jdgazzki9vjm.cloudfront.net/java/javaio/images/java-io-flow.png)

## Java I/O Classes

Java provides a rich set of classes to perform input and output operations. These classes help programs read data from different sources and write data to various destinations.

- **InputStream and OutputStream:**  
    These are abstract base classes used for byte-oriented input and output operations. InputStream is used to read byte data from a source, and OutputStream is used to write byte data to a destination. Many other byte stream classes are derived from these classes.
- [**Reader**](https://www.tpointtech.com/java-reader-class) **and** [**Writer**](https://www.tpointtech.com/java-writer-class)**:**  
    The Reader and Writer classes are abstract classes designed for character-based input and output operations. They are mainly used for handling text data. Reader reads character data from a source, while Writer writes character data to a destination.
- [**FileInputStream**](https://www.tpointtech.com/java-fileinputstream-class) **and** [**FileOutputStream**](https://www.tpointtech.com/java-fileoutputstream-class)**:**  
    These classes are used to read and write byte data from and to files. FileInputStream reads raw bytes from a file, and FileOutputStream writes raw bytes to a file. They are suitable for binary files such as images and videos.
- [**FileReader**](https://www.tpointtech.com/java-filereader-class) **and** [**FileWriter**](https://www.tpointtech.com/java-bufferedwriter-class)**:**  
    These classes are used to read and write character data from and to files. They are best suited for reading and writing text files.
- [**BufferedInputStream**](https://www.tpointtech.com/java-bufferedinputstream-class) **and** [**BufferedOutputStream**](https://www.tpointtech.com/java-bufferedoutputstream-class)**:**  
    These classes improve performance by using a buffer to store data temporarily. This reduces the number of read and write operations and improves efficiency.
- [**BufferedReader**](https://www.tpointtech.com/java-bufferedreader-class) **and** [**BufferedWriter**](https://www.tpointtech.com/java-bufferedwriter-class)**:**  
    Thesae classes provide buffered input and output for character streams. They make character-based I/O faster and provide useful methods like readLine().