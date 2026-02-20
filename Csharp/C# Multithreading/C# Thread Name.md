In the C# programming language, a thread is a lightweight process that is used to run tasks independently. Every thread has a default name, like Thread-1, Thread-2, etc. [C#](https://www.tpointtech.com/c-sharp-tutorial) allows us to assign a custom and meaningful name to a thread. The naming thread makes it easier to identify the thread during program execution, debugging, monitoring, and logging. It improves the readability and simplifies troubleshooting in multi-threaded applications.

![C# Thread Name](https://images.tpointtech.com/cpp/images/c-sharp-thread-name.png)

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)

1. Thread thread = new Thread(MethodName);  
2. thread.Name = "ThreadName";  
3. thread.Start();  

In this syntax,

- **Thread thread:** It is used to create a new object of thread.
- **new Thread (MethodName):** It specifies the method that the thread will execute.
- **Name:** It is used to assign a custom name to the thread.
- **Start():** It is the method that starts the execution of the thread.

### Simple C# Thread Name Example

Let's take an illustrative example to demonstrate the thread name in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Thread t = new Thread(Dis);  
8.         t.Name = "EmployeeThread";  
9.         t.Start();  
10.         Console.WriteLine("The Main Thread Name is " + Thread.CurrentThread.Name );  
11.     }  
12.     static void Dis()  
13.     {  
14.         // Printing current thread name  
15.         Console.WriteLine("The Child Thread Name is " + Thread.CurrentThread.Name );  
16.     }  
17. }  

**Output:**

The Main Thread Name is
The Child Thread Name is EmployeeThread

**Explanation:**

In the above example, we demonstrate the use of a thread name in C#. Inside the main thread, we create a new thread t, and the name is set to EmployeeThread. When the thread starts, the program runs the Dis() method to print the name of the current thread. At the same time, the main thread prints its own name. Therefore, the main thread does not define a custom name. It displays an empty value.

## Multiple Threads with different Names

Let us take an illustrative example to demonstrate the use of multiple threads in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Thread t1 = new Thread( Job );  
8.         t1.Name = "DownloadThread";  
9.         Thread t2 = new Thread (Job);  
10.         t2.Name = "UploadThread";  
11.         t1.Start();  
12.         t2.Start();  
13.     }  
14.     static void Job()  
15.     {  
16.         Console.WriteLine("Executing: " + Thread.CurrentThread.Name );  
17.     }  
18. }  

**Output:**

Executing: UploadThread
Executing: DownloadThread

**Explanation:**

In the above example, we create two threads, t1 and t2, and assign them the names DownloadThread and UploadThread using the Name property. When we start both threads, they run in the same method job(). After that, it prints the name of the running thread because the thread runs independently. The order of thread execution is not fixed. Finally, we use the Console.WriteLine() method to print the output.

## Using Thread Name to Perform Different Tasks

Let us take an illustrative example to perform multiple tasks using threads in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Thread t1 = new Thread( Task1 );  
8.         t1.Name = "CalculationThread";  
9.         Thread t2 = new Thread(Task2);  
10.         t2.Name = "MessageThread";  
11.         Thread t3 = new Thread(Task3);  
12.         t3.Name = "PrintingThread";  
13.         t1.Start();  
14.         t2.Start();  
15.         t3.Start();  
16.     }  
17.     static void Task1()  
18.     {  
19.         Console.WriteLine( Thread.CurrentThread.Name + ": To perform calculations");  
20.     }  
21.     static void Task2()  
22.     {  
23.         Console.WriteLine( Thread.CurrentThread.Name + ": To display messages ");  
24.     }  
25.     static void Task3()  
26.     {  
27.         Console.WriteLine( Thread.CurrentThread.Name + ": To printing reports... " );  
28.     }  
29. }  

**Output:**

CalculationThread: To perform calculations
MessageThread: To display messages
PrintingThread: To printing reports...

**Explanation:**

In the above example, we demonstrate the use of multiple threads in C#. The first thread, CalculationThread, is responsible for performing calculations, the second thread, MessageThread, handles the displaying of messages, and the third thread, PrintingThread, is used to print reports. When the thread starts using the Start() method, all three threads are executing concurrently. Finally, we use the Console.WriteLine() method to print the output.

## Why do we use Thread Name?

There are several aspects that determine the importance of the thread Name in C#. Some of them are as follows.

- **Easy Identification:** In C#, we use the thread name to easily identify a thread during program execution, debugging, and logging. A meaningful thread name helps the developer to understand the purpose and behaviour of the thread, especially when multiple threads are running simultaneously.
- **Debugging:** In C#, the thread name helps to debug easily. It identifies the thread that is executing the task. It is easy to analyse the behaviour of threads. It is easy to find issues like deadlocks, blocked threads, and troubleshoot issues in multithreaded applications.
- **Improve Code Readability:** In C#, the thread name helps to improve the readability of code. It can understand the purpose of each thread.

## Conclusion

In conclusion, a thread in C# is a lightweight process that is used to run tasks independently. Every thread has a default name, like Thread-1, Thread-2, etc. It enables us to assign a custom name to a thread. The meaningful thread name helps to make debugging, monitoring, and logging much easier.# C# Thread Name

