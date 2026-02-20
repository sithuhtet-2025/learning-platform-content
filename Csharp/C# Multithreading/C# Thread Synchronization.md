In the C# programming language, thread synchronization is a mechanism that is commonly utilized in multithreaded programming to manage multiple threads accessing shared resources. It helps to ensure data integrity and avoid race conditions in multithreading programs.

In a [multithreading](https://www.tpointtech.com/c-sharp-multithreading) program, threads are allowed to access any resource for the required execution time. Threads share resources and execute asynchronously. However, accessing shared resources (data) is a critical task that sometimes can lead to unexpected results. In order to avoid these types of issues, thread synchronization techniques are commonly utilized to control how the threads interact with the shared resources.

![C# Thread Synchronization](https://images.tpointtech.com/csharp/images/c-sharp-thread-synchronization.png)

If multiple threads access and modify shared data simultaneously, some issues can arise, such as race conditions. A race condition occurs when multiple threads attempt to modify the same variable at the same time, which can lead to incorrect or unexpected results.

## Syntax:

It has the following syntax.

[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)

1. synchronizationObject.Wait();   // Request / Wait for the lock  
2. // Critical section (shared resource code)  
3. synchronizationObject.Release(); // Release the lock  

In the given syntax,

- **Wait():** It is the method that is used to request access to the shared resources.
- **Critical Section:** It is the portion that contains the code that accesses the shared resources, such as variables, lists, files, etc.
- **Release():** This method is used to release the lock after the thread completes its work in the critical section.

## C# Thread Synchronization Example

Here, we are going to take an illustrative example to demonstrate the thread synchronization in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static int c = 0;  
6.     static object s = new object();  
7.     static void Inc()  
8.     {  
9.         for ( int i = 0; i < 1000; i++ )  
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
25.         Console.WriteLine("The final counter value is " + c );  
26.     }  
27. }  

**Output:**

The final counter value is 2000

### Explanation:

In the given example, we have taken two threads, m1 and m2, and both threads execute the Inc() method at the same time, which increments a shared counter variable c by 1, a thousand times each. After that, we use a lock on the object s to ensure that only one thread can change the value at a time. After the completion of both [thread](https://www.tpointtech.com/c-sharp-thread-class) executions, the final counter value 2000 is displayed on the screen.

## Thread Synchronization Using a Lock

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), the lock keyword is a widely used method for thread synchronization. It is commonly utilized to avoid multiple threads from accessing shared resources at the same time. When multiple thread tries to read or modify the same data simultaneously, several issues can arise, such as a race condition, which can lead to incorrect or undefined results. The lock statement helps to ensure that only one thread can execute it at a time.

### C# Thread Synchronization Example using Lock

Now, we are going to take an illustrative example to define the thread synchronization using a lock in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {     
5.     static int c = 0;  
6.     static object lockObj = new object ();  
7.     static void Incrementer()  
8.     {  
9.         for (int i = 1; i <= 5; i++)  
10.         {  
11.             lock  (lockObj)  // Lock to protect shared resource  
12.             {  
13.                 c++;  
14.             Console.WriteLine(Thread.CurrentThread.Name + " -> Counter: " + c);  
15.             }  
16.             Thread.Sleep(200);   
17.         }  
18.     }  
19.     static void Main()  
20.     {  
21.         Thread t1 = new Thread(Incrementer);  
22.         Thread t2 = new Thread(Incrementer);  
23.         t1.Name = "Thread 1";  
24.         t2.Name = "Thread 2";  
25.         t1.Start();  
26.         t2.Start();  
27.         t1.Join();  
28.         t2.Join();  
29.         Console.WriteLine("\nFinal Counter Value: " + c);  
30.     }  
31. }  

**Output:**

Thread 1 -> Counter: 1
Thread 2 -> Counter: 2
Thread 1 -> Counter: 3
Thread 2 -> Counter: 4
Thread 1 -> Counter: 5
Thread 2 -> Counter: 6
Thread 1 -> Counter: 7
Thread 2 -> Counter: 8
Thread 1 -> Counter: 9
Thread 2 -> Counter: 10

Final Counter Value: 10

### Explanation:

In the above example, we have taken two threads, Thread1 and Thread2, and executed the Incrementer() method, where both threads try to update the shared counter variable c. After that, we use the lock(lockObj) statement to ensure that only one thread can execute at a time in the critical section where the counter is incremented and printed. Every thread increments the counter five times, which shows in a final value of 10. Finally, we use the Console.WriteLine() method to print the output.

## C# Thread Synchronization Using Monitor Class

In the C# programming language, the Monitor class provides a more flexible way of synchronizing threads. It is commonly utilized to control access to shared resources by multiple threads, which ensures that we can execute only one thread in the critical section of the program at a time. It works similarly to a lock keyword, but it also provides extra features, such as Wait(), Pulse(), and PulseAll() for better control.

### C# Thread Synchronization Example Using Monitor Class

Let us take a simple example to demonstrate the use of the Monitor class for synchronizing threads in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static int c = 0;  
6.     static object lockObj = new object();  
7.     static void Incrementer()  
8.     {  
9.         for (int i = 1; i <= 5; i++)  
10.         {  
11.             Monitor.Enter(lockObj);   // Begin synchronization  
12.             try  
13.             {  
14.                 c++;  
15.                 Console.WriteLine(Thread.CurrentThread.Name + " -> Counter: " + c);  
16.             }  
17.             finally  
18.             {  
19.                 Monitor.Exit(lockObj); // Release lock  
20.             }  
21.             Thread.Sleep(200);  
22.         }  
23.     }  
24.     static void Main()  
25.     {  
26.         Thread t1 = new Thread(Incrementer);  
27.         Thread t2 = new Thread(Incrementer);  
28.         t1.Name = "The Thread 1";  
29.         t2.Name = "The Thread 2";  
30.         t1.Start();  
31.         t2.Start();  
32.         t1.Join();  
33.         t2.Join();  
34.         Console.WriteLine("\nThe final counter value is " + c);  
35.     }  
36. }  

