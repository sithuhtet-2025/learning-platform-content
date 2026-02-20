In the C# programming language, multithreading is a technique that enables a program to perform several operations at the same time. It is commonly used to enhance application speed, responsiveness, and resource efficiency. A thread is a lightweight process that represents a separate path of execution in a program. It makes an application run more efficiently and helps avoid wasting CPU time.

![C# Multithreading](https://images.tpointtech.com/csharp/images/c-sharp-multithreading.png)

C# programming language supports multi-threading using the System.Threading namespace provides easier tools like the Task Parallel Library (TPL) and the async and await keywords.

## What is a Thread in C#?

In the C# programming language, a thread is the smallest unit of execution in a program. It represents a separate path of execution. It allows multiple tasks to execute at the same time, which improves performance by making better use of the CPU. Every C# program begins with a main thread, which is automatically created by the .NET runtime. We can also create extra threads to run other tasks at the same time as the main method.

## Thread Life Cycle

In C#, a thread's life cycle begins when we create an object of the System.Threading.Thread class and ends when the thread finishes its work or is stopped. A thread changes when it passes through different stages during its runtime. These are the several stages in a thread's life cycle. These are as follows:

![C# Multithreading](https://images.tpointtech.com/csharp/images/c-sharp-multithreading2.png)

Here, we will discuss these stages of the Thread's life cycle one by one.

### 1) Unstarted State

In the C# programming language, the unstarted state is a state when the instance of the thread is created, but the Start() method has not yet been called. At this point, the thread has not started running.

**Example:**

[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)

1. Thread t = new Thread(MyMethod);  // unstarted state  

### 2) Ready State

It is the situation when the thread is ready to execute and is waiting for the CPU to assign time for execution.

**Example:**

[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)

1. t.Start(); // Thread is now Ready  

### 3) Not Runnable State

A thread enters this state when it cannot run temporarily. It can occur when the thread is put to sleep using the Sleep() function, is waiting for another thread using the Wait() function, or is blocked while performing I/O operations.

### 4) Dead State

In the C# programming language, the thread enters this state when it has finished executing its task or has been aborted. Once a thread is in this state, it cannot be restarted with the Start() function, and a new thread object must be created to run the code again.

## Creating a thread in C#

There are a few steps for creating a thread in C#. These are as follows.

### Step 1: Import the Required Namespace

In the C# programming language, if we want to use threading, we need to include the System.Threading namespace.

[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)

1. using System.Threading;  

### Step 2: Define the Method

In this step, we create a method that we want the thread to execute. This method must contain a void return type and take no parameters if directly passed to a ThreadStart delegate.

**Example:**

[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)

1. void MyMethod()  
2. {  
3.     Console.WriteLine("Thread is running...");  
4. }  

### Step 3: Create and Start the Thread

Now, we create a thread object and pass the method name to it, and then we call the Start() method to begin execution.

**Example:**

[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)

1. Thread t = new Thread(MyMethod); // Create thread  
2. t.Start();  // Start thread  

## C# Multithreading Example:

Let us take an example to illustrate multithreading in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     // Method to be executed by the child thread  
6.     static void Print()  
7.     {  
8.         for (int m = 1; m <= 5; m++)  
9.         {  
10.             Console.WriteLine("Child Thread: " + m);  
11.             Thread.Sleep(500);  // Pause for 500 milliseconds  
12.         }  
13.     }  
14.     static void Main()  
15.     {  
16.         // Create and start a new thread  
17.         Thread t = new Thread(Print);  
18.         t.Start();  
19.         // Main thread also does some work  
20.         for (int m = 1; m <= 5; m++)  
21.         {  
22.             Console.WriteLine("Main Thread: " + m);  
23.             Thread.Sleep(500);  
24.         }  
25.     }  
26. }  

**Output:**

Child Thread: 1
Main Thread: 1
Child Thread: 2
Main Thread: 2
Child Thread: 3
Main Thread: 3
Child Thread: 4
Main Thread: 4
Child Thread: 5
Main Thread: 5

**Explanation:**

In this example, we have taken a class Tpoint that contains a static method Print() which prints numbers from 1 to 5, and pauses for 500 ms between each print to allow some task. Inside the main() method, we create an instance t of the class Tpoint and call the start() method to display the result.

## Async and Await (High-level Multithreading)

In the C# programming language, async and await are programming constructs that are commonly utilized to handle asynchronous operations. It allows running the tasks concurrently, especially I/O bounds tasks, including file access, database calls, or API requests without blocking the main execution thread.

### C# High-level Multithreading Example

Let's take an instance to demonstrate the high-level multithreading using async/await functions in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)

1. using System;  
2. using System.Threading.Tasks;  
3. class Tpoint  
4. {  
5.     static async Task Do(string name)  
6.     {  
7.         for (int m = 1; m <= 5; m++)  
8.         {  
9.          Console.WriteLine(name + " - Step " + m);  
10.             await Task.Delay(500); // delay  
11.         }  
12.     }  
13.     static async Task Main(string[] args)  
14.     {  
15.         // Start two asynchronous tasks  
16.         Task t1 = Do("First task");  
17.         Task t2 = Do("Second task");  
18.         await Task.WhenAll(t1, t2);  
19.         Console.WriteLine("Both tasks completed.");  
20.     }  
21. }  

**Output:**

First task - Step 1
Second task - Step 1
First task - Step 2
Second task - Step 2
First task - Step 3
Second task - Step 3
First task - Step 4
Second task - Step 4
First task - Step 5
Second task - Step 5
Both tasks completed.

**Explanation:**

In this example, we have taken two tasks that run concurrently, each executing the Do() method with a 500 ms delay per step. After that, the await Task.WhenAll() function waits for both tasks to complete before printing the final message.

## Thread Synchronization

In C#, thread synchronization is a mechanism that is commonly utilized in multithreaded programming to manage multiple threads accessing shared resources. It ensures data integrity and avoids race conditions in multithreading programs.

If multiple threads access and modify shared data simultaneously, some issues can arise, such as race conditions. It occurs when multiple threads attempt to modify the same variable at the same time, which can cause incorrect or unexpected results.

### C# Thread Synchronization Example:

Let us take an example to illustrate the thread synchronization in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {     
5.     static int c = 0;  
6.     static object s = new object();  
7.     static void Inc()  
8.     {  
9.         for (int i = 0; i < 1000; i++)  
10.         {  
11.             lock (s) // Synchronization occurs  
12.             {  
13.                 c++;  
14.             }  
15.         }  
16.     }  
17.     static void Main()  
18.     {  
19.         Thread m1 = new Thread(Inc);  
20.         Thread m2 = new Thread(Inc);  
21.         m1.Start();  
22.         m2.Start();  
23.         m1.Join();  
24.         m2.Join();  
25.         Console.WriteLine("The final counter value is " + c);  
26.     }  
27. }  

**Output:**

The final counter value is 2000

**Explanation:**

In this example, we have taken two threads, m1 and m2, and executed the Inc() method at the same time, which increments a shared counter variable c by 1, a thousand times each. After that, we use a lock on the object s to ensure only one thread can change the value at a time. The final result is 2000, which shows that locking keeps shared data safe when using multiple threads.

## Using ParameterizedThreadStart with Lambda Expressions

In C#, the ParameterizedThreadStart with lambda expressions is a way to create and start threads that accept a parameter using inline lambda syntax. This combination simplifies the structure of the code while still allowing data to be passed into the thread function.

### C# Multithreading Example Using Lambda Expression

Let us take an example to illustrate multithreading using a lambda expression in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static void Main()  
6.     {  
7.         string msg = "Welcome to Tpoint Tech";  
8.         // Using ParameterizedThreadStart with a lambda expression  
9.         Thread t = new Thread(param => {  
10.             Console.WriteLine("Message: " + param);  
11.         });  
12.         t.Start(msg); // Pass parameter to thread  
13.     }  
14. }   

