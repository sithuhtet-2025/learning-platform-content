Thread pools are used to manage and reuse multiple threads while executing concurrent tasks. In this chapter, we will learn how thread pools work and how they improve performance in Java applications.

## What is Thread Pool in Java?

Thread pool is a group of already created threads that are reused to perform multiple tasks. The thread pool is managed by the JVM. Instead of creating a new thread for every task, tasks are given to the thread pool, and available threads execute them. Thread pool improves performance, reduces the cost of creating threads, and manages system resource.

There are the following three conditions when a task is submitted:

1. If a thread is free, it executes the task immediately.
2. If all the threads are busy, the task waits in a queue until a thread becomes available.
3. After completing a task, the thread returns to the pool, not terminated.

## Simple Real-Life Example

A thread pool can be understood by thinking about a restaurant kitchen. The kitchen has a fixed number of chefs who are always available to work. Each food order is treated as a task, and any free chef prepares the order. If all chefs are busy, new orders wait until a chef becomes available. The chefs do not leave after completing one order; instead, they continue working on the next orders. In the same way, a thread pool reuses threads to handle multiple tasks efficiently.

## How a Thread Pool Works?

The following are the three main steps involved in the working of a thread pool:

### Step 1: Waiting State

When tasks are submitted, they are placed in a task queue. The thread pool is created with a fixed number of worker threads, which remain idle and wait for tasks to arrive.

### Step 2: Task Execution

Each available thread picks one task from the queue and starts executing it. If all threads are busy, the remaining tasks stay in the queue until a thread becomes free.

### Step 3: Thread Reuse

After a thread completes its task, it does not terminate. Instead, it becomes available again and immediately takes the next task from the queue. If no tasks are left, the thread stays idle and waits for new tasks.

### Advantages of Thread Pool

The following are some of the main advantages of thread pool:

- Thread pools manage threads efficiently by reusing them instead of creating new threads repeatedly.
- They improve application performance by reducing the overhead of thread creation and destruction.
- Thread pools execute tasks faster because threads are already available and ready to work.
- They limit the number of active threads, which helps prevent high CPU usage and memory problems.
- Thread pools keep applications stable under heavy load by controlling concurrency and queuing tasks when needed.

## Examples of Thread Pool

The following examples demonstrate how thread pools manage and execute multiple tasks efficiently.

### Example 1: Fixed Thread Pool Using ExecutorService

The following example demonstrates how a fixed-size thread pool executes multiple tasks by reusing a limited number of threads.

[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)

1. class WorkerThread implements Runnable {    
2.     private String message;    
3.     public WorkerThread(String s){    
4.         this.message=s;    
5.     }    
6.      public void run() {    
7.         System.out.println(Thread.currentThread().getName()+" (Start) message = "+message);    
8.         processmessage();//call processmessage method that sleeps the thread for 2 seconds    
9.         System.out.println(Thread.currentThread().getName()+" (End)");//prints thread name    
10.     }    
11.     private void processmessage() {    
12.         try {  Thread.sleep(2000);  } catch (InterruptedException e) { e.printStackTrace(); }    }    
13. }    

**File Name:** Main.java

[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)

1. import java.util.concurrent.ExecutorService;  
2. import java.util.concurrent.Executors;  
3. public class Main {  
4.     public static void main(String[] args) {  
5.         ExecutorService executor = Executors.newFixedThreadPool(5);// creating a pool of 5 threads  
6.         for (int i = 0; i < 10; i++) {  
7.             Runnable worker = new WorkerThread("" + i);  
8.             executor.execute(worker);// calling execute method of ExecutorService  
9.         }  
10.         executor.shutdown();  
11.         while (!executor.isTerminated()) {  
12.         }  
13.         System.out.println("Finished all threads");  
14.     }  
15. }  

**Output:**

