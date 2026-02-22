In Java, **String** is an immutable object that is used to store a sequence of characters, whereas **StringBuffer** is a mutable object that allows modifications to the same character sequence. In this chapter, we will understand the difference between String and StringBuffer, along with their definitions and examples.

## What is String in Java?

[String](https://www.tpointtech.com/java-string) represents an immutable sequence of characters that means its value cannot be changed once it is created.

### Example

The following example demonstrates String immutability:

[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)

1. class StringExample {  
2.     public static void main(String[] args) {  
3.         String s = "Hello";  
4.         s = s.concat(" World");  
5.         System.out.println(s);  
6.     }  
7. }  

**Output:**

Hello World

The original string "Hello" is not modified. A new String object is created when concat() is called, which shows that String objects are immutable.

## What is StringBuffer in Java?

[StringBuffer](https://www.tpointtech.com/java-string) represents a mutable sequence of characters that allows changes such as appending or modifying content without creating a new object.

### Example

The following example demonstrates StringBuffer mutability:

[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)

1. class StringBufferExample {  
2.     public static void main(String[] args) {  
3.         StringBuffer sb = new StringBuffer("Hello");  
4.         sb.append(" World");  
5.         System.out.println(sb);  
6.     }  
7. }  

**Output:**

Hello World

Here, the original object is modified using append(), which proves that StringBuffer is mutable.

## Difference between String and StringBuffer

There are many differences between String and StringBuffer. A list of differences between String and StringBuffer are given below:

|String|StringBuffer|
|---|---|
|The String class is immutable.|The StringBuffer class is mutable.|
|String is slow and consumes more memory when we concatenate too many strings because every time it creates new instance.|StringBuffer is fast and consumes less memory when we concatenate t strings.|
|String class overrides the equals() method of Object class. So you can compare the contents of two strings by equals() method.|StringBuffer class doesn't override the equals() method of Object class.|
|String class is slower while performing concatenation operation.|StringBuffer class is faster while performing concatenation operation.|
|String class uses String constant pool.|StringBuffer uses Heap memory|

  
![String vs StringBuffer](https://images.tpointtech.com/images/string-vs-stringbuffer.png)

## Performance Test of String and StringBuffer

This example shows that String is slower in repeated concatenation because it creates new objects each time, while StringBuffer is faster since it modifies the same object, making it more efficient for frequent string changes.

### Example

The following example demonstrate how to test the performance of string and stringbuffer.

[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)

1. public class ConcatTest{  
2.     public static String concatWithString()    {  
3.         String t = "Java";  
4.         for (int i=0; i<10000; i++){  
5.             t = t + "Tpoint";  
6.         }  
7.         return t;  
8.     }  
9.     public static String concatWithStringBuffer(){  
10.         StringBuffer sb = new StringBuffer("Java");  
11.         for (int i=0; i<10000; i++){  
12.             sb.append("Tpoint");  
13.         }  
14.         return sb.toString();  
15.     }  
16.     public static void main(String[] args){  
17.         long startTime = System.currentTimeMillis();  
18.         concatWithString();  
19.         System.out.println("Time taken by Concating with String: "+(System.currentTimeMillis()-startTime)+"ms");  
20.         startTime = System.currentTimeMillis();  
21.         concatWithStringBuffer();  
22.         System.out.println("Time taken by Concating with  StringBuffer: "+(System.currentTimeMillis()-startTime)+"ms");  
23.     }  
24. }  

**Output:**

Time taken by Concating with String: 578ms
Time taken by Concating with StringBuffer: 0ms

The above code, calculates the time required for concatenating a string using the String class and StringBuffer class.

## String and StringBuffer HashCode Test

As shown in the program below, a String returns a new hashcode after concatenation because it creates a new object, whereas StringBuffer retains the same hashcode since the same object is modified.

### Example

The following example demonstrate how to test the hashcode of string and stringbuffer.

[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)[](https://www.tpointtech.com/difference-between-string-and-stringbuffer#)

1. public class InstanceTest{  
2.     public static void main(String args[]){  
3.         System.out.println("Hashcode test of String:");  
4.         String str="java";  
5.         System.out.println(str.hashCode());  
6.         str=str+"tpoint";  
7.         System.out.println(str.hashCode());  

8.         System.out.println("Hashcode test of StringBuffer:");  
9.         StringBuffer sb=new StringBuffer("java");  
10.         System.out.println(sb.hashCode());  
11.         sb.append("tpoint");  
12.         System.out.println(sb.hashCode());  
13.     }  
14. }  

**Output:**

Hashcode test of String:
3254818
229541438
Hashcode test of StringBuffer:
118352462
118352462

## String vs StringBuffer Summary

Quick summary of difference between string and StringBuffer is:

- **String** is immutable, so any modification creates a new object that makes string less efficient for frequent changes.
- **StringBuffer** is mutable, so modifications occur on the same object that makes StringBuffer more efficient for repeated updates.