It causes all the calling threads to wait until the current thread (joined thread) is terminated or completes its task.

[](https://www.tpointtech.com/c-sharp-thread-join#)[](https://www.tpointtech.com/c-sharp-thread-join#)[](https://www.tpointtech.com/c-sharp-thread-join#)

1. using System;  
2. using System.Threading;  
3. public class MyThread  
4. {  
5.     public void Thread1()  
6.     {  
7.         for (int i = 0; i < 5; i++)  
8.         {  
9.             Console.WriteLine(i);  
10.             Thread.Sleep(200);  
11.         }  
12.     }  
13. }  
14. public class ThreadExample  
15. {  
16.     public static void Main()  
17.     {  
18.         MyThread mt = new MyThread();  
19.         Thread t1 = new Thread(new ThreadStart(mt.Thread1));  
20.         Thread t2 = new Thread(new ThreadStart(mt.Thread1));  
21.         Thread t3 = new Thread(new ThreadStart(mt.Thread1));  
22.         t1.Start();  
23.         t1.Join();  
24.         t2.Start();  
25.         t3.Start();  
26.     }  
27. }  

Output:

0
1
2
3
4
0
0
1
1
2
2
3
3
4
4