**Output:**

Message: Welcome to Tpoint Tech

**Explanation:**

In this example, we demonstrate the use of a Lambda expression with ParameterizedThreadStart to create a thread and pass a parameter. We pass a string msg to the thread using t.Start(msg), and the thread prints it. After that, we use the lambda expression to keep the code short and simple and print the output.

## Deadlocks in C#

In the C# programming language, a deadlock occurs when two or more threads are waiting on each other to release resources, such as resource1 and resource2, at the same time.

![C# Multithreading](https://images.tpointtech.com/csharp/images/c-sharp-multithreading3.png)

For example, if thread A locks resource1 and waits for resource2, while at the same time Thread B locks resource2 and waits for resource1, both threads become blocked because each is waiting for the other to unlock a resource.

### C# Deadlocks Example

Let us take an example to illustrate the deadlocks in C#.

### Example

[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)[](https://www.tpointtech.com/c-sharp-multithreading#)

1. using System;  
2. using System.Threading;  
3. class TpointDeadlock  
4. {  
5.     static object s1 = new object();  
6.     static object s2 = new object();  
7.     static void Point1()  
8.     {  
9.         lock (s1)  
10.         {  
11.             Console.WriteLine("Thread 1 acquired lock1");  
12.             Thread.Sleep(100);  
13.             lock (s2)  
14.             {  
15.                 Console.WriteLine("Thread 1 acquired lock2");  
16.             }  
17.         }  
18.     }  
19.     static void Point2()  
20.     {  
21.         lock (s2)  
22.         {  
23.             Console.WriteLine("Thread 2 acquired lock2");  
24.             Thread.Sleep(100);   
25.             lock (s1)   
26.             {  
27.                 Console.WriteLine("Thread 2 acquired lock1");  
28.             }  
29.         }  
30.     }  
31.     static void Main()  
32.     {  
33.         Thread m1 = new Thread(Point1);  
34.         Thread m2 = new Thread(Point2);  
35.         m1.Start();  
36.         m2.Start();  
37.         m1.Join();  
38.         m2.Join();  
39.     }  
40. }  

**Output:**

Thread 2 acquired lock2
Thread 1 acquired lock1

**Explanation:**

In this example, we define the two objects, s1 and s2, which are used to lock. After that, Thread 1 locks s1 first and then waits for s2, while Thread 2 locks s2 first and then waits for s1. Since each thread is holding one lock and waiting for the other, they block each other, and the program stops after printing the first lock message.

## Advantages of Multithreading in C#

There are several advantages of multithreading in C#. Some of them are as follows:

**1) Improved Performance**

Multithreading allows multiple tasks to run at the same time, which helps the program work faster and more efficiently. It takes advantage of multiple CPU cores, which makes better use of the computer's processing power.

**2) Improved Responsiveness**

