The SequenceInputStream class in Java is used to read data sequentially from multiple input streams as if they were a single stream.

In this chapter, we will learn what the SequenceInputStream class is, its declaration, constructors, methods, and how to read data from multiple files using different examples.

## What is SequenceInputStream in Java?

The SequenceInputStream class is used to read data from two or more input streams one after another. It reads the data from the first stream completely and then continues reading from the next stream.

This class is useful when data is divided into multiple files and needs to be read in a continuous sequence.

## SequenceInputStream Class Declaration

The following declaration shows how the SequenceInputStream class is defined:

[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)

1. public class SequenceInputStream extends InputStream  

## Constructors of SequenceInputStream Class

The SequenceInputStream class provides constructors to read data from multiple input streams.

### 1. SequenceInputStream(InputStream s1, InputStream s2)

This constructor creates a new input stream that reads data first from s1 and then from s2.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)

1. SequenceInputStream(InputStream s1, InputStream s2)  

### 2. SequenceInputStream(Enumeration e)

This constructor creates a new input stream that reads data from multiple input streams provided through an Enumeration.

**Syntax:**

Here is the syntax of this constructor:

[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)

1. SequenceInputStream(Enumeration<? extends InputStream> e)  

## Methods of SequenceInputStream Class

The SequenceInputStream class provides methods to read data from combined streams.

|Method|Description|
|---|---|
|int read()|It is used to read the next byte of data from the input stream.|
|int read(byte[] ary, int off, int len)|It is used to read len bytes of data from the input stream into the [array](https://www.tpointtech.com/array-in-java) of bytes.|
|int available()|It is used to return the maximum number of byte that can be read from an input stream.|
|void close()|It is used to close the input stream.|

## Examples of SequenceInputStream Class

The following examples demonstrate how to use the SequenceInputStream class in different scenarios.

### Example 1: Reading Data from Two Files Sequentially

This example demonstrates how to read data from two files one after another using SequenceInputStream.

[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)

1. package com.javatpoint;  

2. import java.io.*;  
3. class InputStreamExample {    
4.   public static void main(String args[])throws Exception{    
5.    FileInputStream input1=new FileInputStream("D:\\testin.txt");    
6.    FileInputStream input2=new FileInputStream("D:\\testout.txt");    
7.    SequenceInputStream inst=new SequenceInputStream(input1, input2);    
8.    int j;    
9.    while((j=inst.read())!=-1){    
10.     System.out.print((char)j);    
11.    }    
12.    inst.close();    
13.    input1.close();    
14.    input2.close();    
15.   }    
16. }    

Here, we are assuming that you have two files: testin.txt and testout.txt which have following information:

**testin.txt:**

Welcome to Java IO Programming.

**testout.txt:**

It is the example of Java SequenceInputStream class.

After executing the program, you will get following output:

**Output:**

Welcome to Java IO Programming. It is the example of Java SequenceInputStream class.

### Example 2: Reading from Two Files and Writing into Another File

This example demonstrates how to read data from two files and write the combined data into another file.

[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)

1. package com.javatpoint;  

2. import java.io.*;    
3. class Input1{    
4.   public static void main(String args[])throws Exception{    
5.    FileInputStream fin1=new FileInputStream("D:\\testin1.txt");    
6.    FileInputStream fin2=new FileInputStream("D:\\testin2.txt");    
7.    FileOutputStream fout=new FileOutputStream("D:\\testout.txt");      
8.    SequenceInputStream sis=new SequenceInputStream(fin1,fin2);    
9.    int i;    
10.    while((i=sis.read())!=-1)    
11.    {    
12.      fout.write(i);        
13.    }    
14.    sis.close();    
15.    fout.close();      
16.    fin1.close();      
17.    fin2.close();       
18.    System.out.println("Success..");  
19.   }    
20. }    

**Output:**

Succeess...

**testout.txt:**

[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)

1. Welcome to Java IO Programming. It is the example of Java SequenceInputStream class.  

### Example 3: Reading Data from Multiple Files Using Enumeration

This example demonstrates how to read data from more than two files using SequenceInputStream with Enumeration.

[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)[](https://www.tpointtech.com/java-sequenceinputstream-class#)

1. package com.javatpoint;  
2. import java.io.*;    
3. import java.util.*;    
4. class Input2{    
5. public static void main(String args[])throws IOException{    
6. //creating the FileInputStream objects for all the files    
7. FileInputStream fin=new FileInputStream("D:\\a.txt");    
8. FileInputStream fin2=new FileInputStream("D:\\b.txt");    
9. FileInputStream fin3=new FileInputStream("D:\\c.txt");    
10. FileInputStream fin4=new FileInputStream("D:\\d.txt");    
11. //creating Vector object to all the stream    
12. Vector v=new Vector();    
13. v.add(fin);    
14. v.add(fin2);    
15. v.add(fin3);    
16. v.add(fin4);              
17. //creating enumeration object by calling the elements method    
18. Enumeration e=v.elements();      
19. //passing the enumeration object in the constructor    
20. SequenceInputStream bin=new SequenceInputStream(e);    
21. int i=0;      
22. while((i=bin.read())!=-1){    
23. System.out.print((char)i);    
24. }     
25. bin.close();    
26. fin.close();    
27. fin2.close();    
28. }    
29. }    

The a.txt, b.txt, c.txt and d.txt have following information:

**a.txt:**

Welcome

**b.txt:**

to

**c.txt:**

java

**d.txt:**

programming

**Output:**

Welcometojavaprogramming