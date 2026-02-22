Multitasking in Java allows multiple threads to run simultaneously and perform tasks in parallel. Using [multithreading](https://www.tpointtech.com/multithreading-in-java), a Java program can execute single or multiple tasks efficiently by sharing CPU time among threads.

In this chapter, you will learn how to perform:

- A single task using multiple threads
- Multiple tasks using multiple threads
- Coordination between threads using synchronization

## Performing a Single Task by Multiple Threads

If you want multiple [threads](https://www.tpointtech.com/threads-in-java) to perform the same task, you need only one **run()** method. Each thread executes the same logic independently but runs in a separate call stack.

### Example: Single Task Using Multiple Threads (Extending Thread)

The following example demonstrates how a single task can be executed by multiple threads by extending the [Thread class](https://www.tpointtech.com/java-thread).

[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)

1. class TestMultitasking1 extends Thread{  
2.  public void run(){  
3.    System.out.println("task one");  
4.  }  
5.  public static void main(String args[]){  
6.   TestMultitasking1 t1=new TestMultitasking1();  
7.   TestMultitasking1 t2=new TestMultitasking1();  
8.   TestMultitasking1 t3=new TestMultitasking1();  

9.   t1.start();  
10.   t2.start();  
11.   t3.start();  
12.  }  
13. }  

**Output:**

task one
task one
task one

### Example: Single Task Using Multiple Threads (Implementing Runnable)

The following example demonstrates how a single task can be executed by multiple threads by implementing the [Runnable interface](https://www.tpointtech.com/runnable-interface-in-java).

[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)

1. class TestMultitasking2 implements Runnable{  
2. public void run(){  
3. System.out.println("task one");  
4. }  

5. public static void main(String args[]){  
6. Thread t1 =new Thread(new TestMultitasking2());//passing annonymous object of TestMultitasking2 class  
7. Thread t2 =new Thread(new TestMultitasking2());  

8. t1.start();  
9. t2.start();  

10.  }  
11. }  

**Output:**

task one
task one

## Performing Multiple Tasks by Multiple Threads

If you want different threads to perform different tasks, you must define multiple run() methods - one for each task.

### Example: Two Tasks Using Two Threads

The following example demonstrates how two different tasks can be executed simultaneously using two separate threads.

[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)

1. class Simple1 extends Thread{  
2.  public void run(){  
3.    System.out.println("task one");  
4.  }  
5. }  

6. class Simple2 extends Thread{  
7.  public void run(){  
8.    System.out.println("task two");  
9.  }  
10. }  

11.  class TestMultitasking3{  
12.  public static void main(String args[]){  
13.   Simple1 t1=new Simple1();  
14.   Simple2 t2=new Simple2();  

15.   t1.start();  
16.   t2.start();  
17.  }  
18. }  

**Output:**

task one
task two

### Example: Using Anonymous Class Extending Thread

The following example demonstrates how multiple tasks can be executed using anonymous classes that extend the Thread class.

[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)

1. class TestMultitasking4{  
2.  public static void main(String args[]){  
3.   Thread t1=new Thread(){  
4.     public void run(){  
5.       System.out.println("task one");  
6.     }  
7.   };  
8.   Thread t2=new Thread(){  
9.     public void run(){  
10.       System.out.println("task two");  
11.     }  
12.   };  

13.   t1.start();  
14.   t2.start();  
15.  }  
16. }  

**Output:**

task one
task two

### Example: Using Anonymous Class Implementing Runnable

The following example demonstrates how multiple tasks can be executed using anonymous classes that implement the Runnable interface.

[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)

1. class TestMultitasking5{  
2.  public static void main(String args[]){  
3.   Runnable r1=new Runnable(){  
4.     public void run(){  
5.       System.out.println("task one");  
6.     }  
7.   };  

8.   Runnable r2=new Runnable(){  
9.     public void run(){  
10.       System.out.println("task two");  
11.     }  
12.   };  

13.   Thread t1=new Thread(r1);  
14.   Thread t2=new Thread(r2);  

15.   t1.start();  
16.   t2.start();  
17.  }  
18. }  

**Output:**

task one
task two

## Coordination Between Threads Using Synchronization

Coordination between threads using synchronization is required when multiple threads share common data and must execute in a specific order. In Java, [synchronization](https://www.tpointtech.com/synchronization-in-java) allows only one thread to access a critical section at a time, while methods like **wait()** and **notify()** help threads communicate with each other.

### Example

This example demonstrates thread coordination using the synchronized block along with wait() and notify() methods to print odd and even numbers alternately.

[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)[](https://www.tpointtech.com/multitasking-in-multithreading#)

1. public class OddEvenExample {  
2.     int contr = 1;  
3.     static int NUM;  

4.     public void displayOddNumber() {  
5.         synchronized (this) {  
6.             while (contr < NUM) {  
7.                 while (contr % 2 == 0) {  
8.                     try { wait(); } catch (InterruptedException e) {}  
9.                 }  
10.                 System.out.print(contr + " ");  
11.                 contr++;  
12.                 notify();  
13.             }  
14.         }  
15.     }  

16.     public void displayEvenNumber() {  
17.         synchronized (this) {  
18.             while (contr < NUM) {  
19.                 while (contr % 2 == 1) {  
20.                     try { wait(); } catch (InterruptedException e) {}  
21.                 }  
22.                 System.out.print(contr + " ");  
23.                 contr++;  
24.                 notify();  
25.             }  
26.         }  
27.     }  

28.     public static void main(String[] args) {  
29.         NUM = 20;  
30.         OddEvenExample oe = new OddEvenExample();  

31.         Thread t1 = new Thread(() -> oe.displayEvenNumber());  
32.         Thread t2 = new Thread(() -> oe.displayOddNumber());  

33.         t1.start();  
34.         t2.start();  
35.     }  
36. }  

**Output:**

1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20