**Output:**

The Thread 1 -> Counter: 1
The Thread 2 -> Counter: 2
The Thread 1 -> Counter: 3
The Thread 2 -> Counter: 4
The Thread 1 -> Counter: 5
The Thread 2 -> Counter: 6
The Thread 1 -> Counter: 7
The Thread 2 -> Counter: 8
The Thread 1 -> Counter: 9
The Thread 2 -> Counter: 10

The final counter value is 10

### Explanation:

In the above example, we use the Monitor.Enter() and Monitor.Exit() method to ensure that only one thread updates the counter at a time. Here, the two threads execute the incrementer() method at the same time. After that, the Monitor.Enter() method locks the shared object. After the update, we use the Monitor.Exit() method to release the lock. Finally, we use the Console.WriteLine() method to print the output.

## Using Mutex in Synchronized threads in C#

In the C# programming language, a Mutex is used to control the access of threads, even when threads belong to different programs. A lock works only inside one application, but a mutex can synchronize threads across multiple applications.

### C# Thread Synchronization Example Using Mutex

Let us take an illustrative example to demonstrate a mutex in thread synchronization in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static Mutex mutex = new Mutex();  
6.     static int count = 0;  
7.     static void Inc()  
8.     {  
9.         mutex.WaitOne();  
10.         count++;  
11.         Console.WriteLine( Thread.CurrentThread.Name + " -> " + count );  
12.         mutex.ReleaseMutex();  
13.     }  
14.     static void Main()  
15.     {  
16.         Thread t1 = new Thread(Inc);  
17.         Thread t2 = new Thread(Inc);  
18.         t1.Name = "The Thread 1";  
19.         t2.Name = "The Thread 2";  
20.         t1.Start();  
21.         t2.Start();  
22.     }  
23. }  

**Output:**

The Thread 1 -> 1
The Thread 2 -> 2

### Explanation:

In the above example, we have created the mutex object and the integer variable count. When a thread calls the mutex.WaitOne(), it acquires the mutex and enters the critical section, which ensures that only one thread can update the count at a time. The other threads must wait until the mutex is released. After completing the operation, the thread calls the mutex.ReleaseMutex() function to unlock the mutex. Finally, we use the Console.WriteLine() method to print the output.

## Using a Semaphore in Thread Synchronization

In the C# programming language, a semaphore is used to manage access to shared resources among multiple threads. It allows a specified number of threads to enter the critical section at the same time.

### C# Thread Synchronization Example using Semaphore:

