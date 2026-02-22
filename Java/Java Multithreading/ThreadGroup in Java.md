A ThreadGroup in Java is used to group multiple threads into a single unit so they can be managed together. In this chapter, you will learn what a ThreadGroup is, why it is used in Java, how to create and manage thread groups, and how ThreadGroup helps in controlling and monitoring multiple threads.

## What is ThreadGroup in Java?

A **ThreadGroup** is a built-in class that allows you to **group multiple threads into a single unit** so they can be managed together.

In simple words, instead of handling threads one by one, ThreadGroup helps you organize and control related threads as a group.

Key points about ThreadGroup are:

- A ThreadGroup represents a collection of threads.
- It is useful for managing, monitoring, and controlling multiple threads at once.
- Operations like interrupting, suspending, or checking active threads can be applied to the entire group.
- Thread groups can contain sub-groups that forms parent–child hierarchy.
- Every thread belongs to some ThreadGroup (by default, the main thread group).

## ThreadGroup Class

The **ThreadGroup** class is provided in the **java.lang** package and is used to organize multiple threads into a single group.

A **ThreadGroup** represents a collection of related threads. It can also contain other thread groups, which allows thread groups to be arranged in a **parent–child hierarchy**. This hierarchy forms a tree structure, where every thread group (except the main thread group) has a parent thread group.

A thread can access information about its own thread group, but it is not allowed to access information about its parent thread group or any other thread groups.

## Importing ThreadGroup

The ThreadGroup class belongs to the java.lang package. Since java.lang is imported automatically by Java, you do not need to explicitly import the ThreadGroup class. You can directly use ThreadGroup in your program without any import statement.

## Constructors of ThreadGroup class

The ThreadGroup class provides only two constructors:

### 1. ThreadGroup(String name)

This constructor creates a new thread group with the specified name.

**Syntax:**

Here is the syntax of the constructor:

