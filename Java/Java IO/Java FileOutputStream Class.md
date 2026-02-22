The FileOutputStream class in Java is used to write byte data to a file. In this chapter, we will learn what the FileOutputStream class is, when to use it, its methods, and how to write data to a file using simple examples.

## What is FileOutputStream in Java?

The **FileOutputStream** class is an output stream used to write data into a file. It writes data in the form of bytes and is mainly used for byte-oriented file operations.

If you want to write primitive or binary data into a file, the **FileOutputStream** class is suitable. Although it can also write character data, it is recommended to use the FileWriter class for character-oriented operations.

## FileOutputStream class declaration

The following declaration shows how the FileOutputStream class is defined:

[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)

1. public class FileOutputStream extends OutputStream  

## Constructors of FileOutputStream Class

The FileOutputStream class provides constructors to create an output stream and connect it to a file.

### 1. FileOutputStream(String name)

This constructor creates a file output stream to write data to a file with the specified name. If the file already exists, its content is overwritten. If the file does not exist, a new file is created.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)

1. FileOutputStream(String name)  

### 2. FileOutputStream(String name, boolean append)

This constructor creates a file output stream to write data to a file. If append is set to true, the data is added at the end of the file. If it is false, the existing file content is overwritten.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)

1. FileOutputStream(String name, boolean append)  

### 3. FileOutputStream(File file)

This constructor creates a file output stream using a File object instead of a file name.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)

1. FileOutputStream(File file)  

### 4. FileOutputStream(File file, boolean append)

This constructor creates a file output stream using a File object and allows appending data to the file if required.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)

1. FileOutputStream(File file, boolean append)  

### Example: Using FileOutputStream Constructor with Append Mode

The following example demonstrates how to append data to an existing file using the FileOutputStream constructor.

[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)

1. import java.io.FileOutputStream;  

2. public class AppendExample {  
3.     public static void main(String args[]) {  
4.         try {  
5.             FileOutputStream fout =  
6.                 new FileOutputStream("D:\\testout.txt", true);  
7.             String s = "\nAppending new data";  
8.             fout.write(s.getBytes());  
9.             fout.close();  
10.             System.out.println("data appended successfully");  
11.         } catch (Exception e) {  
12.             System.out.println(e);  
13.         }  
14.     }  
15. }  

**Output:**

data appended successfully

## Methods of FileOutputStream Class

The FileOutputStream class provides several methods to write data to a file.

|Method|Description|
|---|---|
|protected void finalize()|It is used to clean up the connection with the file output stream.|
|void write(byte[] ary)|It is used to write **ary.length** bytes from the byte [array](https://www.tpointtech.com/array-in-java) to the file output stream.|
|void write(byte[] ary, int off, int len)|It is used to write **len** bytes from the byte array starting at offset **off** to the file output stream.|
|void write(int b)|It is used to write the specified byte to the file output stream.|
|FileChannel getChannel()|It is used to return the file channel object associated with the file output stream.|
|FileDescriptor getFD()|It is used to return the file descriptor associated with the stream.|
|void close()|It is used to closes the file output stream.|

## Example 1: Writing a Single Byte Using FileOutputStream

In this example, a single byte value is written to a file. The byte value 65 represents the character A.

[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)

1. import java.io.FileOutputStream;  
2. public class FileOutputStreamExample {  
3.     public static void main(String args[]){    
4.            try{    
5.              FileOutputStream fout=new FileOutputStream("D:\\testout.txt");    
6.              fout.write(65);    
7.              fout.close();    
8.              System.out.println("success...");    
9.             }catch(Exception e){System.out.println(e);}    
10.       }    
11. }  

**Output:**

Success...

The content of a text file **testout.txt** is set with the data **A**.

**testout.txt**

A

## Example 2: Writing a String Using FileOutputStream

In this example, a string is converted into a byte array and then written to a file using the FileOutputStream class.

[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)[](https://www.tpointtech.com/java-fileoutputstream-class#)

1. import java.io.FileOutputStream;  
2. public class FileOutputStreamExample {  
3.     public static void main(String args[]){    
4.            try{    
5.              FileOutputStream fout=new FileOutputStream("D:\\testout.txt");    
6.              String s="Welcome to javaTpoint.";    
7.              byte b[]=s.getBytes();//converting string into byte array    
8.              fout.write(b);    
9.              fout.close();    
10.              System.out.println("success...");    
11.             }catch(Exception e){System.out.println(e);}    
12.       }    
13. }  

**Output:**

Success...

The content of a text file **testout.txt** is set with the data **Welcome to javaTpoint.**

**testout.txt**

Welcome to javaTpoint.