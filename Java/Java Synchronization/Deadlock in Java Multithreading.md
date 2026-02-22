Deadlock in Java Multithreading is a critical concurrency problem where two or more threads get permanently blocked while waiting for resources held by each other.

In this chapter, we will understand what deadlock is, how it occurs in Java multithreading, its necessary conditions with examples.

## How Deadlock Occurs in Java Multithreading?

Deadlock is a condition in [multithreading](https://www.tpointtech.com/multithreading-in-java) that occurs when two or more [threads](https://www.tpointtech.com/multithreading-in-java) are permanently blocked because each thread is waiting for a lock held by another thread. Since none of the threads can proceed until the required lock is released, they remain stuck waiting for each other, resulting in a deadlock.

![Deadlock in Java](https://images.tpointtech.com/core/images/deadlock-in-java.jpg)

## Necessary Conditions for Deadlock in Multithreading

These are the four necessary conditions that must be present for a deadlock to occur in multithreading:

- **Mutual Exclusion:** At least one resource must be held in a non-shareable mode, meaning only one thread can use the resource at a time.
- **Hold and Wait:** A thread holding at least one resource continues to wait for additional resources that are currently held by other threads.
- **No Preemption:** Resources cannot be forcibly taken away from a thread holding them; the thread must release the resources voluntarily.
- **Circular Wait:** A group of threads exists in a circular chain where each thread holds a resource and waits for another resource held by the next thread in the cycle.

## Example of Deadlock in Java Multithreading

The following Java program demonstrates a deadlock situation where two threads attempt to acquire two shared resources in opposite order that causes both threads to wait indefinitely for each other.

### Example

[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)

1. // Java Program to understand Deadlock   
2. public class Main {      
3.   public static void main(String[] args) {      
4.     final String resource1 = "foo";      
5.     final String resource2 = "bar";      
6.     // t1 tries to lock resource1 then resource2      
7.     Thread t1 = new Thread() {      
8.       public void run() {      
9.           synchronized (resource1) {      
10.            System.out.println("Thread 1: locked resource 1");   // first print statement   
11.            try { Thread.sleep(100);} catch (Exception e) {}      
12.            synchronized (resource2) {      
13.             System.out.println("Thread 1: locked resource 2");   // second print statement   
14.            }      
15.          }      
16.       }      
17.     };      
18.     // t2 tries to lock resource2 then resource1      
19.     Thread t2 = new Thread() {      
20.       public void run() {      
21.         synchronized (resource2) {      
22.           System.out.println("Thread 2: locked resource 2");    // third print statement  
23.           try { Thread.sleep(100);} catch (Exception e) {}      
24.           synchronized (resource1) {      
25.             System.out.println("Thread 2: locked resource 1");    // fourth print statement  
26.           }      
27.         }      
28.       }      
29.     };      
30.     t1.start();      
31.     t2.start();      
32.   }      
33. }     

**Output:**

Thread 1: locked resource 1
Thread 2: locked resource 2

**Explanation**

There are two resources: resource1 and resource2. First thread t1 locks the resource1 and sleeps. Similarly, the second thread, t2, locks resource2 and sleeps. Each thread sleeps for 100 milliseconds.

After that, the first thread, t1, tries to acquire resource2, and the second thread, t2, tries to acquire resource1. However, resource1 is acquired by thread t1, and resource2 is acquired by thread t2, resulting in a deadlock situation, and the same is evident from the output. The second and fourth print statements do not execute.

## More Complicated Deadlocks

Deadlocks are not limited to just two threads. In complex applications, a deadlock can involve multiple threads and resources that makes it harder to detect and resolve.

### Example of a Multi-Thread Deadlock Scenario

Consider the following situation involving four threads:

- **Thread 1** locks resource **A** and waits for **B**
- **Thread 2** locks resource **B** and waits for **C**
- **Thread 3** locks resource **C** and waits for **D**
- **Thread 4** locks resource **D** and waits for **A**

In this case, each thread is waiting for a resource held by another thread, forming a circular dependency. As a result, none of the threads can proceed, and the system enters a deadlock state.

## Deadlocks Detection

Java provides command-line tools that help detect deadlocks in running applications. Follow the steps below to identify a deadlock.

### Step 1: Compile and Run the Program

Compile and execute the Java program that contains a deadlock using the following commands:

[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)

1. javac Main.java  
2. java Main  

At this stage, the program will appear to be running indefinitely due to the deadlock.

![Deadlock in Java](https://images.tpointtech.com/core/images/deadlock-in-java2.png)

### Step 2: Find the Java Process ID

Open a new command prompt window and execute:

[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)

1. jps -l  

This command lists all running Java processes along with their process IDs (PID).

![Deadlock in Java](https://images.tpointtech.com/core/images/deadlock-in-java3.png)

Locate the process running your program (for example, Main) and note its PID (e.g., **8680**).

### Step 3: Print Thread Information

Run the following command by replacingwith the actual process ID:

[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)

1. jcmd <PID> Thread.print  

This command generates a full thread dump of the Java process.

![Deadlock in Java](https://images.tpointtech.com/core/images/deadlock-in-java4.png)

**Output:**

8680:
2025-04-03 13:46:30
Full thread dump Java HotSpot(TM) 64-Bit Server VM (12.0.2+10 mixed mode, sharing):

Threads class SMR info:
_java_thread_list=0x000000ddaf977c70, length=12, elements={
0x000000ddae6d0000, 0x000000ddae6d1000, 0x000000ddae6e9800, 0x000000ddae6f0800,
0x000000ddae6f1800, 0x000000ddae6f5800, 0x000000ddae6f8800, 0x000000ddaf911000,
0x000000ddaf95b000, 0x000000ddaf976000, 0x000000ddaf976800, 0x000000dd8f70f800
}
"Reference Handler" #2 daemon prio=10 os_prio=2 cpu=0.00ms elapsed=448.77s tid=0x000000ddae6d0000 nid=0x5e68 waiting on condition [0x000000ddaf14f000]
java.lang.Thread.State: RUNNABLE
at java.lang.ref.Reference.waitForReferencePendingList(java.base@12.0.2/Native Method)
at java.lang.ref.Reference.processPendingReferences(java.base@12.0.2/Reference.java:241)
at java.lang.ref.Reference$ReferenceHandler.run(java.base@12.0.2/Reference.java:213)

"Finalizer" #3 daemon prio=8 os_prio=1 cpu=0.00ms elapsed=448.77s tid=0x000000ddae6d1000 nid=0x29ac in Object.wait() [0x000000ddaf24e000]
java.lang.Thread.State: WAITING (on object monitor)
at java.lang.Object.wait(java.base@12.0.2/Native Method)
- waiting on <0x000000008a90af78> (a java.lang.ref.ReferenceQueue$Lock)
at java.lang.ref.ReferenceQueue.remove(java.base@12.0.2/ReferenceQueue.java:155)
- locked <0x000000008a90af78> (a java.lang.ref.ReferenceQueue$Lock)
at java.lang.ref.ReferenceQueue.remove(java.base@12.0.2/ReferenceQueue.java:176)
at java.lang.ref.Finalizer$FinalizerThread.run(java.base@12.0.2/Finalizer.java:170)

"Signal Dispatcher" #4 daemon prio=9 os_prio=2 cpu=0.00ms elapsed=448.77s tid=0x000000ddae6e9800 nid=0x5220 runnable [0x0000000000000000]
java.lang.Thread.State: RUNNABLE

"Attach Listener" #5 daemon prio=5 os_prio=2 cpu=0.00ms elapsed=448.77s tid=0x000000ddae6f0800 nid=0x52d8 waiting on condition [0x0000000000000000]
java.lang.Thread.State: RUNNABLE

"C2 CompilerThread0" #6 daemon prio=9 os_prio=2 cpu=15.63ms elapsed=448.77s tid=0x000000ddae6f1800 nid=0x1c4 waiting on condition [0x0000000000000000]
java.lang.Thread.State: RUNNABLE
No compile task

"C1 CompilerThread0" #8 daemon prio=9 os_prio=2 cpu=0.00ms elapsed=448.77s tid=0x000000ddae6f5800 nid=0x5338 waiting on condition [0x0000000000000000]
java.lang.Thread.State: RUNNABLE
No compile task

"Sweeper thread" #9 daemon prio=9 os_prio=2 cpu=0.00ms elapsed=448.77s tid=0x000000ddae6f8800 nid=0x5e70 runnable [0x0000000000000000]
java.lang.Thread.State: RUNNABLE

"Service Thread" #10 daemon prio=9 os_prio=0 cpu=0.00ms elapsed=448.76s tid=0x000000ddaf911000 nid=0x3040 runnable [0x0000000000000000]
java.lang.Thread.State: RUNNABLE

"Common-Cleaner" #11 daemon prio=8 os_prio=1 cpu=0.00ms elapsed=448.75s tid=0x000000ddaf95b000 nid=0x888 in Object.wait() [0x000000ddaff2e000]
java.lang.Thread.State: TIMED_WAITING (on object monitor)
at java.lang.Object.wait(java.base@12.0.2/Native Method)
- waiting on <0x000000008a9e7440> (a java.lang.ref.ReferenceQueue$Lock)
at java.lang.ref.ReferenceQueue.remove(java.base@12.0.2/ReferenceQueue.java:155)
- locked <0x000000008a9e7440> (a java.lang.ref.ReferenceQueue$Lock)
at jdk.internal.ref.CleanerImpl.run(java.base@12.0.2/CleanerImpl.java:148)
at java.lang.Thread.run(java.base@12.0.2/Thread.java:835)
at jdk.internal.misc.InnocuousThread.run(java.base@12.0.2/InnocuousThread.java:134)

"Thread-0" #12 prio=5 os_prio=0 cpu=0.00ms elapsed=448.75s tid=0x000000ddaf976000 nid=0x2100 waiting for monitor entry [0x000000ddb002f000]
java.lang.Thread.State: BLOCKED (on object monitor)
at Main$1.run(Main.java:15)
- waiting to lock <0x000000008a800800> (a java.lang.String)
- locked <0x000000008a800000> (a java.lang.String)

"Thread-1" #13 prio=5 os_prio=0 cpu=0.00ms elapsed=448.75s tid=0x000000ddaf976800 nid=0x593c waiting for monitor entry [0x000000ddb012f000]
java.lang.Thread.State: BLOCKED (on object monitor)
at Main$2.run(Main.java:30)
- waiting to lock <0x000000008a800000> (a java.lang.String)
- locked <0x000000008a800800> (a java.lang.String)

"DestroyJavaVM" #14 prio=5 os_prio=0 cpu=31.25ms elapsed=448.75s tid=0x000000dd8f70f800 nid=0x5db4 waiting on condition [0x0000000000000000]
java.lang.Thread.State: RUNNABLE

"VM Thread" os_prio=2 cpu=0.00ms elapsed=448.78s tid=0x000000ddae6c9000 nid=0x5da4 runnable

"GC Thread#0" os_prio=2 cpu=0.00ms elapsed=448.78s tid=0x000000dd8f750000 nid=0x5b84 runnable

"G1 Main Marker" os_prio=2 cpu=0.00ms elapsed=448.78s tid=0x000000dd8f75d800 nid=0x1134 runnable

"G1 Conc#0" os_prio=2 cpu=0.00ms elapsed=448.78s tid=0x000000dd8f760000 nid=0x3624 runnable

"G1 Refine#0" os_prio=2 cpu=0.00ms elapsed=448.78s tid=0x000000dd8f7fa800 nid=0x56b8 runnable

"G1 Young RemSet Sampling" os_prio=2 cpu=0.00ms elapsed=448.78s tid=0x000000dd8f7fb800 nid=0x2464 runnable
"VM Periodic Task Thread" os_prio=2 cpu=0.00ms elapsed=448.75s tid=0x000000ddaf959800 nid=0x19bc waiting on condition

JNI global refs: 4, weak refs: 0


Found one Java-level deadlock:
=============================
"Thread-0":
waiting to lock monitor 0x000000ddae6db280 (object 0x000000008a800800, a java.lang.String),
which is held by "Thread-1"
"Thread-1":
waiting to lock monitor 0x000000ddae6d9280 (object 0x000000008a800000, a java.lang.String),
which is held by "Thread-0"

Java stack information for the threads listed above:
===================================================
"Thread-0":
at Main$1.run(Main.java:15)
- waiting to lock <0x000000008a800800> (a java.lang.String)
- locked <0x000000008a800000> (a java.lang.String)
"Thread-1":
at Main$2.run(Main.java:30)
- waiting to lock <0x000000008a800000> (a java.lang.String)
- locked <0x000000008a800800> (a java.lang.String)

Found 1 deadlock.

We can see that the output says **Found 1 deadlock**.

### Deadlock Detection Output

In the thread dump output, Java clearly reports the deadlock with a message similar to:

[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)

1. Found one Java-level deadlock:  
2. Found 1 deadlock.  

It also shows which threads are involved, the resources they are holding, and the resources they are waiting for. This confirms the presence of a deadlock.

## Preventing Deadlock

Deadlocks should be addressed at their root cause. In most cases, inconsistent ordering of resource acquisition leads to deadlocks.

The simplest way to prevent deadlocks is to ensure that all threads acquire shared resources in the same order.

### Example: Avoiding Deadlock

The following Java program demonstrates how deadlock can be avoided by acquiring resources in a consistent order.

[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)[](https://www.tpointtech.com/deadlock-in-java#)

1. //Java Program to avoid deadlock     
2. public class Main {      
3.     public static void main(String ar[]) {      
4.         Main test = new Main();      
5.         final resource1 a = test.new resource1();      
6.         final resource2 b = test.new resource2();      
7.    // Thread - 1      
8.     Runnable t1 = new Runnable() {      
9.     public void run() {      
10.         synchronized (b) {      
11.             try {      
12.                 /* Adding delay so that both threads can start trying to lock resources */      
13.                 Thread.sleep(100);      
14.             } catch (InterruptedException e) {      
15.                 e.printStackTrace();      
16.             }      
17.             // Thread - 1 have resource2 but need resource1 also      
18.             synchronized (a) {      
19.                 System.out.println("In block 1");      
20.             }      
21.         }      
22.     }      
23.     };      
24.     // Thread - 2      
25.     Runnable t2 = new Runnable() {      
26.     public void run() {      
27.         synchronized (b) {      
28.             // Thread - 2 have resource2 but need resource1 also      
29.             synchronized (a) {      
30.                 System.out.println("In block 2");      
31.             }      
32.         }      
33.     }      
34.     };      
35.         new Thread(b1).start();    // first thread   
36.         new Thread(b2).start();    // second thread  
37.     }      
38.     // resource1      
39.     private class resource1 {      
40.         private int i = 10;      
41.         public int getI() {      
42.             return i;      
43.         }      
44.         public void setI(int i) {      
45.             this.i = i;      
46.         }      
47.     }      
48.     // resource2      
49.     private class resource2 {      
50.         private int i = 20;      
51.         public int getI() {      
52.             return i;      
53.         }      
54.         public void setI(int i) {      
55.             this.i = i;      
56.         }      
57.     }      
58. }    

**Output:**

In block 1
In block 2

**Explanation**

In the above program, there are two threads, t1 and t2. After both the threads are spawned, thread t1 acquires resource b and sleeps for 100 milliseconds. Meanwhile, thread t2 also tries to acquire resource b, and since it is already acquired by thread t1, thread t2 waits.

After that, thread t1 wakes from sleep, applies a lock on resource a, and then finishes its execution. Thus, releasing both resources, a and b. Thread t2 now acquires resource b and then resource a and does its job. Note that both threads do their task. Hence, there is no deadlock.

### How Deadlock Is Avoided in the Above Program

- Both threads acquire the shared resources in the **same order**.
- Thread t1 acquires resource b, waits briefly, then acquires resource a.
- Thread t2 waits for resource b to be released, then acquires both resources safely.
- Since there is no circular dependency, both threads complete execution successfully.

## How to Avoid Deadlocks?

Deadlocks cannot be completely eliminated, but they can be minimized by following these best practices:

- **Avoid Nested Locks:** Minimize situations where a thread holds one lock while requesting another.
- **Avoid Unnecessary Locks:** Apply synchronization only where it is truly required.
- **Use Thread Join Carefully:** Use join() with time limits to avoid indefinite waiting between threads.

## Important Points About Deadlock

The following points list the common causes of deadlocks and best practices to detect, prevent, and manage them in multithreaded applications:

- Deadlocks can occur when multiple threads use synchronized blocks or methods to access shared resources in an improper way.
- Deadlocks can be avoided by using nested synchronized blocks, as holding multiple locks at the same time increases the chances of a deadlock.
- You should use timeouts with locks so that a thread does not wait forever to acquire a resource.
- Deadlocks cannot be fixed automatically; developers should design code carefully and use tools like VisualVM or JConsole to detect deadlocks during runtime.