Thread life cycle in Java refers to the various states a thread passes through during its execution, from creation to termination, as defined in the **java.lang.Thread.State** class.

All thread states are defined as enum constants in the java.lang.Thread.State class. At any given point in time, a thread can be in only one state.

These states represent virtual machine-level thread states and do not necessarily correspond to the underlying operating system thread states.

## Thread States in Java

Here, we are going to discuss several thread states in Java.

### NEW

A thread is in the NEW state when an instance of Thread is created but the start() method has not yet been invoked. At this stage, the thread is not yet "alive" and is not eligible to be run by the thread scheduler.

[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)

1. public static final Thread.State NEW  

### RUNNABLE

A thread, that is ready to run and invokes the start() method, it moves from the NEW state to RUNNABLE state. In the runnable state, the thread may be running or may be ready to run at any given instant of time. It is the duty of the thread scheduler to provide the thread time to run.

[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)

1. public static final Thread.State RUNNABLE  

A program implementing multithreading acquires a fixed slice of time to each individual thread. Each and every thread runs for a short span of time and when that allocated time slice is over, the thread voluntarily gives up the CPU to the other thread, so that the other threads can also run for their slice of time. Whenever such a scenario occurs, all those threads that are willing to run, waiting for their turn to run, lie in the RUNNABLE state. In the RUNNABLE state, there is a queue where the threads lie.

When the thread gets the CPU, it moves from the RUNNABLE state to the running state. Generally, the most common change in the state of a thread is from RUNNABLE to running and again back to RUNNABLE.

### BLOCKED

A thread enters the BLOCKED state when it is waiting to acquire a monitor lock that is held by another thread. This typically occurs when a thread attempts to enter a synchronized block or method and the lock is unavailable.

[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)

1. public static final Thread.State BLOCKED  

For example, a thread (let's say A) may want to print some data from the printer. However, at the same time, the other thread (let's say B) is using the printer to print some data. Therefore, thread A has to wait for thread B to use the printer. Thus, thread A is in the BLOCKED state. A thread in the BLOCKED state is unable to perform any execution and thus never consume any cycle of the Central Processing Unit (CPU). Hence, we can say that thread A remains idle until the thread scheduler reactivates thread A, which is in the waiting or BLOCKED state.

When the main thread invokes the join() method then, it is said that the main thread is in the WAITING state. The main thread then waits for the child threads to complete their tasks. When the child threads complete their job, a notification is sent to the main thread, which again moves the thread from WAITING to the RUNNABLE state.

If there are a lot of threads in the waiting or blocked state, then it is the duty of the thread scheduler to determine which thread to choose and which one to reject, and the chosen thread is then given the opportunity to run.

### WAITING

A thread transitions to the Waiting state when it is waiting indefinitely for another thread to perform a specific action. It can happen when methods like Object.wait() (without a timeout) or Thread.join() (without a timeout) are called. The thread will remain in this state until it is notified by another thread (for example, via Object.notify() or Object.notifyAll()) or the joined thread completes.

[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)

1. public static final Thread.State WAITING  

The key difference between WAITING and TIMED_WAITING is the time constraint. Waiting has no time constraint, whereas timed waiting has the time constraint. A thread invoking the following method reaches the timed waiting state.

- sleep
- join with timeout
- wait with timeout
- parkUntil
- parkNanos

It represents the final state of a thread that is terminated or dead. A terminated thread means it has completed its execution.

### TIMED_WAITING

Sometimes, waiting for leads to starvation. For example, a thread (its name is A) has entered the critical section of a code and is not willing to leave that critical section. In such a scenario, another thread (its name is B) has to wait forever, which leads to starvation. To avoid such scenario, a timed WAITING state is given to thread B. Thus, thread lies in the WAITING state for a specific span of time, and not forever. A real example of timed waiting is when we invoke the sleep() method on a specific thread. The sleep() method puts the thread in the TIMED WAIT state. After the time runs out, the thread wakes up and start its execution from when it has left earlier.

[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)

1. public static final Thread.State TIMED_WAITING  

### TERMINATED

A thread reaches the TERMINATED state because of the following reasons:

- When a thread has finished its job, then it exists or terminates normally.
- **Abnormal termination:**It occurs when some unusual events such as an unhandled exception or segmentation fault.

A terminated thread means the thread is no more in the system. In other words, the thread is dead, and there is no way one can respawn (active after kill) the dead thread.

[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)

1. public static final Thread.State TERMINATED  

The following diagram shows the different states involved in the life cycle of a thread.

