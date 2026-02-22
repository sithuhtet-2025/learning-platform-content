A Java Shutdown Hook is a special thread that allows developers to execute cleanup code just before the Java Virtual Machine (JVM) shuts down.

In this chapter, you will learn what a shutdown hook is, why it is needed, how to register and remove a shutdown hook, and how it helps in safely releasing resources when the JVM terminates.

## JVM Shutdown Hook in Java

A Java Shutdown Hook is a special feature that allows developers to run some code just before the [Java Virtual Machine (JVM)](https://www.tpointtech.com/jvm-java-virtual-machine) shuts down. It is mainly used to perform cleanup tasks when the program is about to end.

In normal situations, it is difficult to run code when the JVM stops due to external reasons such as system shutdown, kill signals, or lack of memory. The shutdown hook solves this problem by giving developers a way to register a thread that will execute automatically when the JVM is shutting down.

A shutdown hook is implemented using a [Thread](https://www.tpointtech.com/jvm-java-virtual-machine). The code that needs to run during shutdown is written inside the run() method of that thread. This thread is then registered with the JVM using the [Runtime class](https://www.tpointtech.com/java-runtime-class).

## When does the JVM shut down?

The Java Virtual Machine (JVM) shuts down in the following situations:

- When the user presses **Ctrl + C** in the command prompt
- When the System.exit(int) method is called
- When the user logs off from the system
- When the system is shut down or restarted

## Shutdown Hook Methods

The following methods are used to register, remove, and manage shutdown hooks:

### 1. addShutdownHook(Thread hook) Method

This method of the Runtime class is used to **register a shutdown hook** with the JVM. The registered thread runs automatically when the JVM is shutting down.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)

1. public void addShutdownHook(Thread hook){}  

### 2. getRuntime() Method

This method is a **factory method** of the Runtime class that returns the runtime instance of the Java application. It is required to access shutdown hook methods.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)

1. Runtime r = Runtime.getRuntime();  

### 3. removeShutdownHook(Thread hook) Method

This method is used to **remove an already registered shutdown hook** from the JVM.

**Syntax:**

Here is the syntax:

[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)

1. public boolean removeShutdownHook(Thread hook){ }    

- Returns true if the shutdown hook is removed successfully
- Returns false if the shutdown hook could not be removed

### 4. Factory Method

A **factory method** is a method that returns an instance of a class. In Java, Runtime.getRuntime() is an example of a factory method.

## Shutdown Hook Using a Separate Thread Class

In this approach, a shutdown hook is created by defining a separate class that extends the Thread class. The cleanup code is written inside the run() method, making this method suitable when the shutdown logic is larger or needs to be reused.

### Example

The following example demonstrates a Shutdown Hook using a separate Thread class:

[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)

1. class MyThread extends Thread {  
2.     public void run() {  
3.         System.out.println("shut down hook task completed..");  
4.     }  
5. }  

6. public class TestShutdown1 {  
7.     public static void main(String[] args) {  

8.         Runtime r = Runtime.getRuntime();  
9.         r.addShutdownHook(new MyThread());  

10.         System.out.println("Now main sleeping... press ctrl+c to exit");  
11.         try { Thread.sleep(3000); } catch (Exception e) {}  
12.     }  
13. }  

**Output:**

Now main sleeping... press ctrl+c to exit
shut down hook task completed..

## Shutdown Hook Using Anonymous Class

A shutdown hook can also be created using an **anonymous class**. This approach is useful when the shutdown task is small and does not require a separate thread class. The code to be executed during JVM shutdown is written directly inside the run() method of the anonymous thread.

### Example

The following example demonstrates a Shutdown Hook using an anonymous class.

[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)

1. public class TestShutdown2{  
2. public static void main(String[] args)throws Exception {  

3. Runtime r=Runtime.getRuntime();  

4. r.addShutdownHook(new Thread(){  
5. public void run(){  
6.     System.out.println("shut down hook task completed..");  
7.     }  
8. }  
9. );  

10. System.out.println("Now main sleeping... press ctrl+c to exit");  
11. try{Thread.sleep(3000);}catch (Exception e) {}  
12. }  
13. }  

**Output:**

Now main sleeping... press ctrl+c to exit
shut down hook task completed..

### Example: Removing a Registered Shutdown Hook

This example demonstrates how to remove a shutdown hook using the removeShutdownHook() method.

[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)[](https://www.tpointtech.com/shutdownhook-thread#)

1. public class RemoveHookExample   
2. {  

3. // the Msg class is derived from the Thread class  
4. static class Msg extends Thread   
5. {  

6. public void run()   
7. {  
8. System.out.println("Bye ...");  
9. }  
10. }  

11. // main method  
12. public static void main(String[] argvs)   
13. {  
14. try   
15. {  
16. // creating an object of the class Msg  
17. Msg ms = new Msg();  

18. // registering the Msg object as the shutdown hook  
19. Runtime.getRuntime().addShutdownHook(ms);  

20. // printing the current state of program  
21. System.out.println("The program is beginning ...");  

22. // causing the thread to sleep for 2 seconds  
23. System.out.println("Waiting for 2 seconds ...");  
24. Thread.sleep(2000);  

25. // removing the hook  
26. Runtime.getRuntime().removeShutdownHook(ms);  

27. // printing the message program is terminating   
28. System.out.println("The program is terminating ...");  
29. }   
30. catch (Exception ex)   
31. {  
32. ex.printStackTrace();  
33. }  
34. }  
35. }  

**Output:**

The program is beginning ...
Waiting for 2 seconds ...
The program is terminating ...