pool-1-thread-1 (Start) message = 0
pool-1-thread-2 (Start) message = 1
pool-1-thread-3 (Start) message = 2
pool-1-thread-5 (Start) message = 4
pool-1-thread-4 (Start) message = 3
pool-1-thread-2 (End)
pool-1-thread-2 (Start) message = 5
pool-1-thread-1 (End)
pool-1-thread-1 (Start) message = 6
pool-1-thread-3 (End)
pool-1-thread-3 (Start) message = 7
pool-1-thread-4 (End)
pool-1-thread-4 (Start) message = 8
pool-1-thread-5 (End)
pool-1-thread-5 (Start) message = 9
pool-1-thread-2 (End)
pool-1-thread-1 (End)
pool-1-thread-4 (End)
pool-1-thread-3 (End)
pool-1-thread-5 (End)
Finished all threads

### Example 2: Executing Multiple Tasks with Thread Pool

The following example demonstrates how a thread pool handles multiple tasks using a fixed number of threads and executes them in batches.

[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)

1. import java.util.Date;  
2. import java.util.concurrent.ExecutorService;  
3. import java.util.concurrent.Executors;  
4. import java.text.SimpleDateFormat;  
5. class Tasks implements Runnable {  
6.     private String taskName;  
7. // constructor of the class Tasks    
8.     public Tasks(String str) {  
9. // initializing the field taskName     
10.         taskName = str;  
11.     }  
12. // Printing the task name and then sleeps for 1 sec    
13. // The complete process is getting repeated five times    
14.     public void run() {  
15.         try {  
16.             for (int j = 0; j <= 5; j++) {  
17.                 if (j == 0) {  
18.                     Date dt = new Date();  
19.                     SimpleDateFormat sdf = new SimpleDateFormat("hh : mm : ss");  
20. //prints the initialization time for every task    
21.                     System.out.println("Initialization time for the task name: " + taskName + " = " + sdf.format(dt));  
22.                 } else {  
23.                     Date dt = new Date();  
24.                     SimpleDateFormat sdf = new SimpleDateFormat("hh : mm : ss");  
25. // prints the execution time for every task    
26.                     System.out.println("Time of execution for the task name: " + taskName + " = " + sdf.format(dt));  
27.                 }  
28. // 1000ms = 1 sec    
29.                 Thread.sleep(1000);  
30.             }  
31.             System.out.println(taskName + " is complete.");  
32.         } catch (InterruptedException ie) {  
33.             ie.printStackTrace();  
34.         }  
35.     }  
36. }  
37. public class Main {  
38. // Maximum number of threads in the thread pool    
39.     static final int MAX_TH = 3;  
40. // main method    
41.     public static void main(String argvs[]) {  
42. // Creating five new tasks    
43.         Runnable rb1 = new Tasks("task 1");  
44.         Runnable rb2 = new Tasks("task 2");  
45.         Runnable rb3 = new Tasks("task 3");  
46.         Runnable rb4 = new Tasks("task 4");  
47.         Runnable rb5 = new Tasks("task 5");  
48. // creating a thread pool with MAX_TH number of    
49. // threads size the pool size is fixed    
50.         ExecutorService pl = Executors.newFixedThreadPool(MAX_TH);  
51. // passes the Task objects to the pool to execute (Step 3)    
52.         pl.execute(rb1);  
53.         pl.execute(rb2);  
54.         pl.execute(rb3);  
55.         pl.execute(rb4);  
56.         pl.execute(rb5);  
57. // pool is shutdown    
58.         pl.shutdown();  
59.     }  
60. }  

**Output:**

