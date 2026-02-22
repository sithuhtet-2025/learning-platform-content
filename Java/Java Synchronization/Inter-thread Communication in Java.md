Inter-thread Communication in Java allows multiple threads to coordinate and communicate with each other to achieve synchronized execution in a multithreaded environment.

In this chapter, we will learn how [threads](https://www.tpointtech.com/threads-in-java) communicate using methods like wait(), notify(), and notifyAll() to efficiently manage shared resources and thread coordination.

## What is Inter-thread Communication in Java?

Inter-thread communication allows multiple threads to coordinate and share resources efficiently by using the wait(), [notify()](https://www.tpointtech.com/java-thread-notify-method), and [notifyAll()](https://www.tpointtech.com/java-thread-notifyall-method) methods of the [Object class](https://www.tpointtech.com/object-class-in-java). These methods help avoid busy waiting (polling) and enable smooth cooperation between threads, such as in the producer–consumer problem.

In this mechanism, one thread pauses its execution by calling wait(), and another thread signals it to resume by calling notify() or notifyAll().

In simple terms, the communication process between synchronized threads is known as **inter-thread communication**.

Inter-thread communication is achieved using the wait(), notify(), and notifyAll() methods of the Object class.

![inter thread communication in java](https://images.tpointtech.com/core/images/inter-thread-communication-in-java-1.png)

To read more [Threads in Java](https://www.tpointtech.com/threads-in-java)

## 1) wait() Method

The wait() method causes current thread to release the lock and wait until either another thread invokes the notify() method or the notifyAll() method for this object, or a specified amount of time has elapsed.

The current thread must own this object's monitor, so it must be called from the synchronized method only otherwise it will throw exception.

|Method|Description|
|---|---|
|public final void wait() throws InterruptedException|It waits until object is notified.|
|public final void wait(long timeout) throws InterruptedException|It waits for the specified amount of time.|

## 2) notify() Method

The notify() method wakes up a single thread that is waiting on this object's monitor. If any threads are waiting on this object, one of them is chosen to be awakened. The choice is arbitrary and occurs at the discretion of the implementation.

### Syntax

It has the following syntax:

[](https://www.tpointtech.com/inter-thread-communication-in-java#)[](https://www.tpointtech.com/inter-thread-communication-in-java#)[](https://www.tpointtech.com/inter-thread-communication-in-java#)

1. public final void notify()  

## 3) notifyAll() Method

The method wakes up all threads that are waiting on this object's monitor.

### Syntax

It has the followig syntax:

[](https://www.tpointtech.com/inter-thread-communication-in-java#)[](https://www.tpointtech.com/inter-thread-communication-in-java#)[](https://www.tpointtech.com/inter-thread-communication-in-java#)

1. public final void notifyAll()  

## Lifecycle of Threads in Inter-thread Communication

![inter thread communication in java](https://images.tpointtech.com/core/images/inter-thread-communication-in-java.png)

The above diagram illustrates how threads interact with object locks during inter-thread communication.

Here are the steps involved in the lifecycle of threads during inter-thread communication:

- Threads attempt to acquire the object’s lock.
- One thread successfully acquires the lock and enters the synchronized block or method.
- If the thread calls the wait() method, it releases the lock and moves to the waiting state. Otherwise, it completes execution and exits.
- When another thread calls notify() or notifyAll(), the waiting thread moves to the notified (runnable) state.
- The notified thread becomes eligible to acquire the lock again.
- After completing its task, the thread releases the lock and exits the object's monitor.

## Object-Level Locking in Inter-thread Communication

In Java, [synchronization](https://www.tpointtech.com/synchronization-in-java) is based on objects rather than threads. Every Java object has an intrinsic lock, also known as a monitor, which is used to control synchronized access. The methods wait(), notify(), and notifyAll() work with these object-level monitors. This is why these methods are defined in the Object class instead of the [Thread class](https://www.tpointtech.com/java-thread).

## Difference Between wait() and sleep() Methods

Let's see the important differences between wait() and sleep() methods.

|wait()|sleep()|
|---|---|
|The wait() method releases the lock.|The sleep() method does not release the lock.|
|It is a [method of Object class](https://www.tpointtech.com/object-class-methods-in-java).|It is a method of Thread class.|
|It is the non-static method.|It is the static method.|
|It should be notified by notify() or notifyAll() methods.|After the specified amount of time, sleep is completed.|
|It must be called inside a synchronized block or method.|It can be called from anywhere.|
|It throws InterruptedException.|It throws InterruptedException.|
|It is used for inter-thread communication (coordination).|It is used to pause execution for a specified duration.|
|Waiting time can be indefinite unless timeout is given.|Always for a fixed time (in milliseconds/nanoseconds).|
|Thread must own the object's monitor before calling wait().|No such requirement.|

To read more [wait() Vs. sleep() in Java](https://www.tpointtech.com/wait-vs-sleep-in-java)

## Example of Inter-thread Communication

The following Java program demonstrates inter-thread communication using the wait() and notify() methods, where one thread waits for a deposit while another thread deposits money and notifies the waiting thread.

[](https://www.tpointtech.com/inter-thread-communication-in-java#)[](https://www.tpointtech.com/inter-thread-communication-in-java#)[](https://www.tpointtech.com/inter-thread-communication-in-java#)

1. //Java Program to understand the use of Inter-Thread Communication  
2. class Customer{      
3.  int amount=10000;      
4.  //creating a withdraw() method which calls the wait() method  
5.  synchronized void withdraw(int amount){      
6.   System.out.println("going to withdraw...");      

7.   if(this.amount<amount){      
8.     System.out.println("Less balance; waiting for deposit...");      
9.     try{wait();}catch(Exception e){}      
10.   }      
11.   this.amount-=amount;      
12.   System.out.println("withdraw completed...");      
13.  }      
14.  //creating a deposit() method with calls the notify() method  
15.  synchronized void deposit(int amount){      
16.   System.out.println("going to deposit...");      
17.   this.amount+=amount;      
18.   System.out.println("deposit completed... ");      
19.   notify();      
20.  }      
21. }      
22. //Creating a Main class to start threads and call deposit() and withdraw()  
23. public class Main{      
24.  public static void main(String args[]){      
25.   final Customer c=new Customer();      
26.   new Thread(){      
27.     public void run(){c.withdraw(15000);}      
28.   }.start();      
29.   new Thread(){      
30.     public void run(){c.deposit(10000);}      
31.   }.start();      
32.  }  
33. }      

**Output:**

going to withdraw...
Less balance; waiting for deposit...
going to deposit...
deposit completed...
withdraw completed