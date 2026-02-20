Let's see an example where we are changing the priority of the thread. The high priority thread can be executed first. But it is not guaranteed because thread is highly system dependent. It increases the chance of the high priority thread to execute before low priority thread.

[](https://www.tpointtech.com/c-sharp-threadpriority#)[](https://www.tpointtech.com/c-sharp-threadpriority#)[](https://www.tpointtech.com/c-sharp-threadpriority#)

1. using System;  
2. using System.Threading;  
3. public class MyThread  
4. {  
5.     public void Thread1()  
6.     {  
7.         Thread t = Thread.CurrentThread;  
8.         Console.WriteLine(t.Name+" is running");  
9.     }  
10. }  
11. public class ThreadExample  
12. {  
13.     public static void Main()  
14.     {  
15.         MyThread mt = new MyThread();  
16.         Thread t1 = new Thread(new ThreadStart(mt.Thread1));  
17.         Thread t2 = new Thread(new ThreadStart(mt.Thread1));  
18.         Thread t3 = new Thread(new ThreadStart(mt.Thread1));  
19.         t1.Name = "Player1";  
20.         t2.Name = "Player2";  
21.         t3.Name = "Player3";  
22.         t3.Priority = ThreadPriority.Highest;  
23.         t2.Priority = ThreadPriority.Normal;  
24.         t1.Priority = ThreadPriority.Lowest;  

25.         t1.Start();  
26.         t2.Start();  
27.         t3.Start();  
28.     }  
29. }  

Output:

The output is unpredictable because threads are highly system dependent. It may follow any algorithm preemptive or non-preemptive.

Player1 is running
Player3 is running
Player2 is running