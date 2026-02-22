The Java Thread class provides the two variants of the sleep() method. First one accepts only an argument, whereas the other variant accepts two arguments. The method sleep() is being used to halt the working of a thread for a given amount of time. The time up to which the thread remains in the sleeping state is known as the sleeping time of the thread. After the sleeping time is over, the thread starts its execution from where it has left.

## What is Thread.sleep()?

The **Thread.sleep()** method is used to pause the execution of the current thread for a specified amount of time. During this period, the [thread](https://www.tpointtech.com/threads-in-java) does not consume CPU resources and moves to the timed waiting state. After the specified time elapses, the thread becomes **runnable** again and waits for the scheduler to pick it for execution.

To understand the various states and life cycle of a thread, read: [Thread Life Cycle](https://www.tpointtech.com/thread-life-cycle-in-java).

## Syntax

The syntaxes with different parameters of the Thread.sleep() are as follow:

[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)

1. public static void sleep(long mls) throws InterruptedException   
2. public static void sleep(long mls, int n) throws InterruptedException   

Here,

- The version with **one parameter** (millis) is a **native method**; the version with **two parameters** (millis, nanos) is implemented in Java.
- Since it throws a **checked exception**, you must use a **try-catch block** or declare throws InterruptedException.
- Any thread, including the **main thread**, can call Thread.sleep().

## Parameters of Thread.sleep()

The sleep() method takes the following parameters:

- **millis (mls):** Specifies the time in **milliseconds** for which the thread will sleep.
- **nanos (n):** Specifies additional **nanoseconds** (0 to 999,999) to pause the thread for more precise timing.

## Return Type

The sleep() method does not return any value.

## Examples of Thread.sleep() Method

The following are examples showing different use cases of the **Thread.sleep()** method.

### Example 1: Simple Sleep on Main Thread

The following example demonstrates a simple pause of **2 seconds** in the main thread using Thread.sleep().

[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)

1. public class SleepExample {  
2.     public static void main(String[] args) {  
3.         System.out.println("Start");  
4.         try {  
5.             Thread.sleep(2000); // Pause for 2000 milliseconds (2 seconds)  
6.         } catch (InterruptedException e) {  
7.             System.out.println("Thread interrupted");  
8.         }  
9.         System.out.println("End");  
10.     }  
11. }  

**Output:**

Start
End

In this example, the main thread prints "Start", pauses for 2 seconds, and then prints "End".

### Example 2: Handling InterruptedException

The following example shows how to **handle InterruptedException** when a sleeping thread is interrupted by another thread.

[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)

1. public class InterruptHandling {  
2.     public static void main(String[] args) {  
3.         Thread thread = new Thread(() -> {  
4.             try {  
5.                 System.out.println("Thread will sleep for 5 seconds.");  
6.                 Thread.sleep(5000);  
7.                 System.out.println("Thread woke up after sleep.");  
8.             } catch (InterruptedException e) {  
9.                 System.out.println("Thread was interrupted during sleep.");  
10.             }  
11.         });  
12.         thread.start();  
13.         try {  
14.             Thread.sleep(2000); // Main thread sleeps for 2 seconds  
15.             thread.interrupt(); // Interrupt the sleeping thread  
16.         } catch (InterruptedException e) {  
17.             e.printStackTrace();  
18.         }  
19.     }  
20. }  

**Output:**

Thread will sleep for 5 seconds.
Thread was interrupted during sleep.

In this code, the child thread sleeps for 5 seconds but gets interrupted by the main thread after 2 seconds. The catch block handles the interruption gracefully.

### Example 3: Sleep in a Custom Thread

The following example demonstrates using Thread.sleep() in a **custom thread** created by extending the Thread class.

[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)

1. class TestSleepMethod1 extends Thread{    
2.  public void run(){    
3.   for(int i=1;i<5;i++){   
4.   // the thread will sleep for the 500 milli seconds   
5.     try{Thread.sleep(500);}catch(InterruptedException e){System.out.println(e);}    
6.     System.out.println(i);    
7.   }    
8.  }    
9.  public static void main(String args[]){    
10.   TestSleepMethod1 t1=new TestSleepMethod1();    
11.   TestSleepMethod1 t2=new TestSleepMethod1();    

12.   t1.start();    
13.   t2.start();    
14.  }    
15. }    

**Output:**

1
1
2
2
3
3
4
4

As you know well that at a time only one thread is executed. If you sleep a thread for the specified time, the thread scheduler picks up another thread and so on.

### Example 4: Sleep in Main Thread with Loop

The following example shows how the **main thread** can sleep in a loop.

[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)

1. // important import statements  
2. import java.lang.Thread;  
3. import java.io.*;  

4. public class TestSleepMethod2  
5. {  
6.     // main method  
7. public static void main(String argvs[])  
8. {  

9. try {  
10. for (int j = 0; j < 5; j++)  
11. {  

12. // The main thread sleeps for the 1000 milliseconds, which is 1 sec  
13. // whenever the loop runs  
14. Thread.sleep(1000);  

15. // displaying the value of the variable  
16. System.out.println(j);  
17. }  
18. }  
19. catch (Exception expn)   
20. {  
21. // catching the exception  
22. System.out.println(expn);  
23. }  
24. }  
25. }  

**Output:**

0
1
2
3
4

### Example 5: Sleep with Negative Time

The following example demonstrates that **Thread.sleep() throws an exception** when the sleeping time is negative.

[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)[](https://www.tpointtech.com/thread-sleep-in-java#)

1. // important import statements  
2. import java.lang.Thread;  
3. import java.io.*;  

4. public class TestSleepMethod3  
5. {  
6. // main method  
7. public static void main(String argvs[])  
8. {  
9. // we can also use throws keyword followed by  
10. // exception name for throwing the exception  
11. try   
12. {  
13. for (int j = 0; j < 5; j++)   
14. {  

15. // it throws the exception IllegalArgumentException  
16. // as the time is -ive which is -100  
17. Thread.sleep(-100);  

18. // displaying the variable's value  
19. System.out.println(j);  
20. }  
21. }  
22. catch (Exception expn)   
23. {  

24. // the exception iscaught here   
25. System.out.println(expn);  
26. }  
27. }  
28. }  

**Output:**

java.lang.IllegalArgumentException: timeout value is negative