In the C# programming language, a thread is the smallest unit of execution in a program. It represents a separate path of execution. It allows multiple tasks to run at the same time. It helps to improve performance by making better use of the CPU. Every C# program begins with a main thread, which is automatically created by the .NET runtime. We can also create extra threads to run other tasks at the same time as the main method.

In C#, the Thread class is defined in the System.Threading namespace. It is commonly used to create and manage threads.

![C# Thread class](https://images.tpointtech.com/csharp/images/c-sharp-thread-class.png)

**Syntax:**

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-thread-class#)[](https://www.tpointtech.com/c-sharp-thread-class#)[](https://www.tpointtech.com/c-sharp-thread-class#)

1. Thread t = new Thread (new ThreadStart(MethodName));  
2. t.Start();  

When we are using a lambda expression.

[](https://www.tpointtech.com/c-sharp-thread-class#)[](https://www.tpointtech.com/c-sharp-thread-class#)[](https://www.tpointtech.com/c-sharp-thread-class#)

1. Thread t = new Thread(() => {  
2.     // thread code here  
3. });  
4. t.Start();  

In this syntax,

- **ThreadStart:** It is a delegate that points to a method that will run inside the new thread.
- **MethodName:** It defines the name of the method that we want to execute.

### C# Thread Class Example

Let us take an example to illustrate the thread class in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-class#)[](https://www.tpointtech.com/c-sharp-thread-class#)[](https://www.tpointtech.com/c-sharp-thread-class#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Num()  
6.     {  
7.         for (int m = 1; m <= 3; m++)  
8.         {  
9.             Console.WriteLine("Thread " + Thread.CurrentThread.Name + ": " + m);  
10.             Thread.Sleep(500); // Pause for 0.5 seconds  
11.         }  
12.     }  
13.     static void Main()  
14.     {  
15.         Thread m1 = new Thread(Num);  
16.         m1.Name = "Worker";  
17.         m1.Start();    // Start the thread  
18.         m1.Join();     // Wait until m1 finishes  
19.         Console.WriteLine("Thread finished. Main thread exiting.");  
20.     }  
21. }  

**Output:**

Thread Worker: 1
Thread Worker: 2
Thread Worker: 3
Thread finished. Main thread exiting.

**Explanation:**

In this example, we have created a thread to execute a method named Num(). The Num() method prints the numbers from 1 to 3, which takes a short pause after each iteration. In the main function, we create an instance m1 and call the Start() method, and then call m1.Join() method ensures the main thread waits until the worker thread completes its execution before printing the final message.

### Key Features of the C# Thread Class

There are several features of the Thread class in C#. Some main features are as follows:

- It is defined in the System.Threading namespace.
- It defines a single thread of execution.
- A thread may be created using a delegate. It can be either with a method reference or a lambda expression.
- A thread in C# supports foreground and background modes.
- It offers several properties, including Priority, Name, IsAlive, and methods like Abort(), Start(), Sleep(), and Join().

## Properties and Methods of the Thread Class

Here is a list of the most commonly utilized properties of the thread class in C#. These are as follows:

|Property|Description|
|---|---|
|**IsAlive**|It returns true if the thread is still running; otherwise, it returns false.|
|**CurrentContext**|It gets the current context in which the thread is running.|
|**CurrentCulture**|It is commonly utilized to get or set for the current thread.|
|**CurrentPrinciple**|The Thread.CurrentPrincipal property gets or sets the security principal for the current method.|
|**CurrentThread**|The Thread.CurrentThread property gets the reference to the currently executing thread.|
|**CurrentUICulture**|The Thread.CurrentUICulture property is used to get or set the current UI culture, which uses the resource manager to look up culture-specific resources at runtime.|
|**ThreadState**|The Thread.ThreadState property is utilized to get a value that shows the current state of the thread.|
|**Priority**|The Thread.Priority property is commonly utilized to get or set a value that indicates the scheduling priority of the thread.|
|**IsThreadPoolThread**|The Thread.ThreadPoolThread property is used to read a property that specifies whether a thread belongs to the .Net thread pool.|
|**IsBackground**|The Thread.IsBackground property is commonly utilized to get or set a value that specifies whether a thread is a background thread.|
|**ManagedThreadId**|The Thread.ManagedThreadId property is used to get a unique identifier for the current managed thread.|
|**Name**|The Thread.Name property is commonly utilized to get or set the thread name.|
|**ExecutionContext**|The Thread.ExecutionContext is used to get an ExecutionContext object that holds information about the different contexts associated with the current thread.|

### C# Thread Class Property Example

Let us take an example to illustrate the properties of threads in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-class#)[](https://www.tpointtech.com/c-sharp-thread-class#)[](https://www.tpointtech.com/c-sharp-thread-class#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {     
5.     static void TechTask()  
6.     {  
7.         for (int i = 1; i <= 3; i++)  
8.         {  
9.             Console.WriteLine("Executing Thread " + Thread.CurrentThread.Name + ": Step " + i);  
10.             Thread.Sleep(500);  
11.         }  
12.     }  
13.     static void Main()  
14.     {  
15.         Thread m1 = new Thread(TechTask);  
16.         m1.Name = "WorkerThread";  
17.         m1.Priority = ThreadPriority.Highest;   
18.         m1.IsBackground = true;    
19.         Console.WriteLine("Thread Details - Name: " + m1.Name +   
20.                           ", Priority: " + m1.Priority +   
21.                           ", Background: " + m1.IsBackground);  
22.         m1.Start();  
23.         m1.Join();  
24.         Console.WriteLine("Is the thread still running? " + m1.IsAlive);  
25.     }  
26. }  

