The volatile keyword in Java is used to ensure visibility and consistency of shared variables across multiple threads.

In this chapter, we will understand what the volatile keyword is, why it is needed in [multithreading](https://www.tpointtech.com/multithreading-in-java), how it works internally, its use cases, examples, important points, and differences between volatile and synchronized.

## What is volatile Keyword in Java?

The **volatile** keyword is used with [variables](https://www.tpointtech.com/types-of-variables-in-java) to indicate that their value may be modified by multiple [threads](https://www.tpointtech.com/threads-in-java) at the same time. It ensures that the value of the variable is always read from and written to the **main memory**, not from the thread’s local cache.

A volatile variable guarantees **visibility** of changes made by one thread to other threads. It also prevents the compiler from reordering instructions related to that variable.

The volatile keyword can be used with primitive data types and object references, but it cannot be applied to classes or [methods](https://www.tpointtech.com/types-of-variables-in-java).

## Why volatile Keyword is Needed?

In multithreaded environments, each thread may keep a local copy of variables in its cache. If one thread updates a variable, other threads may continue using the old cached value, causing **data inconsistency**.

The volatile keyword solves this problem by ensuring that:

- Updates are immediately written to main memory
- All threads always read the latest value

## Problem Without volatile Keyword

Without using volatile, changes made by one thread may not be visible to other threads.

[](https://www.tpointtech.com/volatile-keyword-in-java#)[](https://www.tpointtech.com/volatile-keyword-in-java#)[](https://www.tpointtech.com/volatile-keyword-in-java#)

1. class Test  
2. {  
3. static int var=5;  
4. }  

If two threads run on different processors, each thread may have its own cached copy of var. A change made by one thread may not be reflected in the other thread, leading to inconsistent results.

## Using volatile Keyword

When a variable is declared as volatile, it is never cached locally. All read and write operations happen directly in the main memory.

[](https://www.tpointtech.com/volatile-keyword-in-java#)[](https://www.tpointtech.com/volatile-keyword-in-java#)[](https://www.tpointtech.com/volatile-keyword-in-java#)

1. class Test  
2. {  
3. static volatile int var = 5;  
4. }  

Here, the updated value of var is immediately visible to all threads.

## Example of volatile Keyword

Let us consider a scenario where multiple threads access a shared variable without proper synchronization. In such cases, updates made by one thread may not be visible to other threads, which can lead to unexpected behavior. The volatile keyword helps solve this problem by ensuring visibility of changes across threads.

In this example, we define a class that increases the value of a counter. The run() method in VolatileThread.java reads the counter value before and after updating it. In the main class, an array of threads is created to execute these operations concurrently.

### File: VolatileData.java

[](https://www.tpointtech.com/volatile-keyword-in-java#)[](https://www.tpointtech.com/volatile-keyword-in-java#)[](https://www.tpointtech.com/volatile-keyword-in-java#)

1. public class VolatileData   
2. {  
3. private volatile int counter = 0;   
4. public int getCounter()   
5. {  
6. return counter;  
7. }  
8. public void increaseCounter()   
9. {  
10. ++counter;      //increases the value of counter by 1   
11. }  
12. }  

### File Name: VolatileThread.java

[](https://www.tpointtech.com/volatile-keyword-in-java#)[](https://www.tpointtech.com/volatile-keyword-in-java#)[](https://www.tpointtech.com/volatile-keyword-in-java#)

1. public class VolatileThread extends Thread {  
2.     private final VolatileData data;  

3.     public VolatileThread(VolatileData data) {  
4.         this.data = data;  
5.     }  

6.     public void run() {  
7.         int oldValue = data.getCounter();  
8.         System.out.println("[Thread " + Thread.currentThread().getId() +  
9.                 "]: Old value = " + oldValue);  

10.         data.increaseCounter();  

11.         int newValue = data.getCounter();  
12.         System.out.println("[Thread " + Thread.currentThread().getId() +  
13.                 "]: New value = " + newValue);  
14.     }  
15. }  

### File Name: Main.java

[](https://www.tpointtech.com/volatile-keyword-in-java#)[](https://www.tpointtech.com/volatile-keyword-in-java#)[](https://www.tpointtech.com/volatile-keyword-in-java#)

1. public class Main {  
2.     private final static int noOfThreads = 2;  

3.     public static void main(String[] args) throws InterruptedException {  
4.         VolatileData volatileData = new VolatileData();  
5.         Thread[] threads = new Thread[noOfThreads];  

6.         for (int i = 0; i < noOfThreads; ++i)  
7.             threads[i] = new VolatileThread(volatileData);  

8.         for (int i = 0; i < noOfThreads; ++i)  
9.             threads[i].start();  

10.         for (int i = 0; i < noOfThreads; ++i)  
11.             threads[i].join();  
12.     }  
13. }  

**Output:**

[Thread 22]: Old value = 0
[Thread 22]: New value = 1
[Thread 21]: Old value = 0
[Thread 21]: New value = 2

## When to Use volatile Keyword?

The volatile keyword should be used when a variable is shared between threads and only simple read and write operations are required.

- Use volatile when a variable is accessed by multiple threads
- Use it when one thread updates the value and other threads only read it
- It is commonly used for flags or status variables
- It is suitable for simple read and write operations, not for complex calculations

## Key Facts and Limitations

The following points highlight the key facts and limitations of the volatile keyword in Java.

- The volatile keyword can be applied only to variables
- It ensures visibility of changes but does not provide full synchronization
- Read and write operations on volatile variables are atomic
- It helps reduce memory consistency problems
- A volatile object reference can have a null value
- There is no need to use volatile if a variable is not shared between threads

## Synchronized Vs Volatile Keyword

The volatile keyword is not a substitute for the synchronized keyword, but it can be used as an alternative in certain cases. There are the following differences are as follows:

|volatile Keyword|synchronized Keyword|
|---|---|
|The volatile keyword is a field modifier.|The synchronized keyword modifies code blocks and methods.|
|The thread cannot be blocked for waiting in case of volatile.|Threads can be blocked while waiting in case of synchronized.|
|It improves thread performance.|Synchronized methods degrade the thread performance.|
|It synchronizes the value of one variable at a time between thread memory and main memory.|It synchronizes the value of all variables between thread memory and main memory.|
|Volatile fields are not subject to compiler optimization.|Synchronize is subject to compiler optimization.|
|It does not provide mutual exclusion; multiple threads can access the variable simultaneously.|It provides mutual exclusion; only one thread can access the synchronized block or method at a time.|
|It is suitable for cases where threads perform only read/write operations on a single variable.|It is suitable for scenarios where operations involve multiple variables or compound actions (read-modify-write).|
|It cannot be used to ensure the atomicity of compound actions.|It ensures the atomicity of entire code blocks or methods.|
|Lightweight and less expensive in terms of system resources.|More resource-intensive due to the locking mechanism.|
|It cannot participate in inter-thread signalling using wait/notify.|It can use wait(), notify(), and notifyAll() for inter-thread signalling.|