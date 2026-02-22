In Java, each thread has a unique name that helps in identifying it during execution. Java also provides the currentThread() method to access the currently executing thread. In this chapter, we will learn how to name threads and work with the current thread in Java.

## Naming Thread

The [Thread class](https://www.tpointtech.com/java-thread) provides methods to change and get the name of a thread. By default, each [thread](https://www.tpointtech.com/java-thread) has a name, i.e. thread-0, thread-1 and so on. By we can change the name of the thread by using the setName() method.

### Syntax

The syntax of setName() and getName() methods are given below:

[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)

1. public String getName(): is used to return the name of a thread.  
2. public void setName(String name): is used to change the name of a thread.  

We can also set the name of a thread directly when we create a new thread using the constructor of the class.

### Example of naming a thread : Using setName() Method

The following example demonstrates how to assign a custom name to a thread using the setName() method.

[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)

1. class TestMultiNaming1 extends Thread{  
2.   public void run(){  
3.    System.out.println("running...");  
4.   }  
5.  public static void main(String args[]){  
6.   TestMultiNaming1 t1=new TestMultiNaming1();  
7.   TestMultiNaming1 t2=new TestMultiNaming1();  
8.   System.out.println("Name of t1:"+t1.getName());  
9.   System.out.println("Name of t2:"+t2.getName());  

10.   t1.start();  
11.   t2.start();  

12.   t1.setName("Sonoo Jaiswal");  
13.   System.out.println("After changing name of t1:"+t1.getName());  
14.  }  
15. }  

**Output:**

Name of t1:Thread-0
Name of t2:Thread-1
After changing name of t1:Sonoo Jaiswal
running...
running...

### Example of naming a thread : Without Using setName() Method

You can also set the name of a thread at the time of the creation of a thread, without using the setName() method.

The following example demonstrates how a thread is automatically assigned a default name when the setName() method is not used.

[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)

1. // A Java program that shows how one can   
2. // set the name of a thread at the time  
3. // of creation of the thread  

4. // import statement  
5. import java.io.*;  

6. // The ThreadNameClass is the child class of the class Thread  
7. class ThreadName extends Thread  
8. {  

9. // constructor of the class  
10. ThreadName(String threadName)  
11. {  
12. // invoking the constructor of  
13. // the superclass, which is Thread class.  
14. super(threadName);  
15. }  

16. // overriding the method run()  
17. public void run()  
18. {  
19. System.out.println(" The thread is executing....");  
20. }  
21. }  

22. public class ThreadNamingExample  
23. {  
24. // main method  
25. public static void main (String argvs[])  
26. {  
27. // creating two threads and settting their name  
28. // using the contructor of the class  
29. ThreadName th1 = new ThreadName("JavaTpoint1");  
30. ThreadName th2 = new ThreadName("JavaTpoint2");  

31. // invoking the getName() method to get the names  
32. // of the thread created above  
33. System.out.println("Thread - 1: " + th1.getName());  
34. System.out.println("Thread - 2: " + th2.getName());  

35. // invoking the start() method on both the threads  
36. th1.start();  
37. th2.start();  
38. }  
39. }  

**Output:**

Thread - 1: JavaTpoint1
Thread - 2: JavaTpoint2
The thread is executing....
The thread is executing....

## Current Thread

The currentThread() method returns a reference to the currently executing thread and it is commonly used to obtain the thread's name, priority, and state.

### Syntax

The following is the syntax to get the current thread i.e., currentThread() method:

[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)

1. public static Thread currentThread()    

### Example of currentThread() method

The following example demonstrates how the currentThread() method is used to obtain information about the currently executing thread.

[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)[](https://www.tpointtech.com/java-naming-thread-and-current-thread#)

1. class TestMultiNaming2 extends Thread{  
2.  public void run(){  
3.   System.out.println(Thread.currentThread().getName());  
4.  }  
5.  public static void main(String args[]){  
6.   TestMultiNaming2 t1=new TestMultiNaming2();  
7.   TestMultiNaming2 t2=new TestMultiNaming2();  

8.   t1.start();  
9.   t2.start();  
10.  }  
11. }  

**Output:**

Thread-0
Thread-1