The main part of the program stays responsive even if other tasks are busy in the background. It means the user can click buttons or scroll without the app freezing. It makes the application faster and smoother.

**3) Scalability**

Multithreading enhances the scalability of applications by allowing them to handle more tasks. It splits the work into smaller parts and executes them at the same time. So, the program does not slow down.

**4) Better Resource Usage**

Multithreading helps the computer stay busy instead of wasting time, and makes the program run more efficiently. When one thread is waiting, the other thread can keep working. It allows the program to make full use of the CPU and complete the task faster.

## Disadvantages of Multithreading in C#

There are several disadvantages of C#. Some of them are as follows.

**1) Complexity in Programming**

Multithreaded applications are complex to design, write, understand, and maintain than single-threaded ones, which are simpler because they run one task at a time without needing coordination between threads.

**2) Debugging Challenges**

It is much harder to replicate an error in a multithreaded or multi-contexted application than in a single-threaded application.

**3) Difficulty of testing**

A multithreaded application is more difficult to test than a single-threaded application because multiple threads can run at the same time. It makes it hard to predict all possible interactions and uncover hidden bugs.

**4) Difficulty of Managing Concurrency**

The task of managing concurrency among threads is more difficult. Managing multiple threads at the same time is challenging and creates new problems in the applications.

## Conclusion

In conclusion, C# multithreading is a huge concept with various method that enables the execution of multiple operations concurrently within a single application. It is commonly used to enhance application speed, responsiveness, and resource efficiency. It makes an application execute more efficiently and helps avoid wasting CPU time.