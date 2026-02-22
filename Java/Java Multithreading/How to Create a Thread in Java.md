Thread is the smallest unit of execution in a Java program that allows multiple tasks to run concurrently.

In this chapter, we will learn how to create a thread in Java, explore the different ways to define and start a thread, and understand when and why multithreading is used in real-world applications.

## What are Threads in Java?

Threads are lightweight units of a process that allow a program to perform multiple tasks at the same time. They are used to make applications faster and more responsive by using system resources efficiently. Threads are important to implement [multithreading](https://www.tpointtech.com/how-to-create-a-thread-in-java).

## Ways to Create Thread in Java

**Threads** are represented either by instances of the [Thread class](https://www.tpointtech.com/java-thread) or by implementing the [Runnable interface](https://www.tpointtech.com/java-thread). The Thread class provides built-in support for multithreading, while the Runnable interface defines a single method, **run()**, which contains the code to be executed by the thread.

Using Runnable allows you to separate the task from the thread itself that makes the code more organized and reusable.

There are two main ways to create a thread:

1. By Extending the Thread Class
2. By Implementing the Runnable Interface

## Creating a Thread by Extending Thread Class

When you extend the Thread class, you create a custom thread by overriding its **run()** method. You then start the thread using the **start()** method, which moves the thread from the New state to the Runnable state and executes the run() method when the thread gets CPU time.

### Example 1: Creating a Thread by Extending Thread Class

The following example demonstrates how to create a custom thread by extending the Thread class and overriding the run() method:

[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)

1. class Multi extends Thread {    
2.     public void run() {    
3.         System.out.println("thread is running...");    
4.     }    

5.     public static void main(String args[]) {    
6.         Multi t1 = new Multi();    
7.         t1.start();    
8.     }    
9. }  

**Output:**

thread is running...

Here, we define a thread by extending the Thread class. The thread starts executing when we call the start() method.

### Example 2: Using Thread(String name) Constructor

The following example demonstrates how to create a thread by directly using the Thread class constructor with a **custom name**:

[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)

1. public class MyThread1 {    
2.     public static void main(String argvs[]) {    
3.         Thread t = new Thread("My first thread");    
4.         t.start();    
5.         System.out.println(t.getName());    
6.     }    
7. }  

**Output:**

My first thread

In this example, we create a thread object using the Thread(String name) constructor. The thread is started using the start() method, and we can also retrieve its name using getName().

### Example 3: Using Thread(Runnable r, String name) Constructor

The following example demonstrates how to create a thread using the Thread(Runnable r, String name) constructor, which allows specifying both a task and a thread name:

[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)

1. public class MyThread2 implements Runnable {      
2.     public void run() {      
3.         System.out.println("Now the thread is running ...");      
4.     }      

5.     public static void main(String argvs[]) {     
6.         Runnable r1 = new MyThread2();     
7.         Thread th1 = new Thread(r1, "My new thread");      
8.         th1.start();     
9.         System.out.println(th1.getName());    
10.     }      
11. }      

**Output:**

My new thread
Now the thread is running ...

Here, we create a **Runnable task** and pass it to the Thread constructor along with a thread name. The thread executes the run() method when started.

## Creating a Thread by Implementing the Runnable Interface

Another approach is to implement the Runnable interface. The class must implement the **run()** method, which contains the task logic. After that, you create a **Thread** object, passing your Runnable instance to its constructor, and call start().

### Example

The following example demonstrates how to create a thread by implementing the Runnable interface:

[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)[](https://www.tpointtech.com/how-to-create-a-thread-in-java#)

1. class Multi3 implements Runnable {    
2.     public void run() {    
3.         System.out.println("thread is running...");    
4.     }    

5.     public static void main(String args[]) {    
6.         Multi3 m1 = new Multi3();    
7.         Thread t1 = new Thread(m1);  // Using Thread(Runnable r) constructor    
8.         t1.start();    
9.     }    
10. }  

**Output:**

thread is running...

> **Note:** If a class only implements Runnable and does not extend Thread, you must explicitly create a Thread object to execute its run() method.