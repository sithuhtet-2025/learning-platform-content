In the C# programming language, a Thread's life cycle starts when a thread object is created and ends when the thread completes its work or is stopped. A thread passes via multiple states during its lifetime. These different states are very helpful for multithreaded programming. It helps to manage the thread execution and avoid common issues such as deadlocks, race conditions, or unnecessary CPU usage. Several main stages in a thread's life cycle are as follows:

![C# Thread Life Cycle](https://images.tpointtech.com/csharp/images/c-sharp-thread-life-cycle.png)

- Unstarted State
- Runnable State
- Running State
- WaitSleepJoin (Not Runnable State)
- Dead State

Here, we will discuss the thread life cycle states in C# one by one.

### 1) Unstarted State

In the [C# programming language](https://www.tpointtech.com/c-sharp-tutorial), when we create a thread using a Thread class, it is in the Unstarted state. It means the thread objects exist, but it has not yet begun execution. If we want to execute it, we need to call the Start() method. Once we call the Start() method on the thread object, it exits the unstarted state and moves to the next state. The unstarted state may also be known as the new state.

**Syntax:**

Here, the syntax of the unstarted state.

[](https://www.tpointtech.com/c-sharp-thread-life-cycle#)[](https://www.tpointtech.com/c-sharp-thread-life-cycle#)[](https://www.tpointtech.com/c-sharp-thread-life-cycle#)

1. Thread t = new Thread(MyMethod);  // unstarted state  

When we write the Thread t = new(MyMethod); in C#, a new thread object is created that runs the method named MyMethod(). In this situation, the thread is in the unstarted state. It means it exists in memory but has not begun executing any code. In this state, the thread is not considered alive.

### 2) Runnable State

In the C# programming language, the runnable state is a state when the thread is ready for execution but waiting for the CPU to assign time for execution. In this state, the thread has been started but is not yet executing.

**Syntax:**

Here, the syntax of the runnable state.

[](https://www.tpointtech.com/c-sharp-thread-life-cycle#)[](https://www.tpointtech.com/c-sharp-thread-life-cycle#)[](https://www.tpointtech.com/c-sharp-thread-life-cycle#)

1. t.Start(); // Thread is now Ready  

When we call t.Start(); on a thread in C#, the thread changes from the unstarted state to the runnable or ready-to-run state. At this moment, the thread is ready to execute, but waiting for the scheduler to select it to run. The Start() method represents that the thread is ready to execute its assigned method, and then its ThreadState is moved to the next state accordingly.

### 3) Running State

In this state, a thread will move into the running state when the Start() method is invoked on the thread object. At this point, the thread scheduler selects the thread to execute the code. While in the running state, the thread executes its assigned code. The running state is essential when the thread is actively performing its task.

### 4) WaitSleepJoin State (Not Runnable State)

In this situation, a thread will move into the Not Running State. It means a thread cannot currently run, even though it has been started. It doesn't mean the thread is dead. It is simply waiting for some condition or resource. The thread is ready to execute, but the thread scheduler has not yet selected it to execute. It can happen when:

- The Sleep() method is called.
- The thread is waiting for another thread using Wait().
- The thread is blocked due to input/output (I/O) operations.

### 5) Dead State

When the thread finishes its task, the thread enters a dead state or abort state. It means that the execution of the thread is complete. It is the last state of the thread life cycle. In this situation, the thread reaches this state when it has finished executing its task or has been aborted.

### C# Example to understand Thread Life Cycle States

Let us take an example to illustrate the Thread Life Cycle in C#.

### Example

[](https://www.tpointtech.com/c-sharp-thread-life-cycle#)[](https://www.tpointtech.com/c-sharp-thread-life-cycle#)[](https://www.tpointtech.com/c-sharp-thread-life-cycle#)

1. using System;  
2. using System.Threading;  
3. namespace TpointThreadState  
4. {  
5.     class tech  
6.     {  
7.         static void Main( string[] args )  
8.         {  
9.             // Unstarted state  
10.             Thread th1 = new Thread(Do);  
11. Console.WriteLine(" Thread not started yet -> Alive? " + th1.IsAlive + ", Current Thread State: " + th1.ThreadState );  

12.   // Running state  
13.             th1.Start();  
14.             Thread.Sleep(100);  
15. Console.WriteLine(" After starting thread: IsAlive = " + th1.IsAlive + ", State = " + th1.ThreadState );  
16.             // WaitSleepJoin state  
17.             Thread.Sleep(1500);  
18. Console.WriteLine(" While sleeping: IsAlive = " + th1.IsAlive + ", State = " + th1.ThreadState );  
19.             // Stopped state  
20.             th1.Join();  
21. Console.WriteLine(" After finishing: IsAlive = " + th1.IsAlive + ", State = " + th1.ThreadState );  
22.             Console.ReadKey();  
23.         }  
24.         static void Do()  
25.         {  
26. Console.WriteLine(" Thread execution in progress... ");  
27.             Thread.Sleep(1000); // Thread goes into WaitSleepJoin state  
28.             Console.WriteLine(" Thread finished work. ");  
29.         }  
30.     }  
31. }  

**Output:**

Thread not started yet -> Alive? False, Current Thread State: Unstarted
Thread execution in progress...
After starting thread: IsAlive = True, State = WaitSleepJoin
Thread finished work.
While sleeping: IsAlive = False, State = Stopped
After finishing: IsAlive = False, State = Stopped

**Explanation:**

In this example, we demonstrate the use of the thread life cycle in C#. First, we create an object th1 in the unstarted state, so IsAlive is false. After that, when we called the Start() method, the thread moved to the Running state. Inside the Do() method, the thread sleeps for 1 second. After completing its task, the thread ends and enters the Stopped state, where IsAlive becomes false again. The program prints the thread state at each step to show this transition.

## Features of the Thread Life Cycle in C#

There are several features of the thread life cycle in C#. Some of them are as follows:

- In C#, a thread passes through different states during its lifetime, including Unstarted, Runnable, Running, WaitSleepJoin, and Dead.
- A thread life cycle starts when an object of a thread is created using the System.Threading.Thread class.
- The thread execution is controlled by a thread scheduler that chooses which one of the threads runs at a given time.
- C# enables a thread to run either as foreground or background.
- Thread exceptions should be handled explicitly inside the thread; otherwise, they can cause the thread to terminate unexpectedly.

## Conclusion

In conclusion, a thread life cycle represents a thread being created, started, running, paused, and ending. It helps us to manage threads easily and make the programs work smoothly. It manages the concurrent operation. Additionally, it enhances resource utilization and enables multitasking in applications.