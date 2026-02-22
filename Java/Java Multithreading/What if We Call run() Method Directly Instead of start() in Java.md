In Java, each [thread](https://www.tpointtech.com/threads-in-java) runs in its own call stack that allows concurrent execution. Normally, we start a thread using the start() method, which creates a new call stack for the thread and executes the run() method independently.

However, if we call the run() method directly, it does not create a new call stack. Instead, the run() method executes in the current thread's call stack, just like a normal method call. This means the code runs sequentially, not concurrently.

## Example 1: Directly Calling run() Method

The following example demonstrates calling run() directly on a thread object:

[](https://www.tpointtech.com/what-if-we-call-java-run-method-directly#)[](https://www.tpointtech.com/what-if-we-call-java-run-method-directly#)[](https://www.tpointtech.com/what-if-we-call-java-run-method-directly#)

1. class TestCallRun1 extends Thread{  
2.  public void run(){  
3.    System.out.println("running...");  
4.  }  
5.  public static void main(String args[]){  
6.   TestCallRun1 t1=new TestCallRun1();  
7.   t1.run();//works, but does not start a separate call stack  
8.  }  
9. }  

**Output:**

running...

> **Note:**The run() method executes in the main thread's call stack, not a separate thread.

## Example 2: Problem with Direct run() Calls on Multiple Threads

If multiple thread objects call run() directly, there is no context-switching between threads - they are treated as normal objects, consider the following example:

[](https://www.tpointtech.com/what-if-we-call-java-run-method-directly#)[](https://www.tpointtech.com/what-if-we-call-java-run-method-directly#)[](https://www.tpointtech.com/what-if-we-call-java-run-method-directly#)

1. class TestCallRun2 extends Thread{  
2.  public void run(){  
3.   for(int i=1;i<5;i++){  
4.     try{Thread.sleep(500);}catch(InterruptedException e){System.out.println(e);}  
5.     System.out.println(i);  
6.   }  
7.  }  
8.  public static void main(String args[]){  
9.   TestCallRun2 t1=new TestCallRun2();  
10.   TestCallRun2 t2=new TestCallRun2();  

11.   t1.run();  
12.   t2.run();  
13.  }  
14. }  

**Output:**

1
2
3
4
1
2
3
4

As we can see in the above program that there is no context-switching because here t1 and t2 will be treated as normal object not thread object.

**Observation:** Both threads run one after another in the main thread, not concurrently. There is no context-switching, because calling run() directly does not start a thread object.

## Summary

- Use start() to create a new thread and execute run() concurrently.
- Calling run() directly executes the method in the current thread, behaving like a normal method call.
- Directly calling run() on multiple threads does not provide multithreading, and threads execute sequentially.