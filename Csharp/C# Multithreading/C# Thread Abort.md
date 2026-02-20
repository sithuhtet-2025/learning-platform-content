The Abort() method is used to terminate the thread. It raises ThreadAbortException if Abort operation is not done.

[](https://www.tpointtech.com/c-sharp-thread-abort#)[](https://www.tpointtech.com/c-sharp-thread-abort#)[](https://www.tpointtech.com/c-sharp-thread-abort#)

1. using System;  
2. using System.Threading;  
3. public class MyThread  
4. {  
5.     public void Thread1()  
6.     {  
7.         for (int i = 0; i < 10; i++)  
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
18.         Console.WriteLine("Start of Main");  
19.         MyThread mt = new MyThread();  
20.         Thread t1 = new Thread(new ThreadStart(mt.Thread1));  
21.         Thread t2 = new Thread(new ThreadStart(mt.Thread1));  

22.         t1.Start();  
23.         t2.Start();  
24.         try  
25.         {  
26.             t1.Abort();  
27.             t2.Abort();  
28.         }  
29.         catch (ThreadAbortException tae)  
30.         {  
31.             Console.WriteLine(tae.ToString());  
32.         }  
33.         Console.WriteLine("End of Main");  
34.     }  
35. }  

Output:

Output is unpredictable because thread may be in running state.

Start of Main
0
End of Main