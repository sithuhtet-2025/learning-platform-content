Thread interruption in Java is a mechanism used to signal a thread to stop its execution or break out of a waiting or sleeping state.

In this chapter, we will learn how thread interruption works, the methods used for interruption, and different behaviors of interrupted threads with examples.

## What is Thread Interruption in Java?

If a thread is in a **sleeping or waiting state** (using sleep() or wait()), calling the interrupt() method causes it to exit that state by throwing an InterruptedException.

If the thread is not in a sleeping or waiting state, calling interrupt() does not stop the thread but sets the **interrupted flag** to true, which can be checked later by the programmer.

## Methods Used for Thread Interruption

Java provides built-in methods in the [Thread class](https://www.tpointtech.com/java-thread) to interrupt a thread and check its interruption status.

### 1. interrupt() Method

The interrupt() method is used to interrupt a thread. If the thread is in a sleeping or waiting state, it throws an InterruptedException. Otherwise, it sets the interrupted flag to true.

**Syntax:**

Here is the syntax of the interrupt() method:

[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)

1. public void interrupt()  

### 2. interrupted() Method

The interrupted() method checks whether the current thread has been interrupted and then clears the interrupted status if it is set.

**Syntax:**

Here is the syntax of the interrupted() method:

[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)

1. public static boolean interrupted()  

### 3. isInterrupted() Method

The isInterrupted() method checks whether a thread has been interrupted without changing the interrupted status.

**Syntax:**

Here is the syntax of the isInterrupted() method:

[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)

1. public boolean isInterrupted()  

## Interrupting a Thread That Stops Working

When a thread is in a sleeping or waiting state and the interrupt() method is called, an InterruptedException is thrown. If this exception is not handled properly and is propagated, the thread terminates immediately and stops its execution.

### Example

In this example, the interrupted thread propagates the exception that causes it to stop execution completely.

[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)

1. class TestInterruptingThread1 extends Thread{  
2. public void run(){  
3. try{  
4. Thread.sleep(1000);  
5. System.out.println("task");  
6. }catch(InterruptedException e){  
7. throw new RuntimeException("Thread interrupted..."+e);  
8. }  

9. }  

10. public static void main(String args[]){  
11. TestInterruptingThread1 t1=new TestInterruptingThread1();  
12. t1.start();  
13. try{  
14. t1.interrupt();  
15. }catch(Exception e){System.out.println("Exception handled "+e);}  

16. }  
17. }  

**Output:**

Exception in thread-0
java.lang.RuntimeException: Thread interrupted...
java.lang.InterruptedException: sleep interrupted
at A.run(A.java:7)

## Interrupting a Thread That Continues Working

When a sleeping or waiting thread is interrupted, an InterruptedException is thrown. If the exception is caught and handled inside the thread, the thread exits the waiting state and continues executing the remaining code normally.

### Example

In this example, the interruption is handled properly, so the thread resumes execution after handling the exception.

[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)

1. class TestInterruptingThread2 extends Thread{  
2. public void run(){  
3. try{  
4. Thread.sleep(1000);  
5. System.out.println("task");  
6. }catch(InterruptedException e){  
7. System.out.println("Exception handled "+e);  
8. }  
9. System.out.println("thread is running...");  
10. }  

11. public static void main(String args[]){  
12. TestInterruptingThread2 t1=new TestInterruptingThread2();  
13. t1.start();  

14. t1.interrupt();  

15. }  
16. }  

**Output:**

Exception handled
java.lang.InterruptedException: sleep interrupted
thread is running...

## Interrupting a Thread in Normal Running State

If a thread is running normally and not in a sleeping or waiting state, calling interrupt() does not stop the thread. Instead, it sets the interrupted flag to true that allows the programmer to check the status and decide how the thread should respond.

### Example

The following example demonstrates that when a running thread is interrupted, it continues its execution normally, and only the interrupted flag is set to indicate the interruption.

[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)

1. class TestInterruptingThread3 extends Thread{  

2. public void run(){  
3. for(int i=1;i<=5;i++)  
4. System.out.println(i);  
5. }  

6. public static void main(String args[]){  
7. TestInterruptingThread3 t1=new TestInterruptingThread3();  
8. t1.start();  

9. t1.interrupt();  

10. }  
11. }  

**Output:**

1
2
3
4
5

## Difference Between isInterrupted() and interrupted()

The isInterrupted() method checks the interrupted status without changing it, whereas the static interrupted() method checks and clears the interrupted flag.

### Example

The following example demonstrates the use of the interrupted() method to check and clear the interrupted status of a thread during execution.

[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)[](https://www.tpointtech.com/interrupting-a-thread#)

1. public class TestInterruptingThread4 extends Thread{  

2. public void run(){  
3. for(int i=1;i<=2;i++){  
4. if(Thread.interrupted()){  
5. System.out.println("code for interrupted thread");  
6. }  
7. else{  
8. System.out.println("code for normal thread");  
9. }  

10. }//end of for loop  
11. }  

12. public static void main(String args[]){  

13. TestInterruptingThread4 t1=new TestInterruptingThread4();  
14. TestInterruptingThread4 t2=new TestInterruptingThread4();  

15. t1.start();  
16. t1.interrupt();  

17. t2.start();  

18. }  
19. }  

**Output:**

Code for interrupted thread
code for normal thread
code for normal thread
code for normal thread