Synchronization in Java is a mechanism that controls access to shared resources to prevent data inconsistency in multithreaded programs.

In this chapter, you will learn how synchronization works in Java, why it is needed, and how to use synchronized methods and blocks to ensure thread-safe execution.

## Understanding Threads and Shared Resources

A [thread](https://www.tpointtech.com/threads-in-java) represents an independent path of execution within a program. When multiple threads access shared resources concurrently, unpredictable interleaving of operations may lead to data inconsistency. Consider a scenario where two threads increment a shared variable at the same time:

[](https://www.tpointtech.com/synchronization-in-java#)[](https://www.tpointtech.com/synchronization-in-java#)[](https://www.tpointtech.com/synchronization-in-java#)

1. class Counter {  
2.     private int count = 0;      
3.     public void increment() {  
4.         count++;  
5.     }  
6. }  

If two threads execute the increment() method simultaneously, both may read the same value of count, increment it, and write it back. As a result, one update can overwrite the other, leading to incorrect final values. This situation is known as a **race condition**.

## Introducing Synchronization

**Synchronization** addresses such issues by ensuring that only one thread at a time can access a critical section of code or a shared resource associated with an object. This exclusive access prevents race conditions and maintains data consistency.

Java provides two primary mechanisms for synchronization:

- **Synchronized methods**
- **Synchronized blocks**

These mechanisms allow developers to control thread access and ensure safe execution in multithreaded environments.

## Synchronized Methods

In Java, you can declare entire methods as synchronized which prevent multiple threads from accessing the method simultaneously. With this, synchronization becomes a simpler process because the mechanism is applied to all invocations of the synchronized method automatically.

### Example

In this example, the SynchronizedCounter class uses synchronized methods to ensure that only one thread at a time can modify or access the shared count variable, preventing race conditions and ensuring thread safety.

[](https://www.tpointtech.com/synchronization-in-java#)[](https://www.tpointtech.com/synchronization-in-java#)[](https://www.tpointtech.com/synchronization-in-java#)

1. class SynchronizedCounter {  
2.     private int count = 0;      
3.     public synchronized void increment() {  
4.         count++;  
5.     }      
6.     public synchronized int getCount() {  
7.         return count;  
8.     }  
9. }  

With this modification, concurrent calls to increment() or getCount() will be synchronized, preventing race conditions.

## Synchronized Blocks

[Synchronized block](https://www.tpointtech.com/:%20https://www.tpointtech.com/java-synchronized-block) provides exclusive access to shared resources, and only one thread is allowed to execute it in the same time frame. It's structured as follows:

[](https://www.tpointtech.com/synchronization-in-java#)[](https://www.tpointtech.com/synchronization-in-java#)[](https://www.tpointtech.com/synchronization-in-java#)

1. synchronized (object) {  
2.     // Synchronized code block  
3. }  

This monitor object or lock is the subject. While only one thread can be holding a lock on a monitor object at one instance. Other threads that want to go into the synchronized blocks with this object must wait till the lock becomes available.

## Intrinsic Locks and Synchronization

In Java, every object automatically has an intrinsic lock (or monitor lock) associated to it. The moment a thread enters the synchronized block or method, it gets the lock for the object, and then no other thread is allowed to enter the synchronized block or method for that object until the lock is released.

### 1. Deadlocks

On the one hand, synchronization ensures that race condition is ruled out, but on the other hand, it may lead to deadlocks if not used critically. Stalemates could result as two or more threads are ceaseless when they are waiting for resources from each other. Avoid deadlocks by ordering the locks and releasing them in an opposite sequence of both.

### 2. Locking Granularity

The best locking granularity has to be selected and has to avoid contention and thus be good for performance. Leaning too broadly can reduce concurrency, while leaning too finely can lead to overhead increase. Identification of the only section of the code which needs to be the only one having an exclusive access to the shared resources and synchronization of that section alone.

### 3. Concurrent Collections

Java contains a thread-safe versions of the common collections classes that found in the java.util.concurrent package, including the ConcurrentHashMap and ConcurrentLinkedQueue. These classes provide internal synchronization mechanisms that guarantee the thread safety without giving up the synchronization control to the user.

### 4. Volatile Keyword

Furthermore, volatile keyword may be used to maintain the visibility of changes made to the variables among the threads. For variables declared as volatile, their value will always be read directly from memory and the writes to them will be visible to all the other threads immediately. However, volatile does not ensure as such for complex instructions such as incrementing.

### 5. Atomic Classes

Java gives atomic classes in the **java.util.concurrent.atomic** package including Atomic Integer and Atomic Long, which offer atomic operations of variables without using explicit synchronization. These kind of classes use hardware's low level atomic operations to make thread safety.

## Types of Thread Synchronization

There are two types of thread synchronization in Java: mutual exclusive and inter-thread communication.

1. Mutual Exclusive
    1. Synchronized method.
    2. Synchronized block.
    3. Static synchronization.
2. Cooperation (Inter-thread communication in Java)

### 1. Mutual Exclusion

Mutual exclusion prevents threads from interfering with one another while accessing shared data. It ensures that only one thread can execute a critical section at a time.

In Java, mutual exclusion can be achieved in the following ways:

- Using **synchronized methods**
- Using **synchronized blocks**
- Using **static synchronization**

### Concept of Lock

Synchronization is built around an internal entity called a **lock** or **monitor**. Every object in Java has an associated lock. When a thread enters a synchronized method or block:

- It acquires the object's lock
- Executes the critical section
- Releases the lock when execution completes

Other threads must wait until the lock is released before accessing the synchronized code.

From Java 5 onward, the **java.util.concurrent.locks** package provides advanced lock implementations for more flexible synchronization.

### Understanding the Problem without Synchronization

When synchronization is not used, multiple threads can access shared resources simultaneously, leading to unpredictable output.

Consider the following example where the method is not synchronized:

[](https://www.tpointtech.com/synchronization-in-java#)[](https://www.tpointtech.com/synchronization-in-java#)[](https://www.tpointtech.com/synchronization-in-java#)

1. class Table {      
2.     void printTable(int n) {      
3.         for (int i = 1; i <= 5; i++) {      
4.             System.out.println(n * i);      
5.             try {      
6.                 Thread.sleep(400);      
7.             } catch (Exception e) {      
8.                 System.out.println(e);      
9.             }      
10.         }      
11.     }      
12. }      

13. class MyThread1 extends Thread {      
14.     Table t;      
15.     MyThread1(Table t) {      
16.         this.t = t;      
17.     }      
18.     public void run() {      
19.         t.printTable(5);      
20.     }      
21. }      

22. class MyThread2 extends Thread {      
23.     Table t;      
24.     MyThread2(Table t) {      
25.         this.t = t;      
26.     }      
27.     public void run() {      
28.         t.printTable(100);      
29.     }      
30. }      

31. public class Main {      
32.     public static void main(String args[]) {      
33.         Table obj = new Table();      
34.         MyThread1 t1 = new MyThread1(obj);      
35.         MyThread2 t2 = new MyThread2(obj);      
36.         t1.start();      
37.         t2.start();      
38.     }      
39. }        

**Output:**

5
100
10
200
15
300
20
400
25
500

The output is inconsistent because both threads execute the method simultaneously.

### 2. Cooperation (Inter-thread Communication)

Inter-thread communication allows multiple threads to coordinate their execution by communicating with each other instead of competing for a resource. This cooperation is achieved using the wait(), notify(), and notifyAll() methods of the Object class.

Consider a restaurant scenario, where the Cook thread prepares the food, the Customer thread waits until the food is ready, and once the food is prepared, the cook notifies the customer to proceed.

In the below example code, here one thread waits for a condition to be fulfilled while another thread performs an action and notifies the waiting thread to continue execution.

### Example

[](https://www.tpointtech.com/synchronization-in-java#)[](https://www.tpointtech.com/synchronization-in-java#)[](https://www.tpointtech.com/synchronization-in-java#)

1. class Restaurant {  
2.     boolean foodReady = false;  

3.     synchronized void prepareFood() {  
4.         System.out.println("Cook is preparing food...");  
5.         foodReady = true;  
6.         notify(); // Notify waiting customer  
7.     }  

8.     synchronized void serveFood() {  
9.         while (!foodReady) {  
10.             try {  
11.                 System.out.println("Customer is waiting for food...");  
12.                 wait(); // Customer waits  
13.             } catch (InterruptedException e) {  
14.                 System.out.println(e);  
15.             }  
16.         }  
17.         System.out.println("Customer is served food.");  
18.     }  
19. }  

20. public class Main {  
21.     public static void main(String[] args) {  
22.         Restaurant restaurant = new Restaurant();  

23.         Thread customer = new Thread(() -> restaurant.serveFood());  
24.         Thread cook = new Thread(() -> restaurant.prepareFood());  

25.         customer.start();  
26.         cook.start();  
27.     }  
28. }  

**Output:**

Customer is waiting for food...
Cook is preparing food...
Customer is served food.