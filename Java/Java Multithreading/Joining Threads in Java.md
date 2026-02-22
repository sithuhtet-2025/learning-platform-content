In [Java multithreading](https://www.tpointtech.com/multithreading-in-java), threads often depend on the results of other threads. Java provides a simple way to handle such dependencies using the **join() method**. The join() method allows one thread to pause its execution until another thread has completed.

In this chapter, you will understand what the join() method is, why it is used, and how its different overloaded forms work in Java.

## What is join() Method in Java?

The **join()** method is provided by the **java.lang.Thread** class. It allows the current executing thread to wait until the [thread](https://www.tpointtech.com/threads-in-java) on which join() is called finishes its execution.

In simple terms: One thread waits for another thread to complete before moving forward.

## How join() Method Works?

- Suppose **_th_** is a thread object that is currently executing.
- When **th.join()** is called, the calling thread enters the waiting state. (Read More: [Different Thread States](https://www.tpointtech.com/thread-states-in-java))
- The calling thread resumes execution only after **_th_** has completed its execution (reaches the dead state).

## Why Use join() Method?

The join() method is mainly used when:

- A task must complete before another task starts
- Thread execution order matters
- You want to avoid race conditions caused by parallel execution

## Overloaded join() Methods

Java provides three overloaded versions of the join() method. These allow threads to wait either indefinitely or for a specific amount of time.

### 1. join()

When join() is invoked without parameters, the current thread stops execution and enters the waiting state. It remains there until the target thread completes its execution.

If the waiting thread is interrupted, an InterruptedException is thrown.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)

1. public final void join() throws InterruptedException  

### 2. join(long mls)

This version of the join () method allows the current thread to wait for a specified time (in milliseconds). The waiting ends when:

- The target thread finishes execution, or
- The specified time period expires

Just like [sleep()](https://www.tpointtech.com/thread-states-in-java), the actual waiting time depends on the operating system, so exact timing is not guaranteed.

**Syntax**

It has the following syntax:

[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)

1. public final synchronized void join(long millis) throws InterruptedException  

Here, millis represents time in milliseconds.

### 3. join(long mls, int nanos)

This version of join() method allows even more precise waiting by specifying:

- Milliseconds
- Nanoseconds (additional)

The current thread waits until:

- The target thread completes, or
- The total waiting time (millis + nanos) expires

Again, timing accuracy depends on the operating system.

**Syntax:**

It has the following syntax:

[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)

1. public final synchronized void join(long millis, int nanos) throws InterruptedException  

Here, millis is milliseconds and nanos is additional nanoseconds.

## Example of Joining Threads

The following example demonstrates how the join() method is used to make the main thread wait until a child thread completes its execution.

[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)

1. // A Java program for understanding   
2. // the joining of threads  

3. // import statement  
4. import java.io.*;  

5. // The ThreadJoin class is the child class of the class Thread  
6. class ThreadJoin extends Thread  
7. {  
8. // overriding the run method  
9. public void run()  
10. {  
11. for (int j = 0; j < 2; j++)  
12. {  
13. try  
14. {  
15. // sleeping the thread for 300 milli seconds  
16. Thread.sleep(300);  
17. System.out.println("The current thread name is: " + Thread.currentThread().getName());  
18. }  
19. // catch block for catching the raised exception  
20. catch(Exception e)  
21. {  
22. System.out.println("The exception has been caught: " + e);  
23. }  
24. System.out.println( j );  
25. }  
26. }  
27. }  

28. public class ThreadJoinExample  
29. {  
30. // main method  
31. public static void main (String argvs[])  
32. {  

33. // creating 3 threads  
34. ThreadJoin th1 = new ThreadJoin();  
35. ThreadJoin th2 = new ThreadJoin();  
36. ThreadJoin th3 = new ThreadJoin();  

37. // thread th1 starts  
38. th1.start();  

39. // starting the second thread after when  
40. // the first thread th1 has ended or died.  
41. try  
42. {  
43. System.out.println("The current thread name is: "+ Thread.currentThread().getName());  

44. // invoking the join() method  
45. th1.join();  
46. }  

47. // catch block for catching the raised exception  
48. catch(Exception e)  
49. {  
50. System.out.println("The exception has been caught " + e);  
51. }  

52. // thread th2 starts  
53. th2.start();  

54. // starting the th3 thread after when the thread th2 has ended or died.  
55. try  
56. {  
57. System.out.println("The current thread name is: " + Thread.currentThread().getName());  
58. th2.join();  
59. }  

60. // catch block for catching the raised exception  
61. catch(Exception e)  
62. {  
63. System.out.println("The exception has been caught " + e);  
64. }  

65. // thread th3 starts  
66. th3.start();  
67. }  
68. }  

**Output:**

The current thread name is: main
The current thread name is: Thread - 0
0
The current thread name is: Thread - 0
1
The current thread name is: main
The current thread name is: Thread - 1
0
The current thread name is: Thread - 1
1
The current thread name is: Thread - 2
0
The current thread name is: Thread - 2
1

**Explanation:**

The above program shows that the second thread th2 begins after the first thread th1 has ended, and the thread th3 starts its work after the second thread th2 has ended or died.

## The join() Method and InterruptedException

As discussed earlier, when a thread waiting using the join() method is interrupted, Java throws an InterruptedException. This happens when another thread interrupts the currently waiting thread.

### Example

The following example demonstrates using join() method with InterruptedException:

[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)

1. class ABC extends Thread  
2. {  
3. Thread threadToInterrupt;  
4. // overriding the run() method  
5. public void run()  
6. {  
7. // invoking the method interrupt  
8. threadToInterrupt.interrupt();  
9. }  
10. }  

11. public class ThreadJoinExample1  
12. {  
13. // main method  
14. public static void main(String[] argvs)  
15. {  
16. try  
17. {  
18. // creating an object of the class ABC  
19. ABC th1 = new ABC();  

20. th1.threadToInterrupt = Thread.currentThread();  
21. th1.start();  

22. // invoking the join() method leads   
23. // to the generation of InterruptedException  
24. th1.join();  
25. }  
26. catch (InterruptedException ex)  
27. {  
28. System.out.println("The exception has been caught. " + ex);  
29. }  
30. }  
31. }  

**Output:**

The exception has been caught. java.lang.InterruptedException

## More Examples of the join() Method

Let us now see some additional examples to understand how join() affects thread execution order.

### Example: join() Method without Time Limit

The following example demonstrates how the join() method without any time limit makes one thread wait until another thread completes its execution.

[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)

1. class TestJoinMethod1 extends Thread{    
2.  public void run(){    
3.   for(int i=1;i<=5;i++){    
4.    try{    
5.     Thread.sleep(500);    
6.    }catch(Exception e){System.out.println(e);}    
7.   System.out.println(i);    
8.   }    
9.  }    
10. public static void main(String args[]){    
11.  TestJoinMethod1 t1=new TestJoinMethod1();    
12.  TestJoinMethod1 t2=new TestJoinMethod1();    
13.  TestJoinMethod1 t3=new TestJoinMethod1();    
14.  t1.start();    
15.  try{    
16.   t1.join();    
17.  }catch(Exception e){System.out.println(e);}    

18.  t2.start();    
19.  t3.start();    
20.  }    
21. }    

**Output:**

1
2
3
4
5
1
1
2
2
3
3
4
4
5
5

Here, t1 completes its execution first. Only after t1 finishes do t2 and t3 start executing.

### Example: join(long milliseconds) Method

The following example demonstrates how the join(long milliseconds) method allows a thread to wait for a specified time period.

[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)[](https://www.tpointtech.com/join-thread-in-java#)

1. class TestJoinMethod2 extends Thread{    
2.  public void run(){    
3.   for(int i=1;i<=5;i++){    
4.    try{    
5.     Thread.sleep(500);    
6.    }catch(Exception e){System.out.println(e);}    
7.   System.out.println(i);    
8.   }    
9.  }    
10. public static void main(String args[]){    
11.  TestJoinMethod2 t1=new TestJoinMethod2();    
12.  TestJoinMethod2 t2=new TestJoinMethod2();    
13.  TestJoinMethod2 t3=new TestJoinMethod2();    
14.  t1.start();    
15.  try{    
16.   t1.join(1500);    
17.  }catch(Exception e){System.out.println(e);}    

18.  t2.start();    
19.  t3.start();    
20.  }    
21. }    

**Output:**

1
2
3
1
4
1
2
5
2
3
3
4
4
5
5

In this case, t1 is allowed to execute for 1500 milliseconds (approximately 3 iterations). After that time expires, t2 and t3 begin execution even though t1 has not yet finished.