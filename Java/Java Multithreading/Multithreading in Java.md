Multithreading in Java allows multiple threads to run concurrently within a single program. In this chapter, we will learn the concepts, benefits, and implementation of multithreading.

## What is Multithreading in Java?

**Multithreading** is a process of executing multiple threads simultaneously within a single program. A **thread** is the smallest unit of execution in a program, and **multithreading** allows multiple threads to share the same memory and resources while running concurrently. This improves the performance of programs by making better use of CPU resources and enables tasks such as background processing, parallel computation, and responsive user interfaces.

In Java, multithreading can be implemented by:

1. Extending the Thread class
2. Implementing the Runnable interface

## Multithreading Using Extending the Thread Class

You can create a thread by extending the **Thread** class and overriding its **run()** method. The **run()** method contains the code that defines the thread’s task. After creating an object of the subclass, you start the thread using the **start()** method.

### Syntax

The syntax to implement multithreading using extending the Thread class is as follows:

[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)

1. class MyThread extends Thread {  
2.     public void run() {  
3.         // Code to be executed in the thread  
4.     }  
5. }  

6. public class TestThread {  
7.     public static void main(String[] args) {  
8.         MyThread t1 = new MyThread();  
9.         t1.start(); // Starts the thread  
10.     }  
11. }  

### Example

The following example demonstrates creating a thread by extending the Thread class:

[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)

1. class MyThread extends Thread {  
2.     public void run() {  
3.         for(int i = 1; i <= 5; i++) {  
4.             System.out.println("Thread running: " + i);  
5.         }  
6.     }  
7. }  

8. public class ThreadExample {  
9.     public static void main(String[] args) {  
10.         MyThread t1 = new MyThread();  
11.         t1.start();  
12.     }  
13. }  

**Output:**

Thread running: 1
Thread running: 2
Thread running: 3
Thread running: 4
Thread running: 5

**Explanation:**

The **run()** method contains the code executed by the thread. Calling **start()** initiates a new thread and executes the **run()** method concurrently with the main thread.

## Multithreading by Implementing the Runnable Interface

Another way to create a thread is by implementing the Runnable interface and providing an implementation for the **run()** method. You then pass the Runnable object to a Thread object and call **start()**. This approach can be used when your class is already extending another class.

### Syntax

The syntax to implement multithreading by implementing the Runnable interface is as follows:

[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)

1. class MyRunnable implements Runnable {  
2.     public void run() {  
3.         // Code to be executed in the thread  
4.     }  
5. }  

6. public class TestRunnable {  
7.     public static void main(String[] args) {  
8.         MyRunnable r = new MyRunnable();  
9.         Thread t1 = new Thread(r);  
10.         t1.start(); // Starts the thread  
11.     }  
12. }  

### Example

The following example demonstrates creating a thread by implementing Runnable:

[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)

1. class MyRunnable implements Runnable {  
2.     public void run() {  
3.         for(int i = 1; i <= 5; i++) {  
4.             System.out.println("Runnable Thread: " + i);  
5.         }  
6.     }  
7. }  

8. public class RunnableExample {  
9.     public static void main(String[] args) {  
10.         MyRunnable r = new MyRunnable();  
11.         Thread t1 = new Thread(r);  
12.         t1.start();  
13.     }  
14. }  

**Output:**

Thread running: 1
Thread running: 2
Thread running: 3
Thread running: 4
Thread running: 5

**Explanation:**

