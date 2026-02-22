
Java provides three classes to represent a sequence of characters: String, StringBuffer, and StringBuilder. The String class is an immutable class whereas StringBuffer and StringBuilder classes are mutable. There are many differences between StringBuffer and StringBuilder. The StringBuilder class is introduced since JDK 1.5.

![Difference between StringBuffer and StringBuilder](https://images.tpointtech.com/core/images/stringbuffer-vs-stringbuilder.png "Java - StringBuffer vs StringBuilder")

## What is StringBuffer in Java?

[StringBuffer](https://www.tpointtech.com/stringbuffer-in-java) is a mutable class that is used to create and modify strings without creating new objects. It is thread-safe that means, it is safe to use in [multi-threaded](https://www.tpointtech.com/multithreading-in-java) environments.

### Example

The following example demonstrates the use of StringBuffer:

[](https://www.tpointtech.com/difference-between-stringbuffer-and-stringbuilder#)[](https://www.tpointtech.com/difference-between-stringbuffer-and-stringbuilder#)[](https://www.tpointtech.com/difference-between-stringbuffer-and-stringbuilder#)

1. //Java Program to demonstrate the use of StringBuffer class.  
2. public class BufferTest{  
3.     public static void main(String[] args){  
4.         StringBuffer buffer=new StringBuffer("hello");  
5.         buffer.append("java");  
6.         System.out.println(buffer);  
7.     }  
8. }  

**Output:**

hellojava

The append() method modifies the same StringBuffer object that proves it is mutable.

## What is StringBuilder in Java?

[StringBuilder](https://www.tpointtech.com/stringbuilder-in-java) is a mutable class in Java similar to StringBuffer, but it is not thread-safe. It is faster than StringBuffer and it is commonly used in single-threaded applications.

### Example

The following example demonstrates the use of StringBuilder:

[](https://www.tpointtech.com/difference-between-stringbuffer-and-stringbuilder#)[](https://www.tpointtech.com/difference-between-stringbuffer-and-stringbuilder#)[](https://www.tpointtech.com/difference-between-stringbuffer-and-stringbuilder#)

1. //Java Program to demonstrate the use of StringBuilder class.  
2. public class BuilderTest{  
3.     public static void main(String[] args){  
4.         StringBuilder builder=new StringBuilder("hello");  
5.         builder.append("java");  
6.         System.out.println(builder);  
7.     }  
8. }  

**Output:**

hellojava

Here, the same StringBuilder object is updated using append() that shows the efficient and fast string modification.

## Difference Between StringBuffer and StringBuilder Classes

A list of differences between StringBuffer and StringBuilder classes are given below:

|StringBuffer|StringBuilder|
|---|---|
|StringBuffer is _synchronized_ i.e. thread safe. It means two threads can't call the methods of StringBuffer simultaneously.|StringBuilder is _non-synchronized_ i.e. not thread safe. It means two threads can call the methods of StringBuilder simultaneously.|
|StringBuffer is _less efficient_ than StringBuilder.|StringBuilder is _more efficient_ than StringBuffer.|
|StringBuffer was introduced in Java 1.0|StringBuilder was introduced in Java 1.5|

## Performance Test of StringBuffer and StringBuilder

Let’s look at a program that compares the performance of the StringBuffer and StringBuilder classes.

### Example

The following example demonstrate how to test the performance of StringBuffer and StringBuilder.

[](https://www.tpointtech.com/difference-between-stringbuffer-and-stringbuilder#)[](https://www.tpointtech.com/difference-between-stringbuffer-and-stringbuilder#)[](https://www.tpointtech.com/difference-between-stringbuffer-and-stringbuilder#)

1. //Java Program to demonstrate the performance of StringBuffer and StringBuilder classes.  
2. public class ConcatTest{  
3.     public static void main(String[] args){  
4.         long startTime = System.currentTimeMillis();  
5.         StringBuffer sb = new StringBuffer("Java");  
6.         for (int i=0; i<10000; i++){  
7.             sb.append("Tpoint");  
8.         }  
9.         System.out.println("Time taken by StringBuffer: " + (System.currentTimeMillis() - startTime) + "ms");  
10.         startTime = System.currentTimeMillis();  
11.         StringBuilder sb2 = new StringBuilder("Java");  
12.         for (int i=0; i<10000; i++){  
13.             sb2.append("Tpoint");  
14.         }  
15.         System.out.println("Time taken by StringBuilder: " + (System.currentTimeMillis() - startTime) + "ms");  
16.     }  
17. }  

**Output:**

Time taken by StringBuffer: 16ms
Time taken by StringBuilder: 0ms

In the above example, both StringBuffer and StringBuilder append a string multiple times, but StringBuilder executes faster because it is not synchronized, whereas StringBuffer is thread-safe and has extra overhead.