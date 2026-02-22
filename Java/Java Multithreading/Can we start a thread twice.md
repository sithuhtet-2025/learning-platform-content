Threads in Java allow a program to perform multiple tasks concurrently. Once a thread is started using **start()**, it executes its **run()** method. A thread can be started only once, and trying to start it again will throw an exception. This chapter explains why and how to run the same task multiple times safely.

## Can We Start a Thread Twice in Java?

In Java, a [thread](https://www.tpointtech.com/threads-in-java) cannot be started more than once. Once a thread has been started, calling the start() method again on the same thread object will throw an IllegalThreadStateException.

In other words, a thread runs only once, and any attempt to start it a second time results in an exception.

## Example: Starting a Thread Twice

The following example demonstrates what happens if you try to start a thread twice:

[](https://www.tpointtech.com/can-we-start-a-thread-twice#)[](https://www.tpointtech.com/can-we-start-a-thread-twice#)[](https://www.tpointtech.com/can-we-start-a-thread-twice#)

1. public class TestThreadTwice1 extends Thread {    
2.     public void run() {    
3.         System.out.println("running...");    
4.     }    

5.     public static void main(String args[]) {    
6.         TestThreadTwice1 t1 = new TestThreadTwice1();    
7.         t1.start();    
8.         t1.start(); // Attempting to start the same thread again  
9.     }    
10. }  

**Output:**

running...
Exception in thread "main" java.lang.IllegalThreadStateException

**Explanation:**

- The first call to t1.start() executes the thread normally.
- The second call to t1.start() throws an **IllegalThreadStateException**, because a thread cannot be restarted once it has completed execution.

## Tip to Create and Manage Two Threads for the Same Task

Once a thread is started, it cannot be started again. If you want to run the same task multiple times, you need to create a new thread object each time.

### Example

The following example demonstrates running the same task using two thread objects:

[](https://www.tpointtech.com/can-we-start-a-thread-twice#)[](https://www.tpointtech.com/can-we-start-a-thread-twice#)[](https://www.tpointtech.com/can-we-start-a-thread-twice#)

1. class MyTask extends Thread {  
2.     public void run() {  
3.         System.out.println("Task is running by " + Thread.currentThread().getName());  
4.     }  

5.     public static void main(String[] args) {  
6.         MyTask t1 = new MyTask();  
7.         MyTask t2 = new MyTask(); // Create a new thread object for the same task  

8.         t1.start(); // First thread starts  
9.         t2.start(); // Second thread starts  
10.     }  
11. }  

**Output:**

Task is running by Thread-0
Task is running by Thread-1

> **Note:**If you need to run the same task multiple times, always create a new thread object for each execution. This ensures that each thread can be started and executed independently without throwing an exception.