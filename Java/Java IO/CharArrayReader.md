# Java CharArrayReader Class

Last Updated : 12 Feb 2026

The CharArrayReader class in Java is used to read a character array as a character input stream.

In this chapter, we will learn what the CharArrayReader class is, why it is used, its declaration, constructors, important methods, and how to read character arrays using examples.

### What is CharArrayReader Class in Java?

The **CharArrayReader class** allows a character array to be treated as a character input stream. This means data stored in a character array can be read sequentially just like reading data from a file or any other reader.

It extends the Reader class and is mainly used when character data is already available in memory and needs to be processed using stream-based APIs.

## CharArrayReader Class Declaration

The following declaration shows how the CharArrayReader class is defined:

[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)

1. public class CharArrayReader extends Reader  

## Constructors of CharArrayReader Class

The CharArrayReader class provides constructors to create a reader from a character array.

### 1. CharArrayReader(char[] buf)

This constructor creates a reader that uses the given character array as its input source.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)

1. CharArrayReader reader = new CharArrayReader(charArray);  

### 2. CharArrayReader(char[] buf, int offset, int length)

This constructor creates a reader that reads a specified portion of the character array.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)

1. CharArrayReader reader = new CharArrayReader(charArray, 0, 5);  

### Example of CharArrayReader Class Constructors

The following code shows how the constructors of the CharArrayReader class are used.

[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)

1. char[] data = {'J','a','v','a'};  
2. CharArrayReader r1 = new CharArrayReader(data);  
3. CharArrayReader r2 = new CharArrayReader(data, 1, 3);  

## Methods of CharArrayReader Class

The CharArrayReader class provides methods to read character data from the array.

|Method|Description|
|---|---|
|int read()|It is used to read a single character|
|int read(char[] b, int off, int len)|It is used to read characters into the portion of an array.|
|boolean ready()|It is used to tell whether the stream is ready to read.|
|boolean markSupported()|It is used to tell whether the stream supports mark() operation.|
|long skip(long n)|It is used to skip the character in the input stream.|
|void mark(int readAheadLimit)|It is used to mark the present position in the stream.|
|void reset()|It is used to reset the stream to a most recent mark.|
|void close()|It is used to closes the stream.|

## Examples of Java CharArrayReader Class

The following examples demonstrate how to read character data using the Java CharArrayReader class.

### Example 1: Reading Characters from a Character Array

The following example demonstrates how to read characters sequentially from a character array using the CharArrayReader class.

[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)

1. import java.io.CharArrayReader;  

2. public class CharArrayExample {  
3.     public static void main(String[] args) throws Exception {  
4.         char[] ary = {'j','a','v','a','t','p','o','i','n','t'};  
5.         CharArrayReader reader = new CharArrayReader(ary);  

6.         int k;  
7.         while ((k = reader.read()) != -1) {  
8.             char ch = (char) k;  
9.             System.out.println(ch + " : " + k);  
10.         }  
11.         reader.close();  
12.     }  
13. }  

**Output:**

j : 106
a : 97
v : 118
a : 97
t : 116
p : 112
o : 111
i : 105
n : 110
t : 116

### Example 2: Reading a Portion of a Character Array

The following example demonstrates how to read only a specific portion of a character array using the CharArrayReader class.

[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)[](https://www.tpointtech.com/java-chararrayreader-class#)

1. import java.io.CharArrayReader;  

2. public class CharArrayPartialExample {  
3.     public static void main(String[] args) throws Exception {  
4.         char[] data = {'J','a','v','a','I','O'};  
5.         CharArrayReader reader = new CharArrayReader(data, 0, 4);  

6.         int ch;  
7.         while ((ch = reader.read()) != -1) {  
8.             System.out.print((char) ch);  
9.         }  
10.         reader.close();  
11.     }  
12. }  

**Output:**

Java