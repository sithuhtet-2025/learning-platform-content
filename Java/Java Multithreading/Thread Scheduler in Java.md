Thread Scheduler in Java is responsible for deciding the order in which threads are executed by the [Java Virtual Machine (JVM)](https://www.tpointtech.com/jvm-java-virtual-machine). It determines which thread runs at a given time and manages CPU time for multiple threads in a program.

In this chapter, we will explore how the thread scheduler works, understand different thread states, and learn how thread priorities affect the execution order of threads.

## How Thread Scheduler Works in Java?

A **thread scheduler** is responsible for deciding which [thread](https://www.tpointtech.com/threads-in-java) will run and which threads will wait. Only threads that are in the **runnable state** are considered by the thread scheduler.

If there is more than one thread in the runnable state, the thread scheduler decides which thread to execute based on two main factors: **priority** and **time of arrival**.

### 1. Priority

Each thread has a priority between **1 and 10**. Threads with higher priority are more likely to be chosen by the thread scheduler.

### 2. Time of Arrival

If two or more threads have the **same priority**, the scheduler looks at the **time of arrival**. The thread that became runnable first gets executed first.

By using these two factors, the thread scheduler manages the execution order of threads and ensures that multiple threads can share CPU time effectively.

## Working of Thread Scheduler with Example

Let's understand how the thread scheduler works with an example. Suppose there are **five threads** with different **arrival times** and **priorities**. The **thread scheduler** decides which thread gets the CPU first.

- The thread with the **highest priority** is selected to run first.
- If a thread is already running and a **new thread with higher priority** becomes runnable, the current thread can be **pre-empted**, and the higher-priority thread gets CPU time.
- When two threads have the **same priority and arrival time**, the scheduler follows the **First-Come-First-Served (FCFS) principle** that means the thread that arrived first executes first.

This ensures that threads are executed efficiently based on **priority** and **arrival time**.

The following example demonstrates how the thread scheduler selects threads based on priority and arrival time.

![Thread Scheduler in Java](https://images.tpointtech.com/core/images/thread-scheduler-in-java4.png)

## Example: Demonstrating Thread Scheduler

The following example demonstrates how the thread scheduler selects threads based on priority and arrival time.

[](https://www.tpointtech.com/thread-scheduler-in-java#)[](https://www.tpointtech.com/thread-scheduler-in-java#)[](https://www.tpointtech.com/thread-scheduler-in-java#)

1. class MyThread extends Thread {  
2.     public MyThread(String name, int priority) {  
3.         super(name);          // Set thread name  
4.         setPriority(priority); // Set thread priority (1 to 10)  
5.     }  

6.     public void run() {  
7.         System.out.println(getName() + " with priority " + getPriority() + " is running.");  
8.     }  

9.     public static void main(String[] args) {  
10.         MyThread t1 = new MyThread("Thread 1", 3);  
11.         MyThread t2 = new MyThread("Thread 2", 7);  
12.         MyThread t3 = new MyThread("Thread 3", 5);  
13.         MyThread t4 = new MyThread("Thread 4", 7);  
14.         MyThread t5 = new MyThread("Thread 5", 2);  

15.         t1.start();  
16.         t2.start();  
17.         t3.start();  
18.         t4.start();  
19.         t5.start();  
20.     }  
21. }  

**Output:**

Thread 2 with priority 7 is running.
Thread 4 with priority 7 is running.
Thread 3 with priority 5 is running.
Thread 1 with priority 3 is running.
Thread 5 with priority 2 is running.

**Explanation:**

- The thread scheduler usually selects higher-priority threads first.
- Threads with the same priority (like Thread 2 and Thread 4) may execute in FCFS order (whichever becomes runnable first).
- This is a simulation, so exact order can vary depending on the JVM and OS.

## Thread Scheduler Algorithms

On the basis of the above-mentioned factors, the scheduling algorithm is followed by a Java thread scheduler.

### First Come First Serve Scheduling:

In this scheduling algorithm, the scheduler picks the threads thar arrive first in the runnable queue. Observe the following table:

|Threads|Time of Arrival|
|---|---|
|t1|0|
|t2|1|
|t3|2|
|t4|3|

In the above table, we can see that Thread t1 has arrived first, then Thread t2, then t3, and at last t4, and the order in which the threads will be processed is according to the time of arrival of threads.

![Thread Scheduler in Java](https://images.tpointtech.com/core/images/thread-scheduler-in-java.png)

Hence, Thread t1 will be processed first, and Thread t4 will be processed last.

### Time-slicing scheduling:

Usually, the First Come First Serve algorithm is non-preemptive, which is bad as it may lead to infinite blocking (also known as starvation). To avoid that, some time-slices are provided to the threads so that after some time, the running thread has to give up the CPU. Thus, the other waiting threads also get time to run their job.

![Thread Scheduler in Java](https://images.tpointtech.com/core/images/thread-scheduler-in-java2.png)

In the above diagram, each thread is given a time slice of 2 seconds. Thus, after 2 seconds, the first thread leaves the CPU, and the CPU is then captured by Thread2. The same process repeats for the other threads too.

### Preemptive-Priority Scheduling:

The name of the scheduling algorithm denotes that the algorithm is related to the priority of the threads.

![Thread Scheduler in Java](https://images.tpointtech.com/core/images/thread-scheduler-in-java3.png)

Suppose there are multiple threads available in the runnable state. The thread scheduler picks that thread that has the highest priority. Since the algorithm is also preemptive, therefore, time slices are also provided to the threads to avoid starvation. Thus, after some time, even if the highest priority thread has not completed its job, it has to release the CPU because of preemption.