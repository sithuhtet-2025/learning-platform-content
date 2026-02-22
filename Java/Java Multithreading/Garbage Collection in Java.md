Garbage collection in Java is an automatic process that removes unused objects from memory to free heap space. In this chapter, you will learn how garbage collection works and why it is important for efficient memory management.

## What is Garbage Collection in Java?

First understand, **_what is Garbage in Java?_**

In Java, **garbage** means **unreferenced objects**.

**Garbage collection** is an automatic memory management process in which the [Java Virtual Machine (JVM)](https://www.tpointtech.com/jvm-java-virtual-machine) identifies and removes objects that are no longer in use. This helps free heap memory and prevents memory leaks that allows programs to run efficiently without manual memory management.

## Advantages of Using Garbage Collection

The following are some of the important advantages of using Garbage collection:

- Garbage collection automatically frees memory by removing unused objects that reduces the risk of memory leaks in applications and it eliminates the need for manual memory management.
- Garbage collection allows developers to focus more on program logic rather than memory handling.

## How Can an Object Be Unreferenced in Java?

An object becomes eligible for garbage collection when it is no longer referenced by any [variable](https://www.tpointtech.com/java-variables). There are several ways an object can be unreferenced.

### 1. By Nulling a Reference

When a reference variable is assigned null, the object it was pointing to becomes unreferenced.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)

1. Employee e = new Employee();  
2. e = null;  

### 2. By Assigning a Reference to Another Object

When a reference is reassigned to another object, the previously referenced object becomes eligible for garbage collection.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)

1. Employee e1=new Employee();  
2. Employee e2=new Employee();  
3. e1=e2;//now the first object referred by e1 is available for garbage collection  

### 3. By Using an Anonymous Object

An object created without assigning it to any reference is called an anonymous object and is immediately eligible for garbage collection.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)

1. new Employee();  

## Important Methods Used in Garbage Collection

The following methods are commonly used to interact with the garbage collection process:

### 1. System.gc() Method

This method is used to request the JVM to perform garbage collection. The request may or may not be honored by the JVM. It requests garbage collection to free unused memory.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)

1. System.gc();  

### 2. Runtime.getRuntime().gc() Method

This method requests garbage collection through the Runtime class. It requests the JVM to run the garbage collector programmatically.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)

1. Runtime.getRuntime().gc();  

### 3. finalize() method

This method is invoked by the garbage collector before an object is removed from memory. It is used to perform cleanup operations before object destruction.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)

1. protected void finalize() throws Throwable  

#### Note: The Garbage collector of JVM collects only those objects that are created by new keyword. So if you have created any object without new, you can use finalize method to perform cleanup processing (destroying remaining objects).

## Student Record Example Using Garbage Collection

Suppose you are developing a Student Record System. Student objects are created while the program is running. Once some student records are no longer needed, their memory should be released automatically using garbage collection.

### Example Code

Here is the example code that demonstrates garbage collection using a student-based real-world scenario.

[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)[](https://www.tpointtech.com/garbage-collection-in-java#)

1. class Student {  

2.     int rollNo;  
3.     String name;  

4.     Student(int rollNo, String name) {  
5.         this.rollNo = rollNo;  
6.         this.name = name;  
7.     }  

8.     protected void finalize() {  
9.         System.out.println("Student object is garbage collected");  
10.     }  
11. }  

12. public class StudentGCDemo {  

13.     public static void main(String[] args) {  

14.         Student s1 = new Student(1, "Rahul");  
15.         Student s2 = new Student(2, "Anita");  

16.         // Student objects are no longer needed  
17.         s1 = null;  
18.         s2 = null;  

19.         // Requesting garbage collection  
20.         System.gc();  
21.     }  
22. }  

**Output:**

Student object is garbage collected
Student object is garbage collected

In this example, when student objects s1 and s2 are set to null, they become unreachable. The JVM garbage collector automatically removes these unused objects from memory, demonstrating the concept of garbage collection.

## JVM Role in Garbage Collection

Garbage collection is completely managed by the Java Virtual Machine (JVM). The JVM automatically tracks object usage and removes objects that are no longer reachable, without any direct intervention from the programmer.

## When Garbage Collection Runs

Garbage collection runs automatically when the JVM decides that memory needs to be freed. It usually occurs when heap memory is low or when the JVM requires more space for new objects. The exact time of execution depends on the JVM and system conditions.

## The gc() vs Garbage Collection

Calling System.gc() or Runtime.getRuntime().gc() only **requests** garbage collection. The actual garbage collection process is controlled by the JVM, and there is no guarantee that it will run immediately.