[](https://www.tpointtech.com/threadgroup-in-java#)[](https://www.tpointtech.com/threadgroup-in-java#)[](https://www.tpointtech.com/threadgroup-in-java#)

1. ThreadGroup tg = new ThreadGroup("groupName");  

### 2. ThreadGroup(ThreadGroup parent, String name)

This constructor creates a new thread group with the specified name and assigns it to the given parent thread group.

**Syntax:**

Here is the syntax of the constructor:

[](https://www.tpointtech.com/threadgroup-in-java#)[](https://www.tpointtech.com/threadgroup-in-java#)[](https://www.tpointtech.com/threadgroup-in-java#)

1. ThreadGroup tg = new ThreadGroup(parentGroup, "groupName");  

## Methods of ThreadGroup class

There are many methods in ThreadGroup class. A list of ThreadGroup methods is given below.

|Modifier and Type|Method|Description|
|---|---|---|
|void|[checkAccess()](https://www.tpointtech.com/java-threadgroup-checkaccess-method)|This method determines if the currently running thread has permission to modify the thread group.|
|int|[activeCount()](https://www.tpointtech.com/java-threadgroup-activecount-method)|This method returns an estimate of the number of active threads in the thread group and its subgroups.|
|int|[activeGroupCount()](https://www.tpointtech.com/java-threadgroup-activegroupcount-method)|This method returns an estimate of the number of active groups in the thread group and its subgroups.|
|void|[destroy()](https://www.tpointtech.com/java-threadgroup-destroy-method)|This method destroys the thread group and all of its subgroups.|
|int|[enumerate(Thread[] list)](https://www.tpointtech.com/java-threadgroup-enumerate-method)|This method copies into the specified array every active thread in the thread group and its subgroups.|
|int|[getMaxPriority()](https://www.tpointtech.com/java-threadgroup-getmaxpriority-method)|This method returns the maximum priority of the thread group.|
|String|[getName()](https://www.tpointtech.com/java-threadgroup-getname-method)|This method returns the name of the thread group.|
|ThreadGroup|[getParent()](https://www.tpointtech.com/java-threadgroup-getparent-method)|This method returns the parent of the thread group.|
|void|[interrupt()](https://www.tpointtech.com/java-threadgroup-interrupt-method)|This method interrupts all threads in the thread group.|
|boolean|[isDaemon()](https://www.tpointtech.com/java-threadgroup-isdaemon-method)|This method tests if the thread group is a daemon thread group.|
|void|[setDaemon(boolean daemon)](https://www.tpointtech.com/java-threadgroup-setdaemon-method)|This method changes the daemon status of the thread group.|
|boolean|[isDestroyed()](https://www.tpointtech.com/java-threadgroup-isdestroyed-method)|This method tests if this thread group has been destroyed.|
|void|[list()](https://www.tpointtech.com/java-threadgroup-list-method)|This method prints information about the thread group to the standard output.|
|boolean|[parentOf(ThreadGroup g](https://www.tpointtech.com/java-threadgroup-parentof-method)|This method tests if the thread group is either the thread group argument or one of its ancestor thread groups.|
|void|[suspend()](https://www.tpointtech.com/java-threadgroup-suspend-method)|This method is used to suspend all threads in the thread group.|
|void|[resume()](https://www.tpointtech.com/java-threadgroup-resume-method)|This method is used to resume all threads in the thread group which was suspended using suspend() method.|
|void|[setMaxPriority(int pri)](https://www.tpointtech.com/java-threadgroup-setmaxpriority-method)|This method sets the maximum priority of the group.|
|void|[stop()](https://www.tpointtech.com/java-threadgroup-stop-method)|This method is used to stop all threads in the thread group.|
|String|[toString()](https://www.tpointtech.com/java-threadgroup-tostring-method)|This method returns a string representation of the Thread group.|

## Example of Creating ThreadGroup

The following example shows how to create a **ThreadGroup** and assign threads to it.

[](https://www.tpointtech.com/threadgroup-in-java#)[](https://www.tpointtech.com/threadgroup-in-java#)[](https://www.tpointtech.com/threadgroup-in-java#)

1. class MyTask extends Thread {  
2.     MyTask(ThreadGroup group, String name) {  
3.         super(group, name);  
4.     }  

5.     public void run() {  
6.         System.out.println("Thread running: " + Thread.currentThread().getName());  
7.     }  
8. }  

9. public class ThreadGroupExample {  
10.     public static void main(String[] args) {  

11.         // Creating a thread group  
12.         ThreadGroup tg = new ThreadGroup("MyThreadGroup");  

13.         // Creating threads inside the thread group  
14.         MyTask t1 = new MyTask(tg, "Thread-1");  
15.         MyTask t2 = new MyTask(tg, "Thread-2");  

16.         // Starting threads  
17.         t1.start();  
18.         t2.start();  
19.     }  
20. }  

**Output:**

Thread running: Thread-1
Thread running: Thread-2

## More Examples of ThreadGroup Class and Its Methods

Here, we are going to discuss several examples of ThreadGroup Class and its methods.

### Example 1: Creating a ThreadGroup and Adding Threads

This example shows how to create a thread group and add multiple threads to it.

[](https://www.tpointtech.com/threadgroup-in-java#)[](https://www.tpointtech.com/threadgroup-in-java#)[](https://www.tpointtech.com/threadgroup-in-java#)

1. public class ThreadGroupDemo implements Runnable{    
2.     public void run() {    
3.           System.out.println(Thread.currentThread().getName());    
4.     }    
5.    public static void main(String[] args) {    
6.       ThreadGroupDemo runnable = new ThreadGroupDemo();    
7.           ThreadGroup tg1 = new ThreadGroup("Parent ThreadGroup");    

8.           Thread t1 = new Thread(tg1, runnable,"one");    
9.           t1.start();    
10.           Thread t2 = new Thread(tg1, runnable,"two");    
11.           t2.start();    
12.           Thread t3 = new Thread(tg1, runnable,"three");    
13.           t3.start();    

14.           System.out.println("Thread Group Name: "+tg1.getName());    
15.          tg1.list();    

16.     }    
17.    }    

**Output:**

one
two
three
Thread Group Name: Parent ThreadGroup
java.lang.ThreadGroup[name=Parent ThreadGroup,maxpri=10]

### Example 2: Using activeCount() Method in ThreadGroup

This example demonstrates how to find the number of active threads in a thread group using the activeCount() method.

[](https://www.tpointtech.com/threadgroup-in-java#)[](https://www.tpointtech.com/threadgroup-in-java#)[](https://www.tpointtech.com/threadgroup-in-java#)

1. class ThreadNew extends Thread {  

2.     ThreadNew(String name, ThreadGroup group) {  
3.         super(group, name);  
4.         start();  
5.     }  

6.     public void run() {  
7.         try {  
8.             Thread.sleep(500);  
9.         } catch (InterruptedException e) {  
10.             System.out.println(e);  
11.         }  
12.     }  
13. }  

14. public class ActiveCountExample {  

15.     public static void main(String[] args) {  

16.         // Creating a thread group  
17.         ThreadGroup tg = new ThreadGroup("MyThreadGroup");  

18.         new ThreadNew("Thread-1", tg);  
19.         new ThreadNew("Thread-2", tg);  

20.         // Checking active thread count  
21.         System.out.println("Total active threads: " + tg.activeCount());  
22.     }  
23. }  

**Output:**

Total active threads: 2