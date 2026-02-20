In the C# programming language, the Main Thread is the entry point thread of the program. When a C# program starts execution, the Main Thread is automatically created by the Common Language Runtime (CLR) and serves as the entry point of the application. It performs the code in the Main() method and begins the execution of the program.

![C# Main Thread](https://images.tpointtech.com/csharp/images/c-sharp-main-thread.png)

In C#, the Main Thread is responsible for managing the execution flow of the entire application. We can access or manage the Main Thread by using Thread.CurrentThread property. It provides information, such as thread ID, name, priority, and other thread-related details.

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-main-thread#)[](https://www.tpointtech.com/c-sharp-main-thread#)[](https://www.tpointtech.com/c-sharp-main-thread#)

1. class Program  
2. {  
3.     static void Main(string[] args) // Main Thread starts here  
4.     {  
5.         Console.WriteLine("Hello from the Main Thread!");  
6.     }  
7. }  

In this syntax,

- **static void Main(string[] args):** It is the main method, which serves as the entry point of the program. It runs on the main thread.
- **args:** These are the command-line arguments, and it is passed to the program. It is the optional parameter.

### Simple C# Main Thread Example:

Let us take an example to illustrate the main thread in C#.

### Example

[](https://www.tpointtech.com/c-sharp-main-thread#)[](https://www.tpointtech.com/c-sharp-main-thread#)[](https://www.tpointtech.com/c-sharp-main-thread#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Thread mt = Thread.CurrentThread;  
8.         mt.Name = "Main Thread";  
9.         Console.WriteLine("The Thread Name: " + mt.Name);  
10.         Console.WriteLine("The Thread ID: " + mt.ManagedThreadId);  
11.         Console.WriteLine("Is Alive: " + mt.IsAlive);  
12.         Console.WriteLine("The Priority: " + mt.Priority);  
13.         Console.WriteLine("The Thread State: " + mt.ThreadState);  
14.         Console.WriteLine("The Main thread is running...");  
15.     }  
16. }  

**Output:**

The Thread Name: Main Thread
The Thread ID: 1
Is Alive: True
The Priority: Normal
The Thread State: Running
The Main thread is running...

**Explanation:**

In this example, we demonstrate how to access and display details of the main thread in C#. We use the Thread.CurrentThread property to get a reference to the currently executing thread. After that, we assign a name to the main thread using mt.Name and then display the details using Console.WriteLine() function.

## Importance of the Main Thread

There are several important points of the main threads in C#. Some of them are as follows:

- In C#, the Main thread is essential because it starts the execution of the program.
- It provides a safe and structured way to initialize the program when it starts running.
- When the Main Thread finishes, all background threads stop automatically, but the foreground threads continue running until they complete their task.
- It allows control over the lifetime and management of child threads created during program execution.

## Accessing the Main Thread in C#

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), the main thread is the first thread that is created automatically when a program starts. We can access it using the Thread.CurrentThread property from the System.Threading namespace.

### C# Example to Access the Main Thread

Let us take an example to illustrate how we can access the main thread in C#.

### Example

[](https://www.tpointtech.com/c-sharp-main-thread#)[](https://www.tpointtech.com/c-sharp-main-thread#)[](https://www.tpointtech.com/c-sharp-main-thread#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         Thread mt = Thread.CurrentThread; // Access main thread  
8.         mt.Name = "Main Thread";  
9.         Console.WriteLine("The Thread Name: " + mt.Name );  
10.         Console.WriteLine("The Thread ID: " + mt.ManagedThreadId );  
11.    }  
12. }  

**Output:**

The Thread Name: Main Thread
The Thread ID: 1

**Explanation:**

In this example, we access the main thread of a C# program using the Thread.CurrentThread property. It returns a reference to the currently executing thread.  After that, we assign a name to the main thread using mt.Name and display its name and unique thread ID using Console.WriteLine() function.

## Main Thread Execution with Child Thread

Let us take an example to illustrate the behaviour of the child class in the Main thread in C#.

### Example

[](https://www.tpointtech.com/c-sharp-main-thread#)[](https://www.tpointtech.com/c-sharp-main-thread#)[](https://www.tpointtech.com/c-sharp-main-thread#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Child()  
6.     {  
7.         Console.WriteLine("The child thread is executing.");  
8.         Thread.Sleep( 1500 );  
9.         Console.WriteLine("The child thread is completed.");  
10.     }  
11.     static void Main()  
12.     {     
13.         Console.WriteLine("The main thread Started.");  
14.         Thread c = new Thread( Child );  
15.         c.Start();  
16.         Console.WriteLine("The Main Thread Ended.");  
17.     }  
18. }  

**Output:**

The main thread Started.
The Main Thread Ended.
The child thread is executing
The child thread is completed.

**Explanation:**

In this example, we demonstrate the use of a child thread alongside the main thread. The program executes with the main thread, which prints the result as "The main thread Started.". After that, we create a child thread and start running the child method. The child thread prints a message and sleeps for 1.5 seconds, and then prints an execution message.

## Deadlocking Using the Main Thread in C#

In the C# programming language, a deadlock is a situation where two or more threads are waiting on each other to release resources, such as resource1 and resource2, at the same time. It can be illustrated by calling the Thread.CurrentThread.Join() function, which causes the main thread to wait for itself to complete, leads to a deadlock.

### C# Deadlock Example using the Main Thread

Let us take an example to illustrate the deadlock using the main thread in C#.

### Example

[](https://www.tpointtech.com/c-sharp-main-thread#)[](https://www.tpointtech.com/c-sharp-main-thread#)[](https://www.tpointtech.com/c-sharp-main-thread#)

1. using System;  
2. using System.Threading;  
3. class Program  
4. {  
5.     static void Main()  
6.     {  
7.         // Accessing   
8.         Thread mt = Thread.CurrentThread;  
9.         mt.Name = "Main Thread";  
10.         Console.WriteLine("The Main thread started...");  
11.         // Deadlock situation  
12.         Console.WriteLine("The Main thread is trying to join itself...");  
13.         mt.Join();  // Deadlock occurs here  
14.         Console.WriteLine("This line will never be executed");  
15.     }  
16. }  

**Output:**

The Main thread started...
The Main thread is trying to join itself...

**Explanation:**

In this example, we demonstrate a deadlock situation using the main thread in C#. First, we access the currently executing thread using the Thread.CurrentThread property and assign it the name "Main Thread". After that, the main thread has started. It attempts to join itself by calling the mt.Join() function. As a result, the program enters a deadlock and prints "This line will never be executed".

## Conclusion:

In conclusion, the C# Main Thread is the entry point thread of the program. It starts the execution in the Main() method and manages the execution flow of the entire application. It can also create and manage other threads and provide a safe way to prepare the program when it starts running.