Last Updated : 20 Jan 2026

In the C# programming language, a thread is a lightweight process that is used to run tasks independently. Every thread has a default name, like Thread-1, Thread-2, etc. [C#](https://www.tpointtech.com/c-sharp-tutorial) allows us to assign a custom and meaningful name to a thread. The naming thread makes it easier to identify the thread during program execution, debugging, monitoring, and logging. It improves the readability and simplifies troubleshooting in multi-threaded applications.

![C# Thread Name](https://images.tpointtech.com/cpp/images/c-sharp-thread-name.png)

### Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)

1. Thread thread = new Thread(MethodName);  
2. thread.Name = "ThreadName";  
3. thread.Start();  

In this syntax,

- **Thread thread:** It is used to create a new object of thread.
- **new Thread (MethodName):** It specifies the method that the thread will execute.
- **Name:** It is used to assign a custom name to the thread.
- **Start():** It is the method that starts the execution of the thread.

### Simple C# Thread Name Example

Let's take an illustrative example to demonstrate the thread name in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Thread t = new Thread(Dis);  
8.         t.Name = "EmployeeThread";  
9.         t.Start();  
10.         Console.WriteLine("The Main Thread Name is " + Thread.CurrentThread.Name );  
11.     }  
12.     static void Dis()  
13.     {  
14.         // Printing current thread name  
15.         Console.WriteLine("The Child Thread Name is " + Thread.CurrentThread.Name );  
16.     }  
17. }  

**Output:**

The Main Thread Name is
The Child Thread Name is EmployeeThread

**Explanation:**

In the above example, we demonstrate the use of a thread name in C#. Inside the main thread, we create a new thread t, and the name is set to EmployeeThread. When the thread starts, the program runs the Dis() method to print the name of the current thread. At the same time, the main thread prints its own name. Therefore, the main thread does not define a custom name. It displays an empty value.

## Multiple Threads with different Names

Let us take an illustrative example to demonstrate the use of multiple threads in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Thread t1 = new Thread( Job );  
8.         t1.Name = "DownloadThread";  
9.         Thread t2 = new Thread (Job);  
10.         t2.Name = "UploadThread";  
11.         t1.Start();  
12.         t2.Start();  
13.     }  
14.     static void Job()  
15.     {  
16.         Console.WriteLine("Executing: " + Thread.CurrentThread.Name );  
17.     }  
18. }  

**Output:**

Executing: UploadThread
Executing: DownloadThread

**Explanation:**

In the above example, we create two threads, t1 and t2, and assign them the names DownloadThread and UploadThread using the Name property. When we start both threads, they run in the same method job(). After that, it prints the name of the running thread because the thread runs independently. The order of thread execution is not fixed. Finally, we use the Console.WriteLine() method to print the output.

## Using Thread Name to Perform Different Tasks

Let us take an illustrative example to perform multiple tasks using threads in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)[](https://www.tpointtech.com/c-sharp-thread-name#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Thread t1 = new Thread( Task1 );  
8.         t1.Name = "CalculationThread";  
9.         Thread t2 = new Thread(Task2);  
10.         t2.Name = "MessageThread";  
11.         Thread t3 = new Thread(Task3);  
12.         t3.Name = "PrintingThread";  
13.         t1.Start();  
14.         t2.Start();  
15.         t3.Start();  
16.     }  
17.     static void Task1()  
18.     {  
19.         Console.WriteLine( Thread.CurrentThread.Name + ": To perform calculations");  
20.     }  
21.     static void Task2()  
22.     {  
23.         Console.WriteLine( Thread.CurrentThread.Name + ": To display messages ");  
24.     }  
25.     static void Task3()  
26.     {  
27.         Console.WriteLine( Thread.CurrentThread.Name + ": To printing reports... " );  
28.     }  
29. }  

**Output:**

CalculationThread: To perform calculations
MessageThread: To display messages
PrintingThread: To printing reports...

**Explanation:**

In the above example, we demonstrate the use of multiple threads in C#. The first thread, CalculationThread, is responsible for performing calculations, the second thread, MessageThread, handles the displaying of messages, and the third thread, PrintingThread, is used to print reports. When the thread starts using the Start() method, all three threads are executing concurrently. Finally, we use the Console.WriteLine() method to print the output.

## Why do we use Thread Name?

There are several aspects that determine the importance of the thread Name in C#. Some of them are as follows.

- **Easy Identification:** In C#, we use the thread name to easily identify a thread during program execution, debugging, and logging. A meaningful thread name helps the developer to understand the purpose and behaviour of the thread, especially when multiple threads are running simultaneously.
- **Debugging:** In C#, the thread name helps to debug easily. It identifies the thread that is executing the task. It is easy to analyse the behaviour of threads. It is easy to find issues like deadlocks, blocked threads, and troubleshoot issues in multithreaded applications.
- **Improve Code Readability:** In C#, the thread name helps to improve the readability of code. It can understand the purpose of each thread.

## Conclusion

In conclusion, a thread in C# is a lightweight process that is used to run tasks independently. Every thread has a default name, like Thread-1, Thread-2, etc. It enables us to assign a custom name to a thread. The meaningful thread name helps to make debugging, monitoring, and logging much easier.