![Java thread life cycle](https://images.tpointtech.com/core/images/life-cycle-of-a-thread.png)

## Transitions Between Thread States

- **NEW → start() → RUNNABLE**  
    A thread moves from the **new** state to the **runnable** state when its start() method is called.
- **RUNNABLE → scheduler picks → RUNNING**  
    The thread enters the **running** state when the JVM thread scheduler selects it for execution.
- **RUNNING → wait()/join() → WAITING**  
    A running thread moves to the **waiting** state when it calls wait() or join() without a timeout.
- **RUNNING → sleep()/join(timeout) → TIMED_WAITING**  
    A thread enters **timed waiting** if it calls sleep() or join() with a specified timeout.
- **RUNNING → BLOCKED → trying to acquire a lock**  
    A running thread becomes **blocked** when it attempts to access a synchronized block or method already locked by another thread.
- **Any state → finished/error → TERMINATED**  
    A thread enters the **terminated** state when it completes execution or terminates due to an exception.

## Example Thread Life Cycle (Thread States)

The following Java program shows some of the states of a thread defined above.

### Example

[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)[](https://www.tpointtech.com/thread-life-cycle-in-java#)

1. // ABC class implements the interface Runnable    
2. class ABC implements Runnable {  
3.     public void run() {  
4. // try-catch block    
5.         try {  
6. // moving thread t2 to the state timed waiting    
7.             Thread.sleep(100);  
8.         } catch (InterruptedException ie) {  
9.             ie.printStackTrace();  
10.         }  
11.         System.out.println(  
12.                 "The state of thread t1 while it invoked the method join() on thread t2 -" + Main.t1.getState());  
13. // try-catch block    
14.         try {  
15.             Thread.sleep(200);  
16.         } catch (InterruptedException ie) {  
17.             ie.printStackTrace();  
18.         }  
19.     }  
20. }  
21. // Thread.State class implements the interface Runnable    
22. public class Main implements Runnable {  
23.     public static Thread t1;  
24.     public static Main obj;  
25. // main method     
26.     public static void main(String argvs[]) {  
27. // creating an object of the class Thread.State    
28.         obj = new Main();  
29.         t1 = new Thread(obj);  
30. // thread t1 is spawned     
31. // The thread t1 is currently in the NEW state.    
32.         System.out.println("The state of thread t1 after spawning it - " + t1.getState());  
33. // invoking the start() method on     
34. // the thread t1    
35.         t1.start();  
36. // thread t1 is moved to the Runnable state    
37.         System.out.println("The state of thread t1 after invoking the method start() on it - " + t1.getState());  
38.     }  
39.     public void run() {  
40.         ABC myObj = new ABC();  
41.         Thread t2 = new Thread(myObj);  
42. // thread t2 is created and is currently in the NEW state.    
43.         System.out.println("The state of thread t2 after spawning it - " + t2.getState());  
44.         t2.start();  
45. // thread t2 is moved to the runnable state    
46.         System.out.println("the state of thread t2 after calling the method start() on it - " + t2.getState());  
47. // try-catch block for the smooth flow of the  program    
48.         try {  
49. // moving the thread t1 to the state timed waiting     
50.             Thread.sleep(200);  
51.         } catch (InterruptedException ie) {  
52.             ie.printStackTrace();  
53.         }  
54.         System.out.println("The state of thread t2 after invoking the method sleep() on it - " + t2.getState());  
55. // try-catch block for the smooth flow of the program    
56.         try {  
57. // waiting for thread t2 to complete its execution    
58.             t2.join();  
59.         } catch (InterruptedException ie) {  
60.             ie.printStackTrace();  
61.         }  
62.         System.out.println("The state of thread t2 when it has completed it's execution - " + t2.getState());  
63.     }  
64. }  

**Output:**

The state of thread t1 after spawning it - NEW
The state of thread t1 after invoking the method start() on it - RUNNABLE
The state of thread t2 after spawning it - NEW
the state of thread t2 after calling the method start() on it - RUNNABLE
The state of thread t1 while it invoked the method join() on thread t2 -TIMED_WAITING
The state of thread t2 after invoking the method sleep() on it - TIMED_WAITING
The state of thread t2 when it has completed it's execution - TERMINATED

**Explanation:** Whenever we spawn a new thread, that thread attains the new state. When the method start() is invoked on a thread, the thread scheduler moves that thread to the runnable state. Whenever the join() method is invoked on any thread instance, the current thread executing that statement has to wait for this thread to finish its execution, i.e., move that thread to the terminated state. Therefore, before the final print statement is printed on the console, the program invokes the method join() on thread t2, making the thread t1 wait while the thread t2 finishes its execution and thus, the thread t2 get to the terminated or dead state. Thread t1 goes to the waiting state because it is waiting for thread t2 to finish it's execution as it has invoked the method join() on thread t2.