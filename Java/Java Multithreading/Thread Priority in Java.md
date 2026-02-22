In this chapter, we will learn how thread priorities work, how to set and retrieve them, and how Java handles threads with equal priorities.

## What is Thread Priority in Java?

In Java, each [thread](https://www.tpointtech.com/threads-in-java) is assigned a priority that helps the [thread scheduler](https://www.tpointtech.com/thread-scheduler-in-java) decide the order of execution. **Thread priorities** are represented by numeric values ranging from 1 to 10. Although higher-priority threads generally get preference during execution, the actual scheduling behavior depends on the JVM and the underlying operating system.

## Thread Priority Values

Every thread has a priority value between 1 and 10:

- **1** is the minimum priority
- **10** is the maximum priority

In most cases, the thread scheduler follows pre-emptive scheduling, where higher-priority threads are executed before lower-priority ones. However, this behavior is not guaranteed, as thread scheduling is JVM-dependent. A programmer can explicitly assign priorities to threads within a program.

## Setter and Getter Methods of Thread Priority

Java provides two built-in methods to work with thread priority:

### 1. getPriority() Method

The java.lang.Thread.getPriority() method returns the priority of the given thread.

**Syntax**

The syntax of the method is:

[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)

1. public final int getPriority()  

### 2. setPriority(int newPriority) Method

The java.lang.Thread.setPriority() method updates or assign the priority of the thread to newPriority. The method throws IllegalArgumentException if the value newPriority goes out of the range, which is 1 (minimum) to 10 (maximum).

**Syntax**

The syntax of the method is:

[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)

1. public final void setPriority(int newPriority)  

## Thread Priority Constants

The Thread class defines three priority constants:

[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)

1. public static int MIN_PRIORITY   // value = 1  
2. public static int NORM_PRIORITY  // value = 5  
3. public static int MAX_PRIORITY   // value = 10  

Here:

- The default priority of a thread is **5 (NORM_PRIORITY)**
- Minimum priority is **1**
- Maximum priority is **10**

## Example: Priority of a Thread

The following example demonstrates how to get and set the priority of threads using the getPriority() and setPriority() methods.

[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)

1. // Importing the required classes  
2. import java.lang.*;  

3. public class ThreadPriorityExample extends Thread   
4. {  

5. // Method 1  
6. // Whenever the start() method is called by a thread  
7. // the run() method is invoked  
8. public void run()  
9. {  
10. // the print statement  
11. System.out.println("Inside the run() method");  
12. }  

13. // the main method  
14. public static void main(String argvs[])  
15. {  
16. // Creating threads with the help of ThreadPriorityExample class  
17. ThreadPriorityExample th1 = new ThreadPriorityExample();  
18. ThreadPriorityExample th2 = new ThreadPriorityExample();  
19. ThreadPriorityExample th3 = new ThreadPriorityExample();  

20. // We did not mention the priority of the thread.  
21. // Therefore, the priorities of the thread is 5, the default value  

22. // 1st Thread  
23. // Displaying the priority of the thread  
24. // using the getPriority() method  
25. System.out.println("Priority of the thread th1 is : " + th1.getPriority());  

26. // 2nd Thread   
27. // Display the priority of the thread  
28. System.out.println("Priority of the thread th2 is : " + th2.getPriority());  

29. // 3rd Thread   
30. // // Display the priority of the thread  
31. System.out.println("Priority of the thread th2 is : " + th2.getPriority());  

32. // Setting priorities of above threads by  
33. // passing integer arguments  
34. th1.setPriority(6);  
35. th2.setPriority(3);  
36. th3.setPriority(9);  

37. // 6  
38. System.out.println("Priority of the thread th1 is : " + th1.getPriority());  

39. // 3  
40. System.out.println("Priority of the thread th2 is : " + th2.getPriority());  

41. // 9  
42. System.out.println("Priority of the thread th3 is : " + th3.getPriority());  

43. // Main thread  

44. // Displaying name of the currently executing thread   
45. System.out.println("Currently Executing The Thread : " + Thread.currentThread().getName());  

46. System.out.println("Priority of the main thread is : " + Thread.currentThread().getPriority());  

47. // Priority of the main thread is 10 now  
48. Thread.currentThread().setPriority(10);  

49. System.out.println("Priority of the main thread is : " + Thread.currentThread().getPriority());  
50. }  
51. }  

**Output:**

Priority of the thread th1 is : 5
Priority of the thread th2 is : 5
Priority of the thread th2 is : 5
Priority of the thread th1 is : 6
Priority of the thread th2 is : 3
Priority of the thread th3 is : 9
Currently Executing The Thread : main
Priority of the main thread is : 5
Priority of the main thread is : 10

We know that a thread with high priority will get preference over lower priority threads when it comes to the execution of threads. However, there can be other scenarios where two threads can have the same priority. All of the processing, in order to look after the threads, is done by the Java thread scheduler. Refer to the following example to comprehend what will happen if two threads have the same priority.

## Threads with Same Priority

A thread with a higher priority usually gets preference over lower-priority threads. However, when two or more threads have the same priority, Java does not guarantee which thread will execute first. The decision depends entirely on the thread scheduler algorithm used by the [JVM](https://www.tpointtech.com/jvm-java-virtual-machine) (such as First-Come-First-Serve or Round-Robin).

### Example: Threads Having Same Priority

The following example demonstrates the behavior of threads when multiple threads have the same priority.

[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)

1. // importing the java.lang package  
2. import java.lang.*;  

3. public class ThreadPriorityExample1 extends Thread   
4. {  

5. // Method 1  
6. // Whenever the start() method is called by a thread  
7. // the run() method is invoked  
8. public void run()  
9. {  
10. // the print statement  
11. System.out.println("Inside the run() method");  
12. }  

13. // the main method  
14. public static void main(String argvs[])  
15. {  

16. // Now, priority of the main thread is set to 7  
17. Thread.currentThread().setPriority(7);  

18. // the current thread is retrieved  
19. // using the currentThread() method  

20. // displaying the main thread priority  
21. // using the getPriority() method of the Thread class  
22. System.out.println("Priority of the main thread is : " + Thread.currentThread().getPriority());  

23. // creating a thread by creating an object of the class ThreadPriorityExample1  
24. ThreadPriorityExample1 th1 = new ThreadPriorityExample1();  

25. // th1 thread is the child of the main thread  
26. // therefore, the th1 thread also gets the priority 7  

27. // Displaying the priority of the current thread  
28. System.out.println("Priority of the thread th1 is : " + th1.getPriority());  
29. }  
30. }  

**Output:**

Priority of the main thread is : 7
Priority of the thread th1 is : 7

**Explanation:**

If there are two threads that have the same priority, then one can not predict which thread will get the chance to execute first. The execution then is dependent on the thread scheduler's algorithm (First Come First Serve, Round-Robin, etc.)

## IllegalArgumentException in Thread Priority

If the value passed to the setPriority() method is outside the valid range (1–10), Java throws an IllegalArgumentException.

### Example: IllegalArgumentException

The following example demonstrates how an IllegalArgumentException is thrown when an invalid priority value is assigned to a thread.

[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)[](https://www.tpointtech.com/thread-priority-in-java#)

1. // importing the java.lang package  
2. import java.lang.*;  

3. public class IllegalArgumentException extends Thread   
4. {  

5. // the main method  
6. public static void main(String argvs[])  
7. {  

8. // Now, priority of the main thread is set to 17, which is greater than 10  
9. Thread.currentThread().setPriority(17);  

10. // The current thread is retrieved  
11. // using the currentThread() method  

12. // displaying the main thread priority  
13. // using the getPriority() method of the Thread class  
14. System.out.println("Priority of the main thread is : " + Thread.currentThread().getPriority());  

15. }  
16. }  

When we execute the above program, we get the following exception:

Exception in thread "main" java.lang.IllegalArgumentException
at java.base/java.lang.Thread.setPriority(Thread.java:1141)
at IllegalArgumentException.main(IllegalArgumentException.java:12)