**Output:**

Thread Details - Name: WorkerThread, Priority: Highest, Background: True
Executing Thread WorkerThread: Step 1
Executing Thread WorkerThread: Step 2
Executing Thread WorkerThread: Step 3
Is the thread still running? False

**Explanation:**

In this example, we demonstrate how to create and manage a thread using the C# Thread class. First, we create a worker thread (m1) to run the TechTask method, which gives a name, the highest priority, and sets it as a background thread. After that, the Start() method starts execution, and then calls the Join() function that makes the main thread wait until the worker thread finishes. Finally, the IsAlive checks whether the thread is still running.

## Thread Class Methods

The following table shows the methods of the Thread class in C#.

|Method|Description|
|---|---|
|**Abort()**|It is used to terminate the thread. It raises ThreadAbortException.|
|**Interrupt()**|It is used to interrupt a thread that is in the _WaitSleepJoin_ state.|
|**Join()**|It is used to block all the calling threads until this thread terminates.|
|**ResetAbort()**|It is used to cancel the Abort request for the current thread.|
|**Resume()**|It is used to resume the suspended thread. It is obsolete.|
|**Sleep(Int32)**|It is used to suspend the current thread for the specified milliseconds.|
|**Start()**|It changes the current state of the thread to Runnable.|
|**Suspend()**|It suspends the current thread if it is not suspended. It is obsolete.|
|**Yield()**|It is used to yield the execution of the current thread to another thread.|

### C# Thread Methods Example using Thread Start, Sleep, and Join

Let us take an example to illustrate the Thread Start(), Sleep(), and Join() methods in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-class#)[](https://www.tpointtech.com/c-sharp-thread-class#)[](https://www.tpointtech.com/c-sharp-thread-class#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Number()  
6.     {  
7.         for (int m = 1; m <= 5; m++)  
8.         {  
9.             Console.WriteLine("Thread: Printing number " + m);  
10.             Thread.Sleep(500);   
11.         }  
12.     }  
13.     static void Main()  
14.     {  
15.         // Create an instance of thread  
16.         Thread m1 = new Thread(Number);  
17.         Console.WriteLine("Main thread starting m1...");  
18.         m1.Start(); // Start the thread  
19.         // Wait for m1 to finish  
20.         m1.Join();  
21.         Console.WriteLine("m1 has completed \nThe main threads ends here.");  
22.     }  
23. }  

**Output:**

Main thread starting m1...
Thread: Printing number 1
Thread: Printing number 2
Thread: Printing number 3
Thread: Printing number 4
Thread: Printing number 5
m1 has completed
The main threads ends here.

**Explanation:**

In this example, we have created a thread to run the Number() method, which prints numbers from 1 to 5 with a short delay. In the main function, we create an instance m1 and call the Start() method, and then call m1.Join() method ensures the main thread waits until the worker thread completes its execution before printing the final message.

## Thread Class Constructor in C#

In C#, the Thread class constructor provides four constructors as follows.

**1) Thread(ThreadStart start)**

It is the constructor of the Thread class in C#. It initializes a new thread that will execute a method. It is specified by a ThreadStart delegate that signifies the methods to be invoked on the new thread.

**2) Thread(ParameterizedThreadStart start)**

The Thread(ParameterizedThreadStart start) in C# initializes a new instance of the Thread class. It specifies a delegate that enables an object to be passed to the thread when it starts execution.

**start:** It is a delegate that shows the method to be executed when the thread starts executing. If the start parameter is null, it throws an ArgumentNullException.

**3) Thread(ThreadStart start, int maxStackSize)**

In C#, the Thread(ThreadStart start, int maxStackSize) initializes a new instance of the Thread class. It defines the maximum stack size for the thread.

**start:** It is a ThreadStart delegate that shows the methods to be executed when the thread starts.

**maxStackSize:** It defines the maximum stack size for the thread. We have to use 0 to apply the default maximum stack size defined in the header for the executable.

**4) Thread(ParameterizedThreadStart start, int maxStackSize)**

This constructor initializes the thread class. It allows us to delegate, which enables an object to be passed to the thread using a ParameterizedThreadStart delegate. It defines the maximum stack size for the thread.

## Advantages of the Thread Class in C#

There are several advantages of the thread class in C#. Some of them are as follows:

- It is used to keep UI responsive for applications while background tasks are running.
- It has better CPU utilization while developing applications.
- It enables parallel execution that helps to perform multiple tasks at the same time.
- It helps to improve the application performance.

## Disadvantages of the Thread Class in C#

There are several disadvantages of the Thread Class in C#. Some main disadvantages are as follows:

- It is very complex to handle.
- It has some synchronization issues, such as race conditions and deadlocks.
- It uses higher memory that contains several threads.

## Conclusion

In conclusion, the C# Thread class is an essential class to run multiple tasks at the same time. It enables us to create, start, pause, resume, and stop threads. It helps to improve performance by making better use of the CPU. It has several property and methods that handles multiple operations.