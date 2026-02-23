The FileDescriptor class provides a handle to a file, [socket](https://www.tpointtech.com/socket-programming), or other input/output resource. It represents a connection to an underlying operating system resource.

## What is Java FileDescriptor Class?

The **FileDescriptor** class belongs to the [java.io package](https://www.tpointtech.com/java-io-package) and is used to identify an open file, standard input, standard output, or standard error stream.

The predefined handles are:

- **in**: Standard input
- **out**: Standard output
- **err**: Standard error

## FileDescriptor Class Declaration

The declaration of the FileDescriptor class is as follows:

[](https://www.tpointtech.com/java-filedescriptor-class#)[](https://www.tpointtech.com/java-filedescriptor-class#)[](https://www.tpointtech.com/java-filedescriptor-class#)

1. public final class FileDescriptor  

### Fields of FileDescriptor Class

The FileDescriptor class provides predefined static fields.

|Modifier|Type|Field|Description|
|---|---|---|---|
|static|FileDescriptor|err|A handle to the standard error stream.|
|static|FileDescriptor|in|A handle to the standard input stream.|
|static|FileDescriptor|out|A handle to the standard output stream.|

## Constructors of FileDescriptor Class

The FileDescriptor class provides one constructor that creates an invalid FileDescriptor object.

The syntax of the constructor is as follows:

[](https://www.tpointtech.com/java-filedescriptor-class#)[](https://www.tpointtech.com/java-filedescriptor-class#)[](https://www.tpointtech.com/java-filedescriptor-class#)

1. FileDescriptor()  

## Methods of FileDescriptor Class

The FileDescriptor class provides methods to manage file synchronization and validation.

|Modifier and Type|Method|Description|
|---|---|---|
|void|sync()|It force all system buffers to synchronize with the underlying device.|
|boolean|valid()|It tests if this file descriptor object is valid.|

## Examples of Java FileDescriptor Class

The following examples show how the FileDescriptor class works in Java.

### Example 1: Write Data to File Using FileDescriptor

In this example, data is written to a file and synchronized with the disk using the sync() method.

[](https://www.tpointtech.com/java-filedescriptor-class#)[](https://www.tpointtech.com/java-filedescriptor-class#)[](https://www.tpointtech.com/java-filedescriptor-class#)

1. import java.io.*;  

2. public class FileDescriptorExample1 {  
3.     public static void main(String[] args) {  
4.         try {  
5.             FileOutputStream fos = new FileOutputStream("Record.txt");  
6.             FileDescriptor fd = fos.getFD();  

7.             byte[] data = {48,49,50,51,52,53,54,55,56,57,58};  
8.             fos.write(data);  
9.             fos.flush();  
10.             fd.sync();  

11.             System.out.println("Data written and synced successfully");  
12.             fos.close();  
13.         } catch (Exception e) {  
14.             e.printStackTrace();  
15.         }  
16.     }  
17. }  

**Output:**

Data written and synced successfully

### Example 2: Read File Content Using FileDescriptor

In this example, a file is read after ensuring data synchronization.

[](https://www.tpointtech.com/java-filedescriptor-class#)[](https://www.tpointtech.com/java-filedescriptor-class#)[](https://www.tpointtech.com/java-filedescriptor-class#)

1. import java.io.*;  

2. public class FileDescriptorExample2 {  
3.     public static void main(String[] args) {  
4.         try {  
5.             FileInputStream fis = new FileInputStream("Record.txt");  
6.             int value;  

7.             while ((value = fis.read()) != -1) {  
8.                 System.out.print((char) value);  
9.             }  

10.             System.out.println("\nFile read completed");  
11.             fis.close();  
12.         } catch (Exception e) {  
13.             e.printStackTrace();  
14.         }  
15.     }  
16. }  

**Output:**

0123456789:
File read completed
Record.txt Content
0123456789: