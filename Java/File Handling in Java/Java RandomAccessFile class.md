The **RandomAccessFile** class is used to read and write data to a file at any position. It allows accessing a file like an array of bytes.

In this chapter, we will learn how to use the RandomAccessFile class to read and write data at any position in a file.

## What is Java RandomAccessFile Class?

The **RandomAccessFile** class belongs to the [java.io package](https://www.tpointtech.com/java-io-package) and allows reading and writing data at any location in a file using a file pointer.

The file pointer moves automatically after read or write operations. If the end of the file is reached before reading the required bytes, an EOFException is thrown.

## Java RandomAccessFile Class Declaration

The declaration of the RandomAccessFile class is as follows:

[](https://www.tpointtech.com/java-randomaccessfile-class#)[](https://www.tpointtech.com/java-randomaccessfile-class#)[](https://www.tpointtech.com/java-randomaccessfile-class#)

1. public class RandomAccessFile implements DataOutput, DataInput, Closeable  

## Constructors of RandomAccessFile Class

The RandomAccessFile class provides constructors to open a file in read or read-write mode.

### 1. RandomAccessFile(File file, String mode)

This constructor creates a random-access file stream to read from, and optionally to write to, the file specified by the File object.

Here is the syntax:

[](https://www.tpointtech.com/java-randomaccessfile-class#)[](https://www.tpointtech.com/java-randomaccessfile-class#)[](https://www.tpointtech.com/java-randomaccessfile-class#)

1. RandomAccessFile(File file, String mode)  

### 2. RandomAccessFile(String name, String mode)

This constructor creates a random-access file stream to read from, and optionally to write to, a file with the specified name.

Here is the syntax:

[](https://www.tpointtech.com/java-randomaccessfile-class#)[](https://www.tpointtech.com/java-randomaccessfile-class#)[](https://www.tpointtech.com/java-randomaccessfile-class#)

1. RandomAccessFile(String name, String mode)  

The mode can be:

- "r": The read only mode.
- "rw": The read and write mode.

## Methods of RandomAccessFile Class

The RandomAccessFile class provides methods to read, write, and control file pointer position.

### Constructor

|[Constructor](https://www.tpointtech.com/java-constructor)|Description|
|---|---|
|RandomAccessFile(File file, [String](https://www.tpointtech.com/java-string) mode)|Creates a random access file stream to read from, and optionally to write to, the file specified by the File argument.|
|RandomAccessFile(String name, String mode)|Creates a random access file stream to read from, and optionally to write to, a file with the specified name.|

### Method

|Modifier and Type|Method|Method|
|---|---|---|
|void|close()|It closes this random access file stream and releases any system resources associated with the stream.|
|FileChannel|getChannel()|It returns the unique [FileChannel](https://www.tpointtech.com/data-transfer-between-channels) object associated with this file.|
|int|readInt()|It reads a signed 32-bit integer from this file.|
|String|readUTF()|It reads in a string from this file.|
|void|seek(long pos)|It sets the file-pointer offset, measured from the beginning of this file, at which the next read or write occurs.|
|void|writeDouble(double v)|It converts the double argument to a long using the doubleToLongBits method in class Double, and then writes that long value to the file as an eight-byte quantity, high byte first.|
|void|writeFloat(float v)|It converts the float argument to an int using the floatToIntBits method in class Float, and then writes that int value to the file as a four-byte quantity, high byte first.|
|void|write(int b)|It writes the specified byte to this file.|
|int|read()|It reads a byte of data from this file.|
|long|length()|It returns the length of this file.|
|void|seek(long pos)|It sets the file-pointer offset, measured from the beginning of this file, at which the next read or write occurs.|

## Examples of RandomAccessFile Class

The following examples show how to use the RandomAccessFile class in Java.

### Example 1: Read Data from File Using RandomAccessFile

In this example, data is read from a file starting from a specific position.

[](https://www.tpointtech.com/java-randomaccessfile-class#)[](https://www.tpointtech.com/java-randomaccessfile-class#)[](https://www.tpointtech.com/java-randomaccessfile-class#)

1. import java.io.RandomAccessFile;  
2. import java.io.IOException;  

3. public class RandomAccessFileExample1 {  
4.     public static void main(String[] args) {  
5.         try {  
6.             RandomAccessFile file = new RandomAccessFile("myFile.txt", "r");  
7.             file.seek(0);  

8.             byte[] data = new byte[18];  
9.             file.read(data);  

10.             System.out.println(new String(data));  
11.             file.close();  
12.         } catch (IOException e) {  
13.             e.printStackTrace();  
14.         }  
15.     }  
16. }  

**Output:**

This class is used

### Example 2: Write Data at Specific Position Using RandomAccessFile

In this example, text is written at a specific position in the file.

[](https://www.tpointtech.com/java-randomaccessfile-class#)[](https://www.tpointtech.com/java-randomaccessfile-class#)[](https://www.tpointtech.com/java-randomaccessfile-class#)

1. import java.io.RandomAccessFile;  
2. import java.io.IOException;  

3. public class RandomAccessFileExample2 {  
4.     public static void main(String[] args) {  
5.         try {  
6.             RandomAccessFile file = new RandomAccessFile("myFile.txt", "rw");  
7.             file.seek(31);  
8.             file.write("I love my country and my people".getBytes());  
9.             file.close();  
10.         } catch (IOException e) {  
11.             e.printStackTrace();  
12.         }  
13.     }  
14. }  

**File Content After Execution:**

This class is used for reading I love my country and my people.