By implementing Runnable, the thread’s task is defined in the **run()** method, and the thread is started by creating a Thread object with the Runnable instance. This approach allows better flexibility and supports [multiple inheritance](https://www.tpointtech.com/multiple-inheritance-in-java) indirectly.

## Life Cycle of a Thread in Java Multithreading

In Java, a thread goes through different states from its creation to its termination. To manage the threads in multithreading, it is important to understand the [life cycle of a thread](https://www.tpointtech.com/thread-life-cycle-in-java) (or, a flow of the threads). The main states of a thread are:

1. **New (Created)**: A thread is created but not yet started. It enters this state when you create an object of the Thread class.
2. **Runnable**: After calling the **start()** method, the thread becomes ready to run and waits for CPU scheduling. It is now eligible to run but may not be running immediately.
3. **Running**: When the thread scheduler picks the thread from the runnable pool, it enters the running state and executes its **run()** method.
4. **Waiting/Blocked**: A thread can enter a waiting state if it is waiting for another thread to perform a task or release a resource.
5. **Timed Waiting**: A thread can wait for a specified period using methods like sleep(milliseconds) or join(milliseconds).
6. **Terminated (Dead)**: Once the thread completes its execution or is stopped, it enters the terminated state. A terminated thread cannot be restarted.

### Thread Life Cycle Diagram

The following image shows the thread life cycle:

![Multithreading in Java](https://images.tpointtech.com/core/images/life-cycle-of-a-thread-in-java-multithreading.jpg)

## Java Thread Class and Thread Methods

Java provides the **Thread** class to implement multithreading. The Thread class includes constructors and methods to create, manage, and control threads. It extends the Object class and implements the Runnable interface that allows the threads to be executed concurrently.

### Thread Methods

The following are the Thread class methods used for multithreading:

|Modifier and Type|Method|Description|
|---|---|---|
|void|[start()](https://www.tpointtech.com/java-thread-start-method)|It is used to start the execution of the thread.|
|void|[run()](https://www.tpointtech.com/java-thread-run-method)|It is used to do an action for a thread.|
|static void|[sleep()](https://www.tpointtech.com/java-thread-sleep-method)|It sleeps a thread for the specified amount of time.|
|static Thread|[currentThread()](https://www.tpointtech.com/java-thread-currentthread-method)|It returns a reference to the currently executing thread object.|
|void|[join()](https://www.tpointtech.com/java-thread-join-method)|It waits for a thread to die.|
|int|[getPriority()](https://www.tpointtech.com/java-thread-getpriority-method)|It returns the priority of the thread.|
|void|[setPriority()](https://www.tpointtech.com/java-thread-setpriority-method)|It changes the priority of the thread.|
|String|[getName()](https://www.tpointtech.com/java-thread-getname-method)|It returns the name of the thread.|
|void|[setName()](https://www.tpointtech.com/java-thread-setname-method)|It changes the name of the thread.|
|long|[getId()](https://www.tpointtech.com/java-thread-getid-method)|It returns the ID of the thread.|
|boolean|[isAlive()](https://www.tpointtech.com/java-thread-isalive-method)|It tests if the thread is alive.|
|static void|[yield()](https://www.tpointtech.com/java-thread-yield-method)|It causes the currently executing thread object to pause and allow other threads to execute temporarily.|
|void|[suspend()](https://www.tpointtech.com/java-thread-suspend-method)|It is used to suspend the thread.|
|void|[resume()](https://www.tpointtech.com/java-thread-resume-method)|It is used to resume the suspended thread.|
|void|[stop()](https://www.tpointtech.com/java-thread-stop-method)|It is used to stop the thread.|
|void|[destroy()](https://www.tpointtech.com/java-thread-destroy-method)|It is used to destroy the thread group and all of its subgroups.|
|boolean|[isDaemon()](https://www.tpointtech.com/java-thread-isdaemon-method)|It tests if the thread is a daemon thread.|
|void|[setDaemon()](https://www.tpointtech.com/java-thread-setdaemon-method)|It marks the thread as a daemon or a user thread.|
|void|[interrupt()](https://www.tpointtech.com/java-thread-interrupt-method)|It interrupts the thread.|
|boolean|[isinterrupted()](https://www.tpointtech.com/java-thread-isinterrupted-method)|It tests whether the thread has been interrupted.|
|static boolean|[interrupted()](https://www.tpointtech.com/java-thread-interrupted-method)|It tests whether the current thread has been interrupted.|
|static int|[activeCount()](https://www.tpointtech.com/java-thread-activecount-method)|It returns the number of active threads in the current thread's thread group.|
|void|[checkAccess()](https://www.tpointtech.com/java-thread-checkaccess-method)|It determines if the currently running thread has permission to modify the thread.|
|static boolean|[holdLock()](https://www.tpointtech.com/java-thread-holdlock-method)|It returns true if and only if the current thread holds the monitor lock on the specified object.|
|static void|[dumpStack()](https://www.tpointtech.com/java-thread-dumpstack-method)|It is used to print a stack trace of the current thread to the standard error stream.|
|StackTraceElement[]|[getStackTrace()](https://www.tpointtech.com/java-thread-getstacktrace-method)|It returns an array of stack trace elements representing the stack dump of the thread.|
|static int|[enumerate()](https://www.tpointtech.com/java-thread-enumerate-method)|It is used to copy every active thread's thread group and its subgroup into the specified array.|
|Thread.State|[getState()](https://www.tpointtech.com/java-thread-getstate-method)|It is used to return the state of the thread.|
|ThreadGroup|[getThreadGroup()](https://www.tpointtech.com/java-thread-getthreadgroup-method)|It is used to return the thread group to which this thread belongs|
|String|[toString()](https://www.tpointtech.com/java-thread-tostring-method)|It is used to return a string representation of this thread, including the thread's name, priority, and thread group.|
|void|[notify()](https://www.tpointtech.com/java-thread-notify-method)|It is used to give a notification for only one thread that is waiting for a particular object.|
|void|[notifyAll()](https://www.tpointtech.com/java-thread-notifyall-method)|It is used to give a notification to all waiting threads of a particular object.|
|void|[setContextClassLoader()](https://www.tpointtech.com/java-thread-setcontextclassloader-method)|It sets the context ClassLoader for the Thread.|
|ClassLoader|[getContextClassLoader()](https://www.tpointtech.com/java-thread-getcontextclassloader-method)|It returns the context ClassLoader for the thread.|
|Static Thread.UncaughtExceptionHandler|[getDefaultUncaughtExceptionHandler()](https://www.tpointtech.com/java-thread-getdefaultuncaughtexceptionhandler-method)|It returns the default handler invoked when a thread abruptly terminates due to an uncaught exception.|
|static void|[setDefaultUncaughtExceptionHandler()](https://www.tpointtech.com/java-thread-setdefaultuncaughtexceptionhandler-method)|It sets the default handler invoked when a thread abruptly terminates due to an uncaught exception.|

## Real-Life Examples of Multithreading

Multithreading is widely used in real-world applications to perform multiple tasks simultaneously. Here are two practical examples:

### Example 1: Online Banking Transactions

In online banking systems, multiple users can perform transactions like deposits, withdrawals, and fund transfers at the same time. Each transaction can run on a separate thread that allows the system to process multiple requests concurrently without delays.

The following code demonstrates multithreading in an online banking transaction:

[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)

1. class BankTransaction extends Thread {  
2.     private String transactionName;  

3.     BankTransaction(String name) {  
4.         this.transactionName = name;  
5.     }  

6.     public void run() {  
7.         System.out.println(transactionName + " started.");  
8.         try {  
9.             Thread.sleep(2000); // Simulate processing time  
10.         } catch (InterruptedException e) {  
11.             e.printStackTrace();  
12.         }  
13.         System.out.println(transactionName + " completed.");  
14.     }  

15.     public static void main(String[] args) {  
16.         BankTransaction t1 = new BankTransaction("Deposit");  
17.         BankTransaction t2 = new BankTransaction("Withdrawal");  

18.         t1.start();  
19.         t2.start();  
20.     }  
21. }    

**Output:**

Deposit started.
Withdrawal started.
Deposit completed.
Withdrawal completed.

### Example 2: Web Server Handling Multiple Clients

A web server can handle multiple client requests simultaneously by assigning each request to a separate thread. This ensures that the server remains responsive even when many clients are connected.

The following code demonstrates multithreading for a web server handling multiple clients:

[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)[](https://www.tpointtech.com/multithreading-in-java#)

1. class ClientRequest extends Thread {  
2.     private String clientName;  

3.     ClientRequest(String name) {  
4.         this.clientName = name;  
5.     }  

6.     public void run() {  
7.         System.out.println(clientName + " request processing started.");  
8.         try {  
9.             Thread.sleep(1500); // Simulate request handling  
10.         } catch (InterruptedException e) {  
11.             e.printStackTrace();  
12.         }  
13.         System.out.println(clientName + " request processing completed.");  
14.     }  

15.     public static void main(String[] args) {  
16.         ClientRequest c1 = new ClientRequest("Client1");  
17.         ClientRequest c2 = new ClientRequest("Client2");  

18.         c1.start();  
19.         c2.start();  
20.     }  
21. }  

**Output:**

Client1 request processing started.
Client2 request processing started.
Client1 request processing completed.
Client2 request processing completed.

## Advantages of Using Multithreading

Here are some of the advantages of using multithreading:

- **Better CPU Utilization:**  
    With multithreading, multiple threads can run concurrently which allows the CPU to execute several tasks at the same time. In this way, CPU resources are fully utilized, reduces the idle time, and improves overall system performance.
- **Faster Execution:**  
    By running tasks in parallel, multithreading can complete operations much faster than sequential execution. For example, multiple calculations or data-processing tasks can be handled simultaneously, that reduces the total execution time.
- **Improved Responsiveness:**  
    In applications with user interfaces, multithreading allows background tasks to run without freezing the main program. This keeps the application responsive to user input, even while performing heavy processing in the background.
- **Resource Sharing:**  
    Threads within the same process share memory and resources that makes communication and data exchange between tasks simpler and more efficient compared to processes that run independently.
- **Background Processing:**  
    Multithreading allows time-consuming tasks to run in the background without interrupting the main workflow.