Initialization time for the task name: task 1 = 12 : 14 : 02
Initialization time for the task name: task 3 = 12 : 14 : 02
Initialization time for the task name: task 2 = 12 : 14 : 02
Time of execution for the task name: task 1 = 12 : 14 : 04
Time of execution for the task name: task 3 = 12 : 14 : 04
Time of execution for the task name: task 2 = 12 : 14 : 04
Time of execution for the task name: task 1 = 12 : 14 : 05
Time of execution for the task name: task 3 = 12 : 14 : 05
Time of execution for the task name: task 2 = 12 : 14 : 05
Time of execution for the task name: task 1 = 12 : 14 : 06
Time of execution for the task name: task 3 = 12 : 14 : 06
Time of execution for the task name: task 2 = 12 : 14 : 06
Time of execution for the task name: task 1 = 12 : 14 : 07
Time of execution for the task name: task 3 = 12 : 14 : 07
Time of execution for the task name: task 2 = 12 : 14 : 07
Time of execution for the task name: task 1 = 12 : 14 : 08
Time of execution for the task name: task 3 = 12 : 14 : 08
Time of execution for the task name: task 2 = 12 : 14 : 08
task 1 is complete.
task 3 is complete.
Initialization time for the task name: task 4 = 12 : 14 : 09
Initialization time for the task name: task 5 = 12 : 14 : 09
task 2 is complete.
Time of execution for the task name: task 4 = 12 : 14 : 10
Time of execution for the task name: task 5 = 12 : 14 : 10
Time of execution for the task name: task 4 = 12 : 14 : 11
Time of execution for the task name: task 5 = 12 : 14 : 11
Time of execution for the task name: task 4 = 12 : 14 : 12
Time of execution for the task name: task 5 = 12 : 14 : 12
Time of execution for the task name: task 4 = 12 : 14 : 13
Time of execution for the task name: task 5 = 12 : 14 : 13
Time of execution for the task name: task 4 = 12 : 14 : 14
Time of execution for the task name: task 5 = 12 : 14 : 14
task 4 is complete.
task 5 is complete.

**Explanation:**

It is evident by looking at the output of the program that tasks 4 and 5 are executed only when the thread has an idle thread. Until then, the extra tasks are put in the queue.

The takeaway from the above example is when you wants to execute 50 tasks but is not willing to create 50 threads. In such a case, one can create a pool of 10 threads. Thus, 10 out of 50 tasks are assigned, and the rest are put in the queue. Whenever any thread out of 10 threads becomes idle, it picks up the 11th task. The other pending tasks are treated the same way.

## Tuning the Thread Pool

Choosing the right size for a thread pool depends on the number of available processors and the type of tasks being executed.

- If tasks are **CPU-bound** (only calculations), the best thread pool size is usually equal to the number of processors (P) or P + 1.
- If tasks involve **I/O operations** (such as file or network access), threads spend time waiting. In this case, a larger thread pool is useful.

For I/O-bound tasks, the thread pool size can be estimated using this formula:

Thread Pool Size = P × (1 + W / S)

Where:

- P = number of available processors
- W = waiting time (I/O wait)

S = service time (CPU work)

### Example: Choosing Thread Pool Size

The following example explains how thread pool size is selected based on task type.

If a system has **4 processors** and tasks are mostly CPU-bound, a thread pool size of **4 or 5** works best.  
If tasks spend more time waiting for I/O than processing, a larger pool size helps keep the CPU busy and improves performance.

This approach helps achieve better efficiency and balanced resource usage.

## Thread Pool Methods

Java thread pools provide several methods to manage task execution and control the lifecycle of threads.

### 1. submit(Runnable task)

This method adds a task to the thread pool for execution. The task is placed in the queue and is executed by an available worker thread.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)

1. executorService.submit(task);  

### 2. shutdown()

This method stops the thread pool gracefully. No new tasks are accepted, and all existing tasks are completed before the threads stop.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)

1. executorService.shutdown();  

### 3. shutdownNow()

This method stops the thread pool immediately. It interrupts all running threads and clears the tasks waiting in the queue.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)

1. executorService.shutdownNow();  

### 4. getQueueSize()

This method returns the number of tasks currently waiting in the task queue.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)

1. executor.getQueue().size();  

### 5. getActiveCount()

This method returns the number of threads that are actively executing tasks.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)[](https://www.tpointtech.com/java-thread-pool#)

1. executor.getActiveCount();  

## Risks and Considerations in Thread Pools

The following are some common risks involved in using thread pools:

- **Deadlock:** Deadlock can occur when all active threads are waiting for tasks that are still in the queue, and no thread is available to execute them.
- **Thread Leakage:** Thread leakage happens when a thread does not return to the pool after completing a task, often due to an unhandled exception. Over time, this can reduce the pool size.
- **Resource Thrashing:** Using too many threads can cause excessive context switching, which wastes CPU time and reduces application performance.