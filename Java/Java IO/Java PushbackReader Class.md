
Java PushbackReader class is used to read character data with the ability to push back one or more characters into the stream.

In this chapter, we will learn what the PushbackReader class is, why it is used, its declaration, constructors, methods, and examples to understand how pushback functionality works in Java.

## What is PushbackReader Class in Java?

The **PushbackReader class** is a character stream reader that extends the FilterReader class. It allows a character that has already been read from the stream to be pushed back so that it can be read again.

The PushbackReader class is mainly used in parsing scenarios where a program needs to read ahead, check a character, and then decide whether to keep it or push it back into the stream.

## PushbackReader Class Declaration

The PushbackReader class is a part of the java.io package and extends the FilterReader class. It provides the ability to push back characters into the input stream so they can be read again. Here is the declaration of PushbackReader class in Java.

[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)

1. public class PushbackReader extends FilterReader  

## Constructors of PushbackReader Class

The PushbackReader class provides constructors that allow creating a reader with a default or specified pushback buffer size.

### 1. PushbackReader(Reader in)

This constructor creates a PushbackReader with a default pushback buffer size of one character.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)

1. PushbackReader push = new PushbackReader(reader);  

### 2. PushbackReader(Reader in, int size)

This constructor creates a PushbackReader with a specified buffer size that allows multiple characters to be pushed back.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)

1. PushbackReader push = new PushbackReader(reader, 5);  

### Example of PushbackReader Class Constructors

The following example demonstrates how to create a PushbackReader object using its constructors with a specified pushback buffer size.

[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)

1. Reader reader = new FileReader("data.txt");  
2. PushbackReader push = new PushbackReader(reader, 5);  

## Methods of PushbackReader Class

The PushbackReader class provides several methods to read characters, push them back into the stream, and manage the reader.

|Method|Description|
|---|---|
|int read()|It is used to read a single character.|
|void mark(int readAheadLimit)|It is used to mark the present position in a stream.|
|boolean ready()|It is used to tell whether the stream is ready to be read.|
|boolean markSupported()|It is used to tell whether the stream supports mark() operation.|
|long skip(long n)|It is used to skip the character.|
|void unread (int c)|It is used to pushes back the character by copying it to the pushback buffer.|
|void unread (char[] cbuf)|It is used to pushes back an array of character by copying it to the pushback buffer.|
|void reset()|It is used to reset the stream.|
|void close()|It is used to close the stream.|

## Examples of Java PushbackReader Class

The following examples demonstrate different use cases of the PushbackReader class, including reading characters, pushing them back, and processing character streams efficiently.

### Example 1: Replacing Characters Using PushbackReader

The following example demonstrates how characters can be unread and conditionally replaced using the PushbackReader class.

[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)

1. import java.io.*;  

2. public class PushbackReaderExample1 {  
3.     public static void main(String[] args) throws Exception {  

4.         char ary[] = {'1','-','-','2','-','3','4','-','-','-','5','6'};  
5.         CharArrayReader reader = new CharArrayReader(ary);  
6.         PushbackReader push = new PushbackReader(reader);  

7.         int i;  
8.         while ((i = push.read()) != -1) {  
9.             if (i == '-') {  
10.                 int j = push.read();  
11.                 if (j == '-') {  
12.                     System.out.print("#*");  
13.                 } else {  
14.                     push.unread(j);  
15.                     System.out.print((char) i);  
16.                 }  
17.             } else {  
18.                 System.out.print((char) i);  
19.             }  
20.         }  
21.         push.close();  
22.     }  
23. }  

**Output:**

1#*2-34#*-56

### Example 2: Reading Ahead and Pushing Back a Character

The following example demonstrates how a character can be read, checked, and pushed back into the stream using PushbackReader.

[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)[](https://www.tpointtech.com/java-pushbackreader-class#)

1. import java.io.*;  

2. public class PushbackReaderExample2 {  
3.     public static void main(String[] args) throws Exception {  

4.         String data = "JAVA";  
5.         CharArrayReader reader = new CharArrayReader(data.toCharArray());  
6.         PushbackReader push = new PushbackReader(reader);  

7.         int ch = push.read();  
8.         System.out.println("First read character: " + (char) ch);  

9.         // Push back the character  
10.         push.unread(ch);  

11.         int reread = push.read();  
12.         System.out.println("Re-read character: " + (char) reread);  

13.         push.close();  
14.     }  
15. }  

**Output:**

First read character: J
Re-read character: J