Here, we are going to take an illustrative example to demonstrate the Semaphore in Synchronization in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static Semaphore sm = new Semaphore(2, 2);  
6.     static void Work()  
7.     {  
8.         Console.WriteLine( Thread.CurrentThread.Name + " is waiting... " );  
9.         sm.WaitOne ();  
10.         Console.WriteLine( Thread.CurrentThread.Name + " entered the critical section. " );  
11.         Thread.Sleep( 1000 );  
12.         Console.WriteLine( Thread.CurrentThread.Name + " is leaving the critical section. " );  
13.         sm.Release();  
14.     }  
15.     static void Main()  
16.     {  
17.         for ( int i = 1; i <= 5; i++ )  
18.         {  
19.             Thread t = new Thread ( Work );  
20.             t.Name = " Thread " + i;  
21.             t.Start();  
22.         }  
23.     }  
24. }  

**Output:**

Thread 2 is waiting...
Thread 3 is waiting...
Thread 5 is waiting...
Thread 1 is waiting...
Thread 4 is waiting...
Thread 1 entered the critical section.
Thread 2 entered the critical section.
Thread 1 is leaving the critical section.
Thread 2 is leaving the critical section.
Thread 5 entered the critical section.
Thread 4 entered the critical section.
Thread 5 is leaving the critical section.
Thread 4 is leaving the critical section.
Thread 3 entered the critical section.
Thread 3 is leaving the critical section.

### Explanation:

In the above example, we create the Semaphore with 2 slots, which means only two threads can be allowed inside the critical section at the same time. When each thread starts execution, it first prints that it is waiting. After that, we use the sm.WaitOne() method to get a slot in the semaphore. If a slot is free, the thread enters the critical section. If no slot is free, the thread waits until a slot becomes available. We call the sm.Release() method to release the thread. Finally, we use the Console.WriteLine() method to print the output.

## Using a SemaphoreSlim in Thread Synchronization

In the C# programming language, a SemaphoreSlim is a lightweight synchronization construct that is designed for in-process thread synchronization. It offers better performance compared to a Semaphore. It is especially used for asynchronous code.

### C# Thread Synchronization Example using a SemaphoreSlim

Here, we are going to take an illustrative example to demonstrate the SemaphoreSlim in synchronization in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)[](https://www.tpointtech.com/c-sharp-thread-synchronization#)

1. using System;  
2. using System.Threading;  
3. class Tpoint  
4. {  
5.     static SemaphoreSlim sm = new SemaphoreSlim (2);  
6.     static void Work()  
7.     {  
8.         Console.WriteLine(Thread.CurrentThread.Name + " is waiting... ");  
9.         sm.Wait();  
10.         Console.WriteLine(Thread.CurrentThread.Name + " entered. ");  
11.         Thread.Sleep( 1000 );  
12.         Console.WriteLine(Thread.CurrentThread.Name + " is leaving. ");  
13.         sm.Release();  
14.     }  
15.     static void Main()  
16.     {  
17.         for (int i = 1; i <= 5; i++)  
18.         {  
19.             Thread t = new Thread(Work);  
20.             t.Name = "The Thread " + i;  
21.             t.Start();  
22.         }  
23.     }  
24. }  

**Output:**

The Thread 3 is waiting...
The Thread 1 is waiting...
The Thread 3 entered.
The Thread 5 is waiting...
The Thread 5 entered.
The Thread 2 is waiting...
The Thread 4 is waiting...
The Thread 3 is leaving.
The Thread 5 is leaving.
The Thread 2 entered.
The Thread 1 entered.
The Thread 2 is leaving.
The Thread 4 entered.

The Thread 1 is leaving.
The Thread 4 is leaving.

### Explanation:

In the above example, a SemaphoreSlim allows only two threads to enter the critical section at a time. When each thread starts, it first prints that it is waiting. After that, we use the Wait() method to get the slot. If the two threads are already executed, the other threads wait outside until someone leaves the thread. When a thread gets permission, it prints that it has entered. After a thread leaves, we call the Release() method to release the thread.

## Conclusion

In conclusion, thread synchronization is an essential part of ensuring safe and predictable execution for managing the multiple threads accessing shared resources. It prevents a conflict and avoids an error. It helps the program to execute smoothly when many threads are running at the same time.