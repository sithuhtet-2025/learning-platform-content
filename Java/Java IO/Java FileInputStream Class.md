Java FileInputStream class obtains input bytes from a [file](https://www.tpointtech.com/java-file-class). It is used for reading byte-oriented data (streams of raw bytes) such as image data, audio, video etc. You can also read character-stream data. But, for reading streams of characters, it is recommended to use [FileReader](https://www.tpointtech.com/java-filereader-class) class.

## Java FileInputStream Class Declaration

Let's see the declaration for java.io.FileInputStream class:

[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)

1. public class FileInputStream extends InputStream  

## Java FileInputStream Class Methods

|Method|Description|
|---|---|
|int available()|It is used to return the estimated number of bytes that can be read from the input stream.|
|int read()|It is used to read the byte of data from the input stream.|
|int read(byte[] b)|It is used to read up to **b.length** bytes of data from the input stream.|
|int read(byte[] b, int off, int len)|It is used to read up to **len** bytes of data from the input stream.|
|long skip(long x)|It is used to skip over and discards x bytes of data from the input stream.|
|FileChannel getChannel()|It is used to return the unique FileChannel object associated with the file input stream.|
|FileDescriptor getFD()|It is used to return the [FileDescriptor](https://www.tpointtech.com/java-filedescriptor-class) object.|
|protected void finalize()|It is used to ensure that the close method is call when there is no more reference to the file input stream.|
|void close()|It is used to closes the [stream](https://www.tpointtech.com/java-8-stream).|

### Java FileInputStream Example 1: Read Single Character

**File Name: DataStreamExample.java**

[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)

1. import java.io.FileInputStream;  
2. public class DataStreamExample {  
3.      public static void main(String args[]){    
4.           try{    
5.             FileInputStream fin=new FileInputStream("D:\\testout.txt");    
6.             int i=fin.read();  
7.             System.out.print((char)i);    

8.             fin.close();    
9.           }catch(Exception e){System.out.println(e);}    
10.          }    
11.         }  

#### Note: Before running the code, a text file named as **"testout.txt"** is required to be created. In this file, we have written the following content in the file:

Welcome to javatpoint.

After executing the above program, we will get a single character from the file which is 87 (in byte form). To see the text, we need to convert it into character.

**Output:**

W

### Java FileInputStream Example 2: Read All Characters

**File Name: DataStreamExample.java**

[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)

1. package com.javatpoint;  

2. import java.io.FileInputStream;  
3. public class DataStreamExample {  
4.      public static void main(String args[]){    
5.           try{    
6.             FileInputStream fin=new FileInputStream("D:\\testout.txt");    
7.             int i=0;    
8.             while((i=fin.read())!=-1){    
9.              System.out.print((char)i);    
10.             }    
11.             fin.close();    
12.           }catch(Exception e){System.out.println(e);}    
13.          }    
14.         }  

**Output:**

Welcome to javaTpoint

## FileInputStream Class Constructors

The FileInputStream class in Java provides several constructors to create a FileInputStream instance, allowing us to read bytes from a file in various ways. Here is an overview of the constructors available in the FileInputStream class:

### 1. FileInputStream(String name)

It creates a **FileInputStream** by opening a connection to an actual file, the file named by the path name **name** in the file system.

- **Parameters: name** - the name of the file.
- **Throws FileNotFoundException** if the file does not exist, is a directory rather than a regular file, or for some other reason, cannot be opened for reading.

**Example:**

[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)

1. FileInputStream fis = new FileInputStream("example.txt");  

**File Name: FileInputStreamExample.java**

[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)

1. import java.io.FileInputStream;  
2. import java.io.IOException;  
3. public class FileInputStreamExample {  
4.     public static void main(String[] args) {  
5.         // Specify the file name to open  
6.         String fileName = "D:\\javatpoint\\April\\Files\\example.txt";  
7.         // Try-with-resources statement to ensure the FileInputStream is closed after  
8.         // use  
9.         try (FileInputStream fis = new FileInputStream(fileName)) {  
10.             int i;  
11.             // Read one byte at a time until the end of the file is reached  
12.             while ((i = fis.read()) != -1) {  
13.                 // Convert the byte to a char and print it  
14.                 System.out.print((char) i);  
15.             }  
16.         } catch (IOException e) {  
17.             // Handle exceptions, such as FileNotFoundException  
18.             e.printStackTrace();  
19.         }  
20.     }  
21. }  

**Output:**

![Java FileInputStream Class](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-fileinputstream-class.png)

### 2. FileInputStream(File file)

It creates a **FileInputStream** by opening a connection to an actual file represented by a **File** object.

- **Parameters: file** - the **File** object that represents the file to be opened.
- **Throws FileNotFoundException** if the file does not exist, is a directory rather than a regular file, or for some other reason, cannot be opened for reading.

**Example:**

[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)

1. File file = new File("example.txt");  
2. FileInputStream fis = new FileInputStream(file);  

**File Name: FileInputStreamExample.java**

[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)

1. import java.io.File;  
2. import java.io.FileInputStream;  
3. import java.io.IOException;  
4. public class FileInputStreamExample {  
5.     public static void main(String[] args) {  
6.         // Create a File object for the file to be read  
7.         File file = new File("D:\\javatpoint\\April\\Files\\example.txt");  
8.         // Try-with-resources statement to ensure the FileInputStream is closed after  
9.         // use  
10.         try (FileInputStream fis = new FileInputStream(file)) {  
11.             int i;  
12.             // Read one byte at a time until the end of the file is reached  
13.             while ((i = fis.read()) != -1) {  
14.                 // Convert the byte to a char and print it  
15.                 System.out.print((char) i);  
16.             }  
17.         } catch (IOException e) {  
18.             // Handle exceptions, such as FileNotFoundException  
19.             e.printStackTrace();  
20.         }  
21.     }  
22. }  

**Output:**

![Java FileInputStream Class](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-fileinputstream-class2.png)

### 3. FileInputStream(FileDescriptor fdObj)

It creates a **FileInputStream** by using a file descriptor **fdObj** that represents an existing connection to an actual file in the file system.

- **Parameters: fdObj** - the file descriptor.
- **Note:** It is useful when we have a **FileDescriptor** for a file, perhaps obtained from another file system operation or as part of inter-process communication.

**Example:**

[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)

1. FileDescriptor fd = FileDescriptor.in; // Just an example, usually you get it from other sources.  
2. FileInputStream fis = new FileInputStream(fd);  

**File Name: FileDescriptorExample.java**

[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)[](https://www.tpointtech.com/java-fileinputstream-class#)

1. import java.io.File;  
2. import java.io.FileDescriptor;  
3. import java.io.FileInputStream;  
4. import java.io.FileOutputStream;  
5. import java.io.IOException;  
6. public class FileDescriptorExample {  
7.     public static void main(String[] args) {  
8.         // Specify the file path  
9.         String filePath = "example.txt";  
10.         // Create a file and write some data to it  
11.         try (FileOutputStream out = new FileOutputStream(filePath)) {  
12.             out.write("Hello, world!".getBytes());  
13.         } catch (IOException e) {  
14.             System.out.println("Error writing to file: " + e.getMessage());  
15.             return;  
16.         }  
17.         // Read from the file using FileInputStream and FileDescriptor  
18.         try (FileInputStream fis = new FileInputStream(filePath);  
19.                 FileInputStream fisFromFD = new FileInputStream(fis.getFD())) {  
20.             // Read data from the FileInputStream  
21.             int data;  
22.             while ((data = fisFromFD.read()) != -1) {  
23.                 System.out.print((char) data);  
24.             }  
25.         } catch (IOException e) {  
26.             System.out.println("Error reading from file: " + e.getMessage());  
27.         }  
28.     }  
29. }  

**Output:**

Hello, world!

  
![Java FileInputStream Class](https://d2jdgazzki9vjm.cloudfront.net/core/images/java-fileinputstream-class3.png)

The code will create a file called example.txt, write "Hello, world!" to it, and then read it back using a FileDescriptor to demonstrate how you can utilize this Java feature. Adjust the file path and environment according to your needs. It is a self-contained example suitable for understanding how FileInputStream and FileDescriptor work together in practice.