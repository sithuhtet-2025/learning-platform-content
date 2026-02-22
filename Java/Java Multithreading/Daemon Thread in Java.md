A daemon thread in Java is a background thread that provides support to user threads during program execution. These threads run in the background and automatically terminate when all user threads finish execution. In this chapter, we will learn what daemon threads are, how to create them, and how they behave in Java programs.

## What Daemon Threads Are?

In Java, [multithreading](https://www.tpointtech.com/multithreading-in-java) allows multiple tasks to run at the same time. Among [different types of threads](https://www.tpointtech.com/types-of-threads-in-java), **daemon threads** are special threads that run in the background to support other threads.

A **daemon thread** is a low-priority background thread that provides services to user threads, such as garbage collection or monitoring tasks. These threads work silently and do not require direct interaction from the programmer during normal execution.

A [thread](https://www.tpointtech.com/threads-in-java) can be marked as a daemon thread using the **setDaemon(boolean)** method, and its status can be checked using the **isDaemon()** method.

## Lifecycle of Daemon Threads

Daemon thread's life depends entirely on user threads. When all user threads finish execution, the [JVM](https://www.tpointtech.com/threads-in-java) automatically stops all daemon threads. Because of this behavior, daemon threads are mainly used for background tasks that should not prevent the program from terminating.

## Why JVM Terminates Daemon Threads?

The main purpose of a daemon thread is to support user threads by performing background tasks. When there are no user threads running, the daemon threads have no work to do. Therefore, the JVM automatically stops all daemon threads.

## Thread Class Daemon Thread Methods

The java.lang.Thread class provides the following two methods for Java daemon thread.

|No.|Method|Description|
|---|---|---|
|1)|public void setDaemon(boolean status)|It is used to mark the current thread as daemon thread or user thread.|
|2)|public boolean isDaemon()|It is used to check that current is daemon.|

## Steps to Create a Daemon Thread

A thread must be marked as a daemon before it is started. Once a thread starts execution, its daemon status cannot be changed.

Here are the steps to create a daemon thread:

1. [Create a thread](https://www.tpointtech.com/java-thread) using the [Thread class](https://www.tpointtech.com/java-thread) or by implementing the [Runnable interface](https://www.tpointtech.com/runnable-interface-in-java).
2. Call the **setDaemon(true)** method on the thread object to mark it as a daemon thread.
3. Start the thread using the **start()** method.

If the daemon status is set after calling **start()**, the JVM throws an IllegalThreadStateException.

### Syntax

The syntax to mark a thread as daemon thread is:

[](https://www.tpointtech.com/daemon-thread-in-java#)[](https://www.tpointtech.com/daemon-thread-in-java#)[](https://www.tpointtech.com/daemon-thread-in-java#)

1. threadObject.setDaemon(true);  

## Checking Daemon Status

To check whether a thread is a daemon thread or a user thread, Java provides the isDaemon() method.

### Syntax

The syntax to check a daemon thread status is:

[](https://www.tpointtech.com/daemon-thread-in-java#)[](https://www.tpointtech.com/daemon-thread-in-java#)[](https://www.tpointtech.com/daemon-thread-in-java#)

1. threadObject.isDaemon();  

## Examples of Daemon Thread

Practice these examples to understand the concept of daemon threads.

### Example 1: Creating a Daemon Thread

The following example demonstrates how to create a daemon thread and how Java differentiates between daemon threads and user threads.

[](https://www.tpointtech.com/daemon-thread-in-java#)[](https://www.tpointtech.com/daemon-thread-in-java#)[](https://www.tpointtech.com/daemon-thread-in-java#)

1. public class Main extends Thread{     
2. public void run(){     
3.   if(Thread.currentThread().isDaemon()){//checking for daemon thread     
4.    System.out.println("daemon thread work");     
5.   }     
6.   else{     
7.   System.out.println("user thread work");      
8. }     
9. }      
10. public static void main(String[] args){      
11.   Main t1=new Main();//creating thread     
12.   Main t2=new Main();     
13.   Main t3=new Main();          
14.   t1.setDaemon(true);//now t1 is daemon thread     
15.   t1.start();//starting threads      
16.   t2.start();      
17.   t3.start();     
18. }     
19. }     

**Output:**

daemon thread work
user thread work
user thread work

#### Note: If you want to make a user thread as Daemon, it must not be started otherwise it will throw IllegalThreadStateException. Consider the following example for the same.

### Example 2: IllegalThreadStateException in Daemon Thread

A thread must be marked as a daemon **before calling the start() method**. If setDaemon(true) is called after the thread has started, Java throws an IllegalThreadStateException.

[](https://www.tpointtech.com/daemon-thread-in-java#)[](https://www.tpointtech.com/daemon-thread-in-java#)[](https://www.tpointtech.com/daemon-thread-in-java#)

1. class Main extends Thread{    
2. public void run(){    
3.   System.out.println("Name: "+Thread.currentThread().getName());    
4.   System.out.println("Daemon: "+Thread.currentThread().isDaemon());    
5. }    
6. public static void main(String[] args){    
7.   Main t1=new Main();    
8.   Main t2=new Main();    
9.   t1.start();    
10.   t1.setDaemon(true);//will throw exception here    
11.   t2.start();    
12. }    
13. }    

**Output:**

exception in thread main: java.lang